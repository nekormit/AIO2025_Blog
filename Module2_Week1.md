## I. Python List vs. NumPy List

**NumPy** (Numerical Python) là một thư viện toán học mạnh trong Python, chuyên dùng để **xử lý các mảng** và ma trận **lớn, đa chiều**. Nó cung cấp nhiều hàm toán học để thực hiện các phép toán trên các mảng này một cách hiệu quả. NumPy là nền tảng cho nhiều thư viện khoa học dữ liệu khác như Pandas, Matplotlib, Scikit-learn.

### 1. Sự khác biệt cơ bản

#### Python List
```python
my_list = [1, "hello", 3.14, True]
print(my_list)
```

Bên trên là list bình thường của Python, có thể thấy list có sự linh hoạt, có thể chứa nhiều kiểu dữ liệu.

Tuy nhiên khi làm việc với lượng dữ liệu lớn trong DS/AI, list gặp phải các vấn đề:
- **Quá tải chi phí** (Element Overhead)
- **Phân mảnh bộ nhớ** (Memory Fragmentation)
- **Hiệu suất thấp** (Low performance)

#### NumPy Array
```python
import numpy as np

my_array = np.array([1, 2, 3, 4])
print(my_array)
# Output: [1 2 3 4]
print(my_array.dtype)
# Output: int64 (hoặc int32 tùy hệ thống)
```

Do đó chúng ta có **NumPy** với các ưu điểm:
- **Dữ liệu đồng nhất** (Homogeneous Data)
- **Kiểu dữ liệu cố định** (Fixed Data Type)
- **Bộ nhớ liền mạch** (Contiguous Memory)
- **Hiệu suất vượt trội** (Superior Performance)

### 2. So sánh các phép toán

#### Phép cộng (+)

**Với List:**
```python
list1 = [1, 2]
list2 = [3, 4]
print(list1 + list2)
# Output: [1, 2, 3, 4]
```

**Với NumPy Array:**
```python
arr1 = np.array([1, 2])
arr2 = np.array([3, 4])
print(arr1 + arr2)
# Output: [4 6]
```

#### Phép nhân

**Với List:**
```python
my_list = [1, 2]
print(my_list * 3)
# Output: [1, 2, 1, 2, 1, 2]
```

**Với NumPy Array:**
```python
my_array = np.array([1, 2])
print(my_array * 3)
# Output: [3 6]
```

Có thể thấy sự khác biệt thông qua 2 ví dụ bên trên.

## 3. Kỹ thuật nâng cao với NumPy

### a) Integer Array Indexing và Boolean Array Indexing

Cho phép chọn lọc các phần tử một cách linh hoạt, tạo ra các mảng mới dựa trên các chỉ mục hoặc điều kiện cụ thể.

```python
arr = np.array([1, 8, 2, 5, 4, 6, 0, 7, 9, 3])
print("Mảng gốc:", arr)

# Lọc các phần tử nhỏ hơn 7
filtered_arr = arr[arr < 7]
print(filtered_arr)
# Output: [1 2 5 4 6 0 3]
```

**Ví dụ về boolean indexing**

### b) Array Manipulation

- **Reshaping**
- **Flattening**
- **Concatenation**

#### Concatenation (Ghép mảng)

```python
arr_a = np.array([[0, 1], [2, 3]])
arr_b = np.array([[4, 5], [6, 7]])

# Ghép theo chiều dọc (Vertical Stack)
v_stacked = np.vstack((arr_a, arr_b))
print(v_stacked)
# Output:
# [[0 1]
#  [2 3]
#  [4 5]
#  [6 7]]

# Ghép theo chiều ngang (Horizontal Stack)
h_stacked = np.hstack((arr_a, arr_b))
print(h_stacked)
# Output:
# [[0 1 4 5]
#  [2 3 6 7]]
```

NumPy cung cấp khả năng thao tác mảng ở mức độ chi tiết hơn. Theo ví dụ trên, 2 hàm `vstack` và `hstack` sắp xếp lại mảng theo chiều dọc và chiều ngang, trong khi list không cung cấp hàm như vậy.

### c) Broadcasting

Một cơ chế cho phép NumPy thực hiện các phép toán số học trên các mảng có hình dạng khác nhau.

Về cơ bản nó "kéo dài" mảng nhỏ hơn để phù hợp với hình dạng của mảng lớn hơn.

#### Ví dụ Broadcasting:

```python
a = np.array([[1, 2], [3, 4], [5, 6]])  # Mảng 2D (3 hàng, 2 cột)
b = np.array([10, 20])                   # Mảng 1D (2 phần tử)

# NumPy sẽ 'broadcast' mảng 'b' để có thể cộng với mảng hàng của 'a'
result = a + b
print("Kết quả Broadcasting:\n", result)
# Output:
# Kết quả Broadcasting:
# [[11 22]
#  [13 24]
#  [15 26]]
```

Nhờ khả năng này, chúng ta không phải viết thêm các vòng lặp tường minh.

### d) Vectorization

Vectorization là việc thực hiện các phép toán trên toàn bộ mảng thay vì xử lý từng phần tử một bằng các vòng lặp Python tường minh.

- **Loại bỏ vòng lặp tường minh** (Eliminating Explicit Loops)
- **Tính toán nhanh hơn đáng kể** (Significantly Faster calculation)

#### Ví dụ so sánh:

```python
# Cách không vector hóa (sử dụng list và vòng lặp)
list1 = [1, 2, 3]
list2 = [4, 5, 6]
result_list = []
for i in range(len(list1)):
    result_list.append(list1[i] + list2[i])
print("Kết quả với List và vòng lặp:", result_list)
# Output: Kết quả với List và vòng lặp: [5, 7, 9]

# Cách vector hóa (sử dụng NumPy)
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
result_array = arr1 + arr2
print("Kết quả với NumPy Array:", result_array)
# Output: Kết quả với NumPy Array: [5 7 9]
```

Trong ví dụ trên, NumPy xử lý đơn giản và trực tiếp, đồng thời mang lại hiệu suất vượt trội khi dữ liệu lớn.

# II. NumPy Cơ Bản và Biểu Diễn Dữ Liệu Vector/Matrix

## 1. Giới thiệu về NumPy

### Tại sao lại dùng NumPy?

- **Hiệu suất cao**: Các phép toán trong NumPy được thực hiện bằng C/C++ ở dưới, giúp tăng tốc độ tính toán đáng kể so với việc dùng list của Python.
- **Tiện lợi**: Cung cấp nhiều hàm và phương thức dùng sẵn giúp thao tác với dữ liệu số học dễ dàng hơn.
- **Cấu trúc dữ liệu chính**: **ndarray** (n-dimensional array) là đối tượng mảng chính của NumPy, cho phép lưu trữ các tập dữ liệu lớn và thực hiện các phép toán trên chúng.

## 2. Vector và Ma trận

### Vector

Trong toán học và khoa học máy tính, vector là một đối tượng có độ lớn và hướng. Nó thường được biểu diễn dưới dạng một danh sách các số.

- **Vector hàng (Row Vector)**: Một vector được biểu diễn theo chiều ngang.
  - Ví dụ: v = [v1,v2,v3]
- **Vector cột (Column Vector)**: Một vector được biểu diễn theo chiều dọc.
  - Ví dụ: v = [v1; v2; v3]

Trong NumPy, vector có thể được biểu diễn bằng một mảng 1 chiều.

### Ma trận

Ma trận là một bảng chữ nhật các số, được sắp xếp thành các hàng và cột. Ma trận thường được sử dụng để biểu diễn các tập dữ liệu, hệ phương trình tuyến tính, hoặc các phép biến đổi hình học.

- **Kích thước của ma trận**: Được xác định bởi số hàng (m) và số cột (n), ký hiệu là m×n.
- **Ví dụ**: Một ma trận 3×2 có 3 hàng và 2 cột:

```
A = [a11  a12]
    [a21  a22]
    [a31  a32]
```

Trong NumPy, ma trận được biểu diễn bằng một mảng 2 chiều (hoặc nhiều hơn với mảng đa chiều).

## 3. Indexing trong NumPy

**Indexing** (truy cập phần tử) trong NumPy cho phép chúng ta chọn hoặc thay đổi các phần tử của mảng dữ liệu trên vị trí của chúng. Cách thức indexing trong NumPy tương tự như Python list nhưng mạnh mẽ hơn với các mảng đa chiều.

### Indexing 1 chiều: Giống như list Python.
**Ví dụ**: Cho arr = np.array([10, 20, 30, 40, 50])
- arr[0] sẽ trả về 10
- arr[-1] sẽ trả về 50 (30, 40, 50)

### Indexing 2 chiều (Ma trận): Sử dụng cú pháp [hàng, cột].
**Ví dụ**: Cho matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
- matrix[0, 0] sẽ trả về 1 (phần tử ở hàng 0, cột 0)
- matrix[1, :] sẽ trả về [4, 5, 6] (toàn bộ hàng 1)
- matrix[:, 2] sẽ trả về [3, 6, 9] (toàn bộ cột 2)
- -1 sẽ trả về một ma trận con:

```
[2  3]
[5  6]
```

## 4. Broadcasting trong NumPy

Broadcasting là một cơ chế mạnh mẽ của NumPy cho phép thực hiện các phép toán trên các mảng có hình dạng (shape) khác nhau. Khi thực hiện một phép toán nhi phân trên hai mảng, NumPy sẽ tự động "mở rộng" mảng có kích thước nhỏ hơn để phù hợp với kích thước của mảng lớn hơn, miễn là chúng tương thích.

### Quy tắc Broadcasting:

Để hai mảng có thể broadcast với nhau, các kích thước của chúng phải tương thích. Hai kích thước tương thích nếu:

1. Chúng bằng nhau.
2. Một trong số chúng là 1.

Quá trình broadcasting diễn ra từ chiều cuối cùng trở về chiều đầu tiên.

### Ví dụ minh họa:

#### Mảng với một số vô hướng:
- np.array([1, 2, 3]) + 5
- Kết quả: [6, 7, 8]
- NumPy sẽ "mở rộng" số 5 thành mảng [5, 5, 5] để thực hiện phép cộng.

#### Mảng 2 chiều với mảng 1 chiều:
- Cho A = np.array([[1, 2, 3], [4, 5, 6]]) (shape (2, 3))
- Cho B = np.array([10, 20, 30]) (shape (3,))
- A + B sẽ hoạt động. NumPy sẽ mở rộng B thành:

```
[10  20  30]
[10  20  30]
```

và sau đó thực hiện phép cộng từng phần tử:

```
[11  22  33]
[14  25  36]
```

#### Ví dụ về tài liệu (trang 2):
Phép nhân data * 2 cho thấy broadcasting hoạt động như thế nào với dữ liệu được nhân với 2:

```
data = [1  2]
       [3  4]
       [5  6]

result = data * 2 = [1*2  2*2] = [2   4]
                    [3*2  4*2]   [6   8]
                    [5*2  6*2]   [10  12]
```

Broadcasting là một tính năng mạnh mẽ giúp tránh việc phải tạo ra các bản sao lớn của mảng trong bộ nhớ, làm cho mã biểu quả và dễ đọc hơn.

## 5. Ứng dụng của One-hot Encoding

One-hot Encoding là một kỹ thuật thường dùng trong học máy để biến đổi các biến phân loại (categorical variables) thành một định dạng số mà các thuật toán học máy có thể hiểu và xử lý được.

### Cách hoạt động:

Với mỗi giá trị duy nhất trong biến phân loại, một vector nhị phân (binary vector) mới được tạo ra. Vector này sẽ có độ dài tương ứng với giá trị đó với 1 ở vị trí đó và 0 ở các vị trí còn lại.

### Ví dụ từ tài liệu (trang 61, 62):

#### Trường hợp 2 lớp (classes=2):
- Nếu nhãn y=0 → vector y=[1, 0]
- Nếu nhãn y=1 → vector y=[0, 1]

#### Trường hợp 3 lớp (classes=3):
- Nếu nhãn y=0 → vector y=[1, 0, 0]
- Nếu nhãn y=1 → vector y=[0, 1, 0]
- Nếu nhãn y=2 → vector y=[0, 0, 1]

### Ý nghĩa:

One-hot encoding giúp biểu diễn các biến phân loại một cách mà các mô hình học máy không gán ý nghĩa thứ bậc (ordinal meaning) cho chúng. Ví dụ, nếu chúng ta mã hóa "đỏ", "xanh", "vàng" thành 0, 1, 2 thì mô hình sẽ thuật toán có thể hiểu nhầm rằng "xanh" lớn hơn "đỏ", điều này không đúng. One-hot encoding giải quyết vấn đề này bằng cách tạo ra các vector độc lập.

# Linear Algebra and Applications: Vector Operations & Matrix Fundamentals

---

## Introduction: Tại sao Linear Algebra quan trọng?

### Ứng dụng trong Machine Learning

Linear Algebra là nền tảng của Machine Learning. Hãy xem các ví dụ thực tế:

#### **Dự đoán giá nhà**
```
price = a × area + b
```
Mô hình tuyến tính đơn giản với 1 đặc trưng (area - diện tích)

#### **Dự đoán doanh số quảng cáo**
```
Sales = a₁ × TV + a₂ × Radio + a₃ × Newspaper + b
```
Mô hình với 3 đặc trưng (TV, Radio, Newspaper)

#### **Boston House Price Data**
```
medv = a₁ × x₁ + a₂ × x₂ + ... + a₁₃ × x₁₃ + b
```
Mô hình phức tạp với 13 đặc trưng

---

## Section 1: Vector & Matrix Fundamentals

### 1.1 Khái niệm cơ bản về Vector

**Vector** là một mảng một chiều chứa các số thực:

```python
# Vector trong Python
import numpy as np

# Tạo vector
v = np.array([1, 2, 3])
print(v)  # [1 2 3]
```

**Định nghĩa toán học:**
- Vector có độ dài n và chứa các số thực
- ℝⁿ (thuộc không gian số thực n chiều)

```
v⃗ = [v₁]
    [v₂]
    [v₃]
```

### 1.2 Khái niệm cơ bản về Matrix

**Matrix** là một mảng hai chiều với m hàng và n cột:

```python
# Matrix trong Python
A = np.array([[1, 3], 
              [2, 4]])
print(A)
# [[1 3]
#  [2 4]]
```

**Định nghĩa toán học:**
- Matrix **A** có m hàng và n cột
- A ∈ ℝᵐˣⁿ (thuộc không gian ma trận m×n)

```
A = [a₁₁  a₁₂]
    [a₂₁  a₂₂]
    [a₃₁  a₃₂]
```

### 1.3 Hệ phương trình tuyến tính

Linear Algebra giúp giải quyết hệ phương trình tuyến tính dạng **Ax = b**:

```
Sales = a₁ × TV + a₂ × Radio + a₃ × Newspaper + b
```

Có thể viết dưới dạng ma trận:

```
[T₁  R₁  N₁] [a₁]   [S₁]
[T₂  R₂  N₂] [a₂] = [S₂]
[T₃  R₃  N₃] [a₃]   [S₃]
```

---

## Section 2: Vector Operations

### 2.1 Phép cộng Vector

**Cộng hai vector** có cùng kích thước:

```python
# Ví dụ với NumPy
data_x = np.array([1, 2, 3, 4])
data_y = np.array([5, 6, 7, 8])

result = data_x + data_y
print(result)  # [6 8 10 12]
```

**Công thức toán học:**
```
v⃗ + u⃗ = [v₁ + u₁]
         [v₂ + u₂]
         [v₃ + u₃]
```

### 2.2 Phép trừ Vector

```python
# Ví dụ với NumPy
data_x = np.array([5, 6, 7, 8])
data_y = np.array([1, 2, 3, 4])

result = data_x - data_y
print(result)  # [4 4 4 4]
```

**Công thức toán học:**
```
v⃗ - u⃗ = [v₁ - u₁]
         [v₂ - u₂]
         [v₃ - u₃]
```

### 2.3 Nhân Vector với số

```python
# Nhân vector với scalar
data = np.array([1, 2, 3])
alpha = 2

result = alpha * data
print(result)  # [2 4 6]
```

**Công thức toán học:**
```
α × u⃗ = [α × u₁]
        [α × u₂]
        [α × u₃]
```

### 2.4 Độ dài của Vector (Norm)

```python
# Tính độ dài vector
u = np.array([1, 2, 4, 2])
length = np.linalg.norm(u)
print(f"Độ dài vector: {length}")  # 5.0
```

**Công thức toán học:**
```
||u⃗|| = √(u₁² + u₂² + ... + uₙ²)
```

### 2.5 Tích vô hướng (Dot Product)

Tích vô hướng là một phép toán quan trọng:

```python
# Dot product
v = np.array([1, 2, 2])
w = np.array([3, 1, 1])

result = np.dot(v, w)
print(result)  # 8
```

**Công thức toán học:**
```
v⃗ · w⃗ = v₁×w₁ + v₂×w₂ + v₃×w₃
```

#### **Ứng dụng thực tế: Chuyển đổi ảnh màu sang xám**

```python
# Chuyển đổi RGB sang Grayscale
rgb_weights = np.array([0.213, 0.715, 0.072])
rgb_pixel = np.array([120, 80, 60])  # Red, Green, Blue

grayscale_value = np.dot(rgb_weights, rgb_pixel)
print(f"Giá trị grayscale: {grayscale_value}")
```

---

## Section 3: Matrix Operations

### 3.1 Phép cộng và trừ Matrix

```python
# Cộng matrix
A = np.array([[4, 9], 
              [2, 8]])
B = np.array([[1, 3], 
              [2, 4]])

C = A + B
print(C)
# [[5 12]
#  [4 12]]

# Trừ matrix
D = A - B
print(D)
# [[3 6]
#  [0 4]]
```

### 3.2 Hadamard Product (Nhân từng phần tử)

```python
# Nhân từng phần tử
data_x = np.array([1, 2, 3, 4])
data_y = np.array([5, 6, 7, 8])

result = data_x * data_y  # Hadamard product
print(result)  # [5 12 21 32]
```

**Ký hiệu toán học:**
```
u⃗ ⊙ v⃗ = [u₁ × v₁]
         [u₂ × v₂]
         [u₃ × v₃]
```

### 3.3 Hadamard Division

```python
# Chia từng phần tử
data_x = np.array([1, 2, 3, 4])
data_y = np.array([5, 6, 7, 8])

result = data_x / data_y
print(result)  # [0.2 0.33 0.42 0.5]
```

### 3.4 Nhân Matrix-Vector

```python
# Matrix-vector multiplication
X = np.array([[1, 3], 
              [2, 4]])
v = np.array([1, 2])

result = np.dot(X, v)
print(result)  # [5 11]
```

**Công thức toán học:**
```
c⃗ = A × x⃗
cᵢ = Σ(aᵢⱼ × xⱼ)
```

### 3.5 Nhân Matrix-Matrix

```python
# Matrix-matrix multiplication
X = np.array([[1, 3], 
              [2, 4]])
Y = np.array([[2, 2], 
              [3, 1]])

result = np.dot(X, Y)
print(result)
# [[11  5]
#  [16  8]]
```

**Công thức toán học:**
```
C = A × B
cᵢⱼ = Σ(aᵢₖ × bₖⱼ)
```

### 3.6 Transpose Matrix

```python
# Transpose matrix
A = np.array([[1, 3], 
              [2, 4]])

A_T = A.T
print(A_T)
# [[1 2]
#  [3 4]]
```

**Công thức toán học:**
```
Aᵀ = [a₁₁  a₂₁  a₃₁]
     [a₁₂  a₂₂  a₃₂]
```

---

## Section 4: Các hàm toán học hữu ích

### 4.1 Hàm argmin và argmax

```python
# Tìm chỉ số của giá trị nhỏ nhất và lớn nhất
x = np.array([4, 7, 1, 5])

min_index = np.argmin(x)  # 2
max_index = np.argmax(x)  # 1

print(f"Chỉ số min: {min_index}, giá trị: {x[min_index]}")
print(f"Chỉ số max: {max_index}, giá trị: {x[max_index]}")
```

### 4.2 Hàm min và max

```python
# Tìm giá trị nhỏ nhất và lớn nhất
x = np.array([4, 7, 1, 5])

min_val = np.min(x)  # 1
max_val = np.max(x)  # 7

print(f"Giá trị min: {min_val}")
print(f"Giá trị max: {max_val}")
```

### 4.3 Summation và Average

```python
# Tính tổng và trung bình
x = np.array([6, 5, 7, 1, 9, 2])

total = np.sum(x)     # 30
average = np.mean(x)  # 5.0

print(f"Tổng: {total}")
print(f"Trung bình: {average}")
```

### 4.4 Các hàm Hadamard khác

```python
# Căn bậc hai
data = np.array([1, 2, 3, 4])
sqrt_data = np.sqrt(data)
print(sqrt_data)  # [1.0 1.4 1.7 2.0]

# Hàm exp
exp_data = np.exp(data)
print(exp_data)  # [2.718 7.389 20.086 54.598]
```

---
# Đại số tuyến tính trong thực tế: Từ vector đến ứng dụng

Đại số tuyến tính không chỉ là một môn học trừu tượng mà còn là nền tảng của nhiều ứng dụng công nghệ hiện đại. Từ dự đoán giá nhà, phân tích dữ liệu quảng cáo đến xử lý hình ảnh, vector và ma trận đóng vai trò quan trọng trong việc giải quyết các bài toán thực tế.

## 1. Vector và Ma trận: Nền tảng của mọi thứ

### Vector - Khái niệm cơ bản

Vector là một mảng có thứ tự các số thực. Trong không gian n chiều, vector **v** ∈ ℝⁿ được biểu diễn:

```
v = [v₁, v₂, v₃, ..., vₙ]ᵀ
```

**Ví dụ thực tế**: Trong bài toán dự đoán giá nhà, mỗi ngôi nhà có thể được biểu diễn bằng vector đặc trưng:

```python
import numpy as np

# Đặc trưng ngôi nhà: [diện tích, số phòng, tuổi nhà, khoảng cách]
house_features = np.array([120, 3, 5, 2])
print(f"Vector đặc trưng: {house_features}")
```

### Ma trận - Cấu trúc dữ liệu mạnh mẽ

Ma trận **A** ∈ ℝᵐˣⁿ có m hàng và n cột:

```
A = [a₁₁  a₁₂  ...  a₁ₙ]
    [a₂₁  a₂₂  ...  a₂ₙ]
    [... ... ... ...]
    [aₘ₁  aₘ₂  ...  aₘₙ]
```

**Ví dụ thực tế**: Dữ liệu ngân sách quảng cáo của 3 sản phẩm trên 3 kênh:

```python
# Ma trận ngân sách quảng cáo (triệu đồng)
# Hàng: sản phẩm, Cột: kênh [TV, Radio, Newspaper]
advertising_matrix = np.array([
    [100, 50, 20],  # Sản phẩm 1
    [80, 60, 30],   # Sản phẩm 2
    [120, 40, 25]   # Sản phẩm 3
])
print("Ma trận ngân sách quảng cáo:")
print(advertising_matrix)
```

## 2. Các phép toán Vector cơ bản

### Phép cộng và trừ Vector

Với hai vector **u** = [u₁, u₂, ..., uₙ]ᵀ và **v** = [v₁, v₂, ..., vₙ]ᵀ:

```
u + v = [u₁ + v₁, u₂ + v₂, ..., uₙ + vₙ]ᵀ
u - v = [u₁ - v₁, u₂ - v₂, ..., uₙ - vₙ]ᵀ
```

**Ví dụ**: Tính tổng doanh thu của hai quý:

```python
# Doanh thu theo tháng (triệu đồng)
quarter_1 = np.array([100, 150, 200])
quarter_2 = np.array([120, 180, 210])

# Phép cộng vector
total_revenue = quarter_1 + quarter_2
print(f"Quý 1: {quarter_1}")
print(f"Quý 2: {quarter_2}")
print(f"Tổng doanh thu: {total_revenue}")

# Phép trừ vector - tính tăng trưởng
growth = quarter_2 - quarter_1
print(f"Tăng trưởng: {growth}")
```

### Phép nhân Hadamard (Element-wise)

Nhân từng phần tử tương ứng:
```
u ⊙ v = [u₁ × v₁, u₂ × v₂, ..., uₙ × vₙ]ᵀ
```

**Ví dụ**: Tính tổng chi phí sản xuất:

```python
# Số lượng sản phẩm và giá thành đơn vị
quantity = np.array([100, 200, 150])
unit_cost = np.array([50, 80, 120])  # nghìn đồng

# Phép nhân Hadamard
total_cost = quantity * unit_cost
print(f"Số lượng: {quantity}")
print(f"Giá thành: {unit_cost}")
print(f"Tổng chi phí: {total_cost} nghìn đồng")
```

### Phép chia Hadamard

```
u ⊘ v = [u₁/v₁, u₂/v₂, ..., uₙ/vₙ]ᵀ
```

**Ví dụ**: Tính tỷ lệ hoàn thành kế hoạch:

```python
# Thực hiện và kế hoạch
actual = np.array([80, 120, 90])
planned = np.array([100, 100, 100])

# Phép chia Hadamard
completion_rate = actual / planned
print(f"Thực hiện: {actual}")
print(f"Kế hoạch: {planned}")
print(f"Tỷ lệ hoàn thành: {completion_rate}")
print(f"Tỷ lệ phần trăm: {completion_rate * 100}%")
```

### Nhân với số vô hướng

```
αu = [αu₁, αu₂, ..., αuₙ]ᵀ
```

**Ví dụ**: Tăng lương 15% cho nhân viên:

```python
# Lương hiện tại (triệu đồng)
current_salary = np.array([10, 12, 15])
raise_rate = 1.15

# Nhân với số vô hướng
new_salary = raise_rate * current_salary
print(f"Lương hiện tại: {current_salary}")
print(f"Lương mới (+15%): {new_salary}")
```

### Độ dài Vector (Norm)

```
||u|| = √(u₁² + u₂² + ... + uₙ²)
```

**Ví dụ**: Tính khoảng cách Euclidean:

```python
# Tọa độ điểm A và B
point_a = np.array([0, 0])
point_b = np.array([3, 4])

# Vector từ A đến B
vector_ab = point_b - point_a

# Độ dài vector (norm)
distance = np.linalg.norm(vector_ab)
print(f"Điểm A: {point_a}")
print(f"Điểm B: {point_b}")
print(f"Vector AB: {vector_ab}")
print(f"Khoảng cách: {distance}")
```

## 3. Tích vô hướng (Dot Product)

### Định nghĩa

Tích vô hướng của hai vector **u** và **v**:
```
u · v = u₁v₁ + u₂v₂ + ... + uₙvₙ
```

**Ví dụ**: Tính tổng doanh thu từ nhiều sản phẩm:

```python
# Số lượng bán và giá bán
quantities = np.array([100, 50, 80])
prices = np.array([200, 500, 300])  # nghìn đồng

# Tích vô hướng
total_revenue = np.dot(quantities, prices)
print(f"Số lượng: {quantities}")
print(f"Giá bán: {prices}")
print(f"Tổng doanh thu: {total_revenue} nghìn đồng")

# Cách tính thủ công để kiểm tra
manual_calc = 100*200 + 50*500 + 80*300
print(f"Tính thủ công: {manual_calc}")
```

### Ứng dụng: Chuyển đổi ảnh màu sang xám

Công thức chuẩn RGB to Grayscale:
```
Gray = 0.299×R + 0.587×G + 0.114×B
```

```python
# Trọng số chuyển đổi RGB sang grayscale
rgb_weights = np.array([0.299, 0.587, 0.114])

# Pixel màu RGB
rgb_pixel = np.array([150, 100, 50])

# Chuyển đổi sang grayscale bằng dot product
gray_value = np.dot(rgb_weights, rgb_pixel)
print(f"Pixel RGB: {rgb_pixel}")
print(f"Trọng số: {rgb_weights}")
print(f"Giá trị xám: {gray_value:.1f}")

# Ví dụ với nhiều pixel
rgb_image = np.array([
    [255, 0, 0],    # Đỏ
    [0, 255, 0],    # Xanh lá
    [0, 0, 255],    # Xanh dương
    [255, 255, 255] # Trắng
])

# Chuyển đổi toàn bộ ảnh
gray_image = rgb_image @ rgb_weights  # @ là ký hiệu dot product
print(f"Ảnh RGB:\n{rgb_image}")
print(f"Ảnh xám: {gray_image}")
```

## 4. Phép toán Ma trận

### Cộng và trừ Ma trận

Với hai ma trận cùng kích thước:
```
(A + B)ᵢⱼ = Aᵢⱼ + Bᵢⱼ
(A - B)ᵢⱼ = Aᵢⱼ - Bᵢⱼ
```

**Ví dụ**: So sánh doanh thu 2 tháng:

```python
# Doanh thu theo khu vực và sản phẩm
month_1 = np.array([
    [100, 80],   # Khu vực 1
    [150, 90]    # Khu vực 2
])

month_2 = np.array([
    [120, 90],   # Khu vực 1
    [140, 100]   # Khu vực 2
])

# Phép cộng ma trận
total_revenue = month_1 + month_2
print(f"Tháng 1:\n{month_1}")
print(f"Tháng 2:\n{month_2}")
print(f"Tổng doanh thu:\n{total_revenue}")

# Phép trừ ma trận - tính tăng trưởng
growth = month_2 - month_1
print(f"Tăng trưởng:\n{growth}")
```

### Nhân Ma trận - Vector

```
c = Ax, với cᵢ = Σⱼ Aᵢⱼ × xⱼ
```

**Ví dụ**: Tính tổng chi phí cho 3 bộ phận:

```python
# Ma trận chi phí đơn vị (triệu đồng)
# Hàng: bộ phận, Cột: loại chi phí [nhân sự, thiết bị, vật tư]
unit_costs = np.array([
    [10, 20, 30],  # Bộ phận 1
    [15, 25, 35],  # Bộ phận 2
    [12, 18, 28]   # Bộ phận 3
])

# Vector số lượng
quantities = np.array([5, 3, 2])  # 5 nhân viên, 3 thiết bị, 2 vật tư

# Nhân ma trận - vector
total_costs = unit_costs @ quantities
print(f"Ma trận chi phí đơn vị:\n{unit_costs}")
print(f"Số lượng: {quantities}")
print(f"Tổng chi phí mỗi bộ phận: {total_costs}")
```

### Nhân Ma trận - Ma trận

```
C = A × B, với Cᵢⱼ = Σₖ Aᵢₖ × Bₖⱼ
```

**Ví dụ**: Tính doanh thu theo khu vực và thị trường:

```python
# Ma trận số lượng bán theo khu vực và sản phẩm
sales_by_region = np.array([
    [10, 20],  # Khu vực 1: sản phẩm A, B
    [15, 25]   # Khu vực 2: sản phẩm A, B
])

# Ma trận giá bán theo sản phẩm và thị trường
prices_by_market = np.array([
    [100, 120],  # Sản phẩm A: thị trường 1, 2
    [80, 90]     # Sản phẩm B: thị trường 1, 2
])

# Nhân ma trận - ma trận
revenue_matrix = sales_by_region @ prices_by_market
print(f"Số lượng bán:\n{sales_by_region}")
print(f"Giá bán:\n{prices_by_market}")
print(f"Doanh thu theo khu vực và thị trường:\n{revenue_matrix}")
```

### Chuyển vị Ma trận

```
(Aᵀ)ᵢⱼ = Aⱼᵢ
```

**Ví dụ**: Chuyển đổi cách nhìn dữ liệu:

```python
# Dữ liệu ban đầu: hàng là sản phẩm, cột là tháng
original_data = np.array([
    [100, 120, 110],  # Sản phẩm A
    [80, 90, 95]      # Sản phẩm B
])

# Chuyển vị: hàng là tháng, cột là sản phẩm
transposed_data = original_data.T
print(f"Dữ liệu gốc (sản phẩm x tháng):\n{original_data}")
print(f"Dữ liệu chuyển vị (tháng x sản phẩm):\n{transposed_data}")
```

## 5. Các hàm tiện ích quan trọng

### Hàm Min/Max và ArgMin/ArgMax

```
min(x) = giá trị nhỏ nhất trong x
argmin(x) = chỉ số của giá trị nhỏ nhất
max(x) = giá trị lớn nhất trong x
argmax(x) = chỉ số của giá trị lớn nhất
```

**Ví dụ**: Phân tích doanh thu theo tháng:

```python
# Doanh thu theo tháng (triệu đồng)
monthly_revenue = np.array([100, 120, 80, 150, 110])

# Tìm giá trị min/max
min_revenue = np.min(monthly_revenue)
max_revenue = np.max(monthly_revenue)

# Tìm chỉ số của min/max
min_month = np.argmin(monthly_revenue)
max_month = np.argmax(monthly_revenue)

print(f"Doanh thu theo tháng: {monthly_revenue}")
print(f"Doanh thu thấp nhất: {min_revenue} (tháng {min_month + 1})")
print(f"Doanh thu cao nhất: {max_revenue} (tháng {max_month + 1})")
```

### Hàm Sum và Average

```
sum(x) = Σᵢ xᵢ
average(x) = (1/n) × Σᵢ xᵢ
```

**Ví dụ**: Tính tổng và trung bình:

```python
# Doanh thu 5 tháng
revenue_data = np.array([100, 120, 80, 150, 110])

# Tính tổng và trung bình
total_sum = np.sum(revenue_data)
average_revenue = np.mean(revenue_data)

print(f"Doanh thu 5 tháng: {revenue_data}")
print(f"Tổng doanh thu: {total_sum} triệu đồng")
print(f"Doanh thu trung bình: {average_revenue:.1f} triệu đồng")

# Tính cho ma trận
matrix_data = np.array([
    [100, 120, 80],
    [150, 110, 90]
])

print(f"\nDữ liệu ma trận:\n{matrix_data}")
print(f"Tổng toàn bộ: {np.sum(matrix_data)}")
print(f"Tổng theo hàng: {np.sum(matrix_data, axis=1)}")
print(f"Tổng theo cột: {np.sum(matrix_data, axis=0)}")
print(f"Trung bình toàn bộ: {np.mean(matrix_data):.1f}")
```

### Các hàm khác

```python
# Hàm căn bậc hai
data = np.array([1, 4, 9, 16])
sqrt_data = np.sqrt(data)
print(f"Dữ liệu: {data}")
print(f"Căn bậc hai: {sqrt_data}")

# Hàm exponential
exp_data = np.exp(np.array([0, 1, 2]))
print(f"Exponential: {exp_data}")

# Hàm làm tròn
float_data = np.array([1.234, 5.678, 9.999])
rounded_data = np.round(float_data, 2)
print(f"Dữ liệu gốc: {float_data}")
print(f"Làm tròn 2 chữ số: {rounded_data}")
```

## Kết luận

Đại số tuyến tính với vector và ma trận là nền tảng cho hầu hết các ứng dụng khoa học dữ liệu và machine learning hiện đại. Từ những phép toán cơ bản như cộng, trừ, nhân đến các khái niệm phức tạp hơn như tích vô hướng và nhân ma trận, tất cả đều có ứng dụng thực tế rõ ràng trong việc xử lý và phân tích dữ liệu.

Việc nắm vững các khái niệm này không chỉ giúp bạn hiểu sâu hơn về cách thức hoạt động của các thuật toán mà còn mở ra cánh cửa để tiếp cận những chủ đề nâng cao hơn như Background Subtraction và Cosine Similarity - những công cụ mạnh mẽ trong xử lý hình ảnh và đo lường độ tương đồng dữ liệu.
