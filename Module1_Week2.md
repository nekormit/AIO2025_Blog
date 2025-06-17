# Module 1/Week 2 AIO 2025: Data Structures in Python, SQL, Git & Github
---
# List trong Python

## 1. Danh sách 1D (1D List)

### 1.1 Khái niệm cơ bản về danh sách

**Danh sách (List)** là một kiểu dữ liệu quan trọng trong Python, hoạt động như một vùng chứa để lưu trữ nhiều phần tử. Danh sách có thể chứa các phần tử có kiểu dữ liệu khác nhau và được sắp xếp theo thứ tự.

#### 🔸 **Ví dụ tạo danh sách:**

```python
# Danh sách các số nguyên
numbers =

# Danh sách các chuỗi
fruits = ["táo", "cam", "chuối", "xoài"]

# Danh sách hỗn hợp (heterogeneous)
mixed_list = [1, "Hello", 3.14, True]
```

### 1.2 Đặc điểm của danh sách

Danh sách trong Python có **4 đặc điểm** quan trọng:

| Đặc điểm | Mô tả | Ví dụ |
|:----------|:-------|:-------|
| **Có thứ tự (Ordered)** | Các phần tử được sắp xếp theo thứ tự cố định | `[1, 2, 3]` ≠ `[3, 2, 1]` |
| **Có thể trùng lặp (Duplicated)** | Danh sách có thể chứa các phần tử giống nhau | `[1, 2, 2, 3]` |
| **Có thể truy cập bằng chỉ mục (Indexable)** | Mỗi phần tử có vị trí cố định | `list[0]`, `list[1]` |
| **Đa dạng kiểu dữ liệu (Heterogeneous)** | Chứa nhiều kiểu dữ liệu khác nhau | `[1, "text", True]` |


#### 🔸 **Ví dụ minh họa:**
```python
# Danh sách có thứ tự và có thể trùng lặp
scores =  # 92 xuất hiện 2 lần
print(scores)  # - thứ tự được giữ nguyên
```

### 1.3 Truy cập phần tử bằng chỉ mục

#### **Chỉ mục tiến (Forward Indexing)**
Bắt đầu từ `0` và tăng dần:
```python
fruits = ["táo", "cam", "chuối", "xoài"]
print(fruits)  # "táo" (phần tử đầu tiên)
print(fruits)  # "cam" (phần tử thứ hai)
print(fruits)  # "xoài" (phần tử cuối cùng)
```

#### **Chỉ mục lùi (Backward Indexing)**
Bắt đầu từ `-1` và giảm dần:
```python
fruits = ["táo", "cam", "chuối", "xoài"]
print(fruits[-1])  # "xoài" (phần tử cuối cùng)
print(fruits[-2])  # "chuối" (phần tử thứ hai từ cuối)
print(fruits[-4])  # "táo" (phần tử đầu tiên)
```

### 1.4 Cắt lát (Slicing)
Slicing cho phép truy cập một phần của danh sách bằng cú pháp `list[start:end:step]`:

- `start`: Vị trí bắt đầu (bao gồm)
- `end`: Vị trí kết thúc (không bao gồm)
- `step`: Bước nhảy (mặc định là 1)

```python
numbers =

# Lấy từ vị trí 2 đến 5 (không bao gồm 5)
print(numbers[2:5])    #

# Lấy từ đầu đến vị trí 4
print(numbers[:4])     #

# Lấy từ vị trí 6 đến cuối
print(numbers[6:])     #

# Lấy các phần tử cách nhau 2 vị trí
print(numbers[::2])    #

# Đảo ngược danh sách
print(numbers[::-1])   #
```

### 1.5 Các phương thức thêm phần tử

#### 🔸 **`append()`** - Thêm một phần tử vào cuối danh sách.
```python
fruits = ["táo", "cam"]
fruits.append("chuối")
print(fruits)  # ["táo", "cam", "chuối"]
```

#### 🔸 **`insert()`** - Thêm phần tử vào vị trí cụ thể.
```python
fruits = ["táo", "cam"]
fruits.insert(1, "xoài")  # Thêm "xoài" vào vị trí 1
print(fruits)  # ["táo", "xoài", "cam"]
```

#### 🔸 **`extend()`** - Thêm nhiều phần tử từ một danh sách khác.
```python
fruits = ["táo", "cam"]
more_fruits = ["chuối", "xoài"]
fruits.extend(more_fruits)
print(fruits)  # ["táo", "cam", "chuối", "xoài"]
```

### 1.6 Cập nhật phần tử
Sử dụng toán tử gán `=` để thay đổi giá trị của phần tử:

```python
fruits = ["táo", "cam", "chuối"]
fruits = "dưa hấu"  # Thay đổi "cam" thành "dưa hấu"
print(fruits)  # ["táo", "dưa hấu", "chuối"]

# Cập nhật nhiều phần tử cùng lúc bằng slicing
fruits[0:2] = ["nho", "lê"]
print(fruits)  # ["nho", "lê", "chuối"]
```

### 1.7 Các phương thức xóa phần tử

#### 🔸 **`pop()`** - Xóa và trả về phần tử tại vị trí chỉ định. Nếu không có tham số, xóa phần tử cuối.
```python
fruits = ["táo", "cam", "chuối", "xoài"]
removed_fruit = fruits.pop(1)  # Xóa phần tử tại vị trí 1
print(f"Phần tử đã xóa: {removed_fruit}")  # Phần tử đã xóa: cam
print(f"Danh sách còn lại: {fruits}")  # Danh sách còn lại: ['táo', 'chuối', 'xoài']
```

#### 🔸 **`remove()`** - Xóa phần tử đầu tiên có giá trị cụ thể.
```python
fruits = ["táo", "cam", "chuối", "cam"]
fruits.remove("cam")  # Xóa "cam" đầu tiên tìm thấy
print(fruits)  # ["táo", "chuối", "cam"]
```

#### 🔸 **`clear()`** - Xóa tất cả phần tử.
```python
fruits = ["táo", "cam", "chuối"]
fruits.clear()
print(fruits)  # []
```

#### 🔸 **`del`** - Từ khóa để xóa phần tử, lát cắt hoặc cả danh sách.
```python
fruits = ["táo", "cam", "chuối", "xoài"]
del fruits  # Xóa phần tử tại vị trí 1
print(fruits)  # ["táo", "chuối", "xoài"]

del fruits[0:2] # Xóa nhiều phần tử từ vị trí 0 đến 2 (không bao gồm 2)
print(fruits) # ["xoài"]
```

### 1.8 Các phương thức sắp xếp và thao tác

#### 🔸 **`sort()`** - Sắp xếp danh sách tại chỗ (thay đổi danh sách gốc).
```python
numbers =
numbers.sort()  # Sắp xếp tăng dần
print(numbers)  #

numbers.sort(reverse=True)  # Sắp xếp giảm dần
print(numbers)  #
```

#### 🔸 **`reverse()`** - Đảo ngược thứ tự phần tử tại chỗ.
```python
fruits = ["táo", "cam", "chuối"]
fruits.reverse()
print(fruits)  # ["chuối", "cam", "táo"]
```

#### 🔸 **`count()`** - Đếm số lần xuất hiện của một phần tử.
```python
numbers =
count_2 = numbers.count(2)
print(f"Số 2 xuất hiện {count_2} lần.")  # Số 2 xuất hiện 3 lần.
```

#### 🔸 **`copy()`** - Tạo một bản sao nông (shallow copy) của danh sách.
```python
original =
copied = original.copy()
copied = 100
print(f"Danh sách gốc: {original}")  # Danh sách gốc: - không thay đổi
print(f"Danh sách đã sao chép: {copied}")    # Danh sách đã sao chép:
```

#### 🔸 **`index()`** - Tìm chỉ mục của lần xuất hiện đầu tiên của một phần tử.
```python
fruits = ["táo", "cam", "chuối"]
index_cam = fruits.index("cam")
print(f"Vị trí của 'cam' là: {index_cam}")  # Vị trí của 'cam' là: 1
```

### 1.9 Toán tử với danh sách

#### 🔸 **Toán tử `+` (Nối danh sách)**
```python
list1 =
list2 =
combined = list1 + list2
print(combined)  #
```

#### 🔸 **Toán tử `*` (Lặp lại danh sách)**
```python
pattern =
repeated = pattern * 3
print(repeated)  #
```

---

## 2. Danh sách 2D (2D List)

### 2.1 Động lực và ví dụ thực tế
Danh sách 2D (hay ma trận) hữu ích khi cần lưu trữ dữ liệu có cấu trúc bảng, như:

- **Lớp học:** Lưu điểm của học sinh theo từng môn.
- **Bàn cờ:** Trạng thái các ô trên bàn cờ vua, cờ caro.
- **Hình ảnh:** Pixel của ảnh đen trắng hoặc ảnh màu.
- **Bảng tính:** Dữ liệu dạng hàng và cột.

### 2.2 Hiểu về chỉ mục hàng và cột
Trong danh sách 2D, mỗi phần tử được truy cập bằng hai chỉ mục: `matrix[hàng][cột]`.

```python
# Ma trận 3x3 đại diện cho bàn cờ tic-tac-toe
board = [
    ['X', 'O', 'X'],  # Hàng 0
    ['O', 'X', 'O'],  # Hàng 1
    ['X', 'O', 'X']   # Hàng 2
]
#   Cột 0, 1, 2

# Truy cập phần tử tại hàng 1, cột 2
print(board)  # 'O'
```

### 2.3 Tạo danh sách 2D

#### 🔸 **Cách 1: Khởi tạo trực tiếp**
```python
# Ma trận 2x3
matrix = [
   ,
   
]
```

#### 🔸 **Cách 2: Sử dụng List Comprehension (Khuyên dùng)**
Đây là cách tạo ma trận nhanh và gọn gàng nhất.
```python
# Tạo ma trận 3x4 với tất cả phần tử là 0
rows, cols = 3, 4
matrix = [[0 for j in range(cols)] for i in range(rows)]
print(matrix)
# [,,]
```

#### 🔸 **Cách 3: Sử dụng vòng lặp**
Cách này rõ ràng và dễ hiểu cho người mới bắt đầu.
```python
# Tạo bảng cửu chương 3x5
multiplication_table = []
for i in range(1, 4):  # 3 hàng
    row = []
    for j in range(1, 6):  # 5 cột
        row.append(i * j)
    multiplication_table.append(row)

print(multiplication_table)
```

# Hướng dẫn Python Lists - Danh sách trong Python

## 2.4 Truy cập và cập nhật phần tử

```python
# Điểm số của 3 học sinh, 4 môn học
scores = [
    [85, 92, 78, 88],  # Học sinh 1
    [90, 87, 85, 91],  # Học sinh 2
    [82, 89, 92, 86]   # Học sinh 3
]

# Truy cập điểm môn thứ 2 của học sinh thứ 1
print(scores[0][1])  # 92

# Cập nhật điểm môn cuối của học sinh thứ 3
scores[2][3] = 95
print(scores[2][3])  # 95

# Lấy tất cả điểm của học sinh thứ 2
print(scores[1])  # [90, 87, 85, 91]
```

## 2.5 Lặp qua ma trận 2D

#### 🔸 **Lặp qua tất cả phần tử**

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Cách 1: Sử dụng vòng lặp lồng nhau với chỉ mục
for i in range(len(matrix)):
    for j in range(len(matrix[i])):
        print(f"matrix[{i}][{j}] = {matrix[i][j]}")

# Cách 2: Lặp trực tiếp qua giá trị
for row in matrix:
    for element in row:
        print(element, end=" ")
    print()  # Xuống dòng sau mỗi hàng
```

#### 🔸 **Lặp qua từng hàng**

```python
for i, row in enumerate(matrix):
    print(f"Hàng {i}: {row}")
```

## 2.6 Tích Hadamard (Hadamard Product)

Tích Hadamard là phép nhân từng phần tử tương ứng của hai ma trận cùng kích thước:

```python
# Hai ma trận 2x3
matrix_a = [
    [1, 2, 3],
    [4, 5, 6]
]

matrix_b = [
    [2, 3, 1],
    [1, 2, 3]
]

# Tính tích Hadamard
hadamard_product = []
for i in range(len(matrix_a)):
    row = []
    for j in range(len(matrix_a[i])):
        row.append(matrix_a[i][j] * matrix_b[i][j])
    hadamard_product.append(row)

print(hadamard_product)
# [[2, 6, 3], [4, 10, 18]]
```

## 3. Thuật toán trên Danh sách

## 3.1 Tìm kiếm tuyến tính (Linear Search)

Tìm kiếm tuyến tính duyệt qua từng phần tử để tìm giá trị cần tìm:

```python
def linear_search(arr, target):
    """Tìm kiếm tuyến tính và trả về chỉ mục"""
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # Trả về chỉ mục khi tìm thấy
    return -1  # Trả về -1 nếu không tìm thấy

# Ví dụ sử dụng
numbers = [64, 34, 25, 12, 22, 11, 90]
target = 22
result = linear_search(numbers, target)

if result != -1:
    print(f"Tìm thấy {target} tại vị trí {result}")
else:
    print(f"Không tìm thấy {target}")
```

## 3.2 Sắp xếp sử dụng min(), remove(), append()

Thuật toán sắp xếp đơn giản bằng cách tìm phần tử nhỏ nhất và di chuyển:

```python
def selection_sort_basic(arr):
    """Sắp xếp chọn cơ bản"""
    sorted_list = []
    temp_list = arr.copy()  # Tạo bản sao để không làm thay đổi danh sách gốc
    
    while temp_list:
        min_value = min(temp_list)  # Tìm giá trị nhỏ nhất
        temp_list.remove(min_value)  # Xóa giá trị nhỏ nhất
        sorted_list.append(min_value)  # Thêm vào danh sách đã sắp xếp
    
    return sorted_list

# Ví dụ sử dụng
numbers = [64, 34, 25, 12, 22, 11, 90]
sorted_numbers = selection_sort_basic(numbers)
print(f"Danh sách gốc: {numbers}")
print(f"Danh sách đã sắp xếp: {sorted_numbers}")
```

## 3.3 Bài toán "Tổng các số chẵn"

```python
def sum_even_numbers(arr):
    """Tính tổng các số chẵn trong danh sách"""
    total = 0
    for num in arr:
        if num % 2 == 0:  # Kiểm tra số chẵn
            total += num
    return total

# Ví dụ sử dụng
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_sum = sum_even_numbers(numbers)
print(f"Tổng các số chẵn: {even_sum}")  # 30 (2+4+6+8+10)
```

## 3.4 Bài toán "Two Sum"

Tìm hai số trong danh sách có tổng bằng giá trị cho trước:

```python
def two_sum(arr, target):
    """Tìm hai số có tổng bằng target"""
    for i in range(len(arr)):
        for j in range(i + 1, len(arr)):
            if arr[i] + arr[j] == target:
                return [i, j]  # Trả về chỉ mục của hai số
    return None  # Không tìm thấy

# Ví dụ sử dụng
numbers = [2, 7, 11, 15]
target = 9
result = two_sum(numbers, target)

if result:
    print(f"Hai số tại vị trí {result[0]} và {result[1]} có tổng bằng {target}")
    print(f"Hai số đó là: {numbers[result[0]]} và {numbers[result[1]]}")
else:
    print("Không tìm thấy hai số có tổng bằng target")
```

## 3.5 List Comprehension

List comprehension là cách viết ngắn gọn để tạo danh sách mới:

```python
# Cú pháp cơ bản: [expression for item in iterable if condition]

# Ví dụ 1: Bình phương các số
numbers = [1, 2, 3, 4, 5]
squares = [x**2 for x in numbers]
print(squares)  # [1, 4, 9, 16, 25]

# Ví dụ 2: Lọc số chẵn
even_numbers = [x for x in numbers if x % 2 == 0]
print(even_numbers)  # [2, 4]

# Ví dụ 3: Chuyển đổi chuỗi thành chữ hoa
words = ["hello", "world", "python"]
upper_words = [word.upper() for word in words]
print(upper_words)  # ['HELLO', 'WORLD', 'PYTHON']

# Ví dụ 4: Tạo ma trận 2D
matrix = [[i*j for j in range(1, 4)] for i in range(1, 4)]
print(matrix)  # [[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

## 3.6 Tính chất có thể thay đổi (Mutable) vs không thể thay đổi (Immutable)

Danh sách trong Python là mutable (có thể thay đổi):

```python
# Danh sách có thể thay đổi
original_list = [1, 2, 3]
modified_list = original_list  # Cùng tham chiếu
modified_list.append(4)

print(original_list)    # [1, 2, 3, 4] - Bị thay đổi!
print(modified_list)    # [1, 2, 3, 4]

# So sánh với tuple (immutable)
original_tuple = (1, 2, 3)
# original_tuple.append(4)  # Lỗi! Tuple không thể thay đổi

# Cách tạo bản sao độc lập
original_list = [1, 2, 3]
independent_copy = original_list.copy()  # hoặc original_list[:]
independent_copy.append(4)

print(original_list)      # [1, 2, 3] - Không thay đổi
print(independent_copy)   # [1, 2, 3, 4]
```

## 4. Hàm dựng sẵn cho Danh sách

## 4.1 len() - Trả về số lượng phần tử

```python
fruits = ["táo", "cam", "chuối", "xoài"]
print(len(fruits))  # 4

# Với danh sách 2D
matrix = [[1, 2, 3], [4, 5, 6]]
print(len(matrix))     # 2 (số hàng)
print(len(matrix[0]))  # 3 (số cột trong hàng đầu tiên)
```

## 4.2 min() và max() - Giá trị nhỏ nhất và lớn nhất

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]
print(min(numbers))  # 1
print(max(numbers))  # 9

# Với chuỗi (so sánh theo thứ tự alphabet)
fruits = ["táo", "cam", "chuối", "xoài"]
print(min(fruits))  # "cam"
print(max(fruits))  # "xoài"
```

## 4.3 sum() - Tính tổng tất cả phần tử

```python
numbers = [1, 2, 3, 4, 5]
total = sum(numbers)
print(total)  # 15

# Với giá trị khởi tạo
total_with_start = sum(numbers, 10)  # 10 + 1 + 2 + 3 + 4 + 5
print(total_with_start)  # 25

# Tính tổng từng hàng trong ma trận 2D
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
row_sums = [sum(row) for row in matrix]
print(row_sums)  # [6, 15, 24]
```

## 4.4 sorted() - Trả về danh sách mới đã sắp xếp

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]
sorted_numbers = sorted(numbers)
print(numbers)         # [3, 1, 4, 1, 5, 9, 2, 6] - Không thay đổi
print(sorted_numbers)  # [1, 1, 2, 3, 4, 5, 6, 9] - Danh sách mới

# Sắp xếp giảm dần
sorted_desc = sorted(numbers, reverse=True)
print(sorted_desc)  # [9, 6, 5, 4, 3, 2, 1, 1]

# Sắp xếp chuỗi theo độ dài
words = ["python", "java", "c", "javascript"]
sorted_by_length = sorted(words, key=len)
print(sorted_by_length)  # ['c', 'java', 'python', 'javascript']
```

## 4.5 zip() - Kết hợp các phần tử tương ứng

```python
# Kết hợp hai danh sách
names = ["An", "Bình", "Chi"]
ages = [25, 30, 28]
combined = list(zip(names, ages))
print(combined)  # [('An', 25), ('Bình', 30), ('Chi', 28)]

# Kết hợp ba danh sách
scores = [85, 90, 88]
info = list(zip(names, ages, scores))
print(info)  # [('An', 25, 85), ('Bình', 30, 90), ('Chi', 28, 88)]

# Tách lại các danh sách
names_back, ages_back = zip(*combined)
print(list(names_back))  # ['An', 'Bình', 'Chi']
print(list(ages_back))   # [25, 30, 28]
```

## 4.6 reversed() - Trả về iterator đảo ngược

```python
numbers = [1, 2, 3, 4, 5]
reversed_iter = reversed(numbers)
reversed_list = list(reversed_iter)

print(numbers)        # [1, 2, 3, 4, 5] - Không thay đổi
print(reversed_list)  # [5, 4, 3, 2, 1]

# Sử dụng trong vòng lặp
for num in reversed(numbers):
    print(num, end=" ")  # 5 4 3 2 1
```

## 4.7 enumerate() - Thêm chỉ mục vào iterable

```python
fruits = ["táo", "cam", "chuối", "xoài"]

# enumerate trả về các tuple (index, value)
enumerated = list(enumerate(fruits))
print(enumerated)  # [(0, 'táo'), (1, 'cam'), (2, 'chuối'), (3, 'xoài')]

# Sử dụng trong vòng lặp
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")

# Bắt đầu đếm từ số khác 0
for index, fruit in enumerate(fruits, start=1):
    print(f"{index}. {fruit}")
```

## 4.8 Kết hợp các hàm dựng sẵn

```python
# Ví dụ: Tìm học sinh có điểm cao nhất
students = ["An", "Bình", "Chi", "Dũng"]
scores = [85, 92, 78, 90]

# Tìm điểm cao nhất và vị trí
max_score = max(scores)
max_index = scores.index(max_score)
best_student = students[max_index]

print(f"Học sinh xuất sắc nhất: {best_student} với {max_score} điểm")

# Cách khác sử dụng zip và max với key
student_scores = list(zip(students, scores))
best_pair = max(student_scores, key=lambda x: x[1])
print(f"Học sinh xuất sắc nhất: {best_pair[0]} với {best_pair[1]} điểm")

# Thống kê tổng quan
print(f"Tổng số học sinh: {len(students)}")
print(f"Điểm trung bình: {sum(scores) / len(scores):.2f}")
print(f"Điểm thấp nhất: {min(scores)}")
print(f"Điểm cao nhất: {max(scores)}")
```

## Bài tập thực hành

### Bài tập 1: Quản lý danh sách học sinh

```python
# Tạo danh sách học sinh và điểm số
students = ["Nguyễn Văn An", "Trần Thị Bình", "Lê Văn Chi", "Phạm Thị Dung"]
math_scores = [85, 92, 78, 88]
english_scores = [90, 87, 85, 91]

# Yêu cầu:
# 1. Tính điểm trung bình của mỗi học sinh
# 2. Tìm học sinh có điểm trung bình cao nhất
# 3. Thêm một học sinh mới với điểm số
# 4. Sắp xếp học sinh theo điểm trung bình

# Gợi ý giải:
average_scores = []
for i in range(len(students)):
    avg = (math_scores[i] + english_scores[i]) / 2
    average_scores.append(avg)

print("Điểm trung bình của từng học sinh:")
for student, avg in zip(students, average_scores):
    print(f"{student}: {avg}")
```

### Bài tập 2: Ma trận và phép toán

```python
# Tạo ma trận 3x3 đại diện cho bàn cờ tic-tac-toe
board = [
    [' ', ' ', ' '],
    [' ', ' ', ' '],
    [' ', ' ', ' ']
]

# Yêu cầu:
# 1. Tạo hàm hiển thị bàn cờ
# 2. Tạo hàm đánh dấu X hoặc O tại vị trí cụ thể
# 3. Kiểm tra có người thắng không

def display_board(board):
    for i, row in enumerate(board):
        print(" | ".join(row))
        if i < len(board) - 1:
            print("---------")

def make_move(board, row, col, player):
    if board[row][col] == ' ':
        board[row][col] = player
        return True
    return False
```

### Bài tập 3: Thuật toán tìm kiếm và sắp xếp

```python
# Danh sách số ngẫu nhiên
import random
numbers = [random.randint(1, 100) for _ in range(10)]

# Yêu cầu:
# 1. Tìm tất cả số chẵn
# 2. Tìm số lớn thứ hai
# 3. Đếm số lần xuất hiện của mỗi số
# 4. Tạo histogram đơn giản

even_numbers = [num for num in numbers if num % 2 == 0]
sorted_unique = sorted(set(numbers), reverse=True)
second_largest = sorted_unique[1] if len(sorted_unique) > 1 else None

# Đếm tần suất
frequency = {}
for num in numbers:
    frequency[num] = frequency.get(num, 0) + 1
```

## Ứng dụng thực tế

### 1. Xử lý dữ liệu bán hàng

```python
# Dữ liệu bán hàng theo tháng
months = ["T1", "T2", "T3", "T4", "T5", "T6"]
sales = [1200, 1350, 1100, 1450, 1600, 1400]

# Phân tích xu hướng
total_sales = sum(sales)
average_monthly = total_sales / len(sales)
best_month_index = sales.index(max(sales))
worst_month_index = sales.index(min(sales))

print(f"Tổng doanh thu: {total_sales:,} VNĐ")
print(f"Trung bình tháng: {average_monthly:,.0f} VNĐ")
print(f"Tháng bán chạy nhất: {months[best_month_index]} ({sales[best_month_index]:,} VNĐ)")
print(f"Tháng bán ít nhất: {months[worst_month_index]} ({sales[worst_month_index]:,} VNĐ)")

# Tính tỷ lệ tăng trưởng
growth_rates = []
for i in range(1, len(sales)):
    growth = ((sales[i] - sales[i-1]) / sales[i-1]) * 100
    growth_rates.append(growth)
    print(f"Tăng trưởng {months[i-1]} -> {months[i]}: {growth:.1f}%")
```

### 2. Quản lý thư viện sách

```python
# Cấu trúc dữ liệu sách
books = [
    ["Tắt đèn", "Ngô Tất Tố", 1939, "Văn học"],
    ["Số đỏ", "Vũ Trọng Phụng", 1936, "Văn học"],
    ["Dế Mèn phiêu lưu ký", "Tô Hoài", 1941, "Thiếu nhi"],
    ["Lão Hạc", "Nam Cao", 1943, "Văn học"]
]

# Các chức năng quản lý
def search_by_author(books, author_name):
    """Tìm sách theo tác giả"""
    result = []
    for book in books:
        if author_name.lower() in book[1].lower():
            result.append(book)
    return result

def filter_by_genre(books, genre):
    """Lọc sách theo thể loại"""
    return [book for book in books if book[3] == genre]

def sort_by_year(books):
    """Sắp xếp sách theo năm xuất bản"""
    return sorted(books, key=lambda book: book[2])

# Sử dụng
literature_books = filter_by_genre(books, "Văn học")
sorted_books = sort_by_year(books)
nam_cao_books = search_by_author(books, "Nam Cao")
```

### 3. Phân tích điểm thi

```python
# Dữ liệu điểm thi của lớp (môn Toán, Lý, Hóa)
class_scores = [
    ["Nguyễn An", [8.5, 7.0, 8.0]],
    ["Trần Bình", [9.0, 8.5, 7.5]],
    ["Lê Chi", [7.5, 8.0, 9.0]],
    ["Phạm Dung", [8.0, 7.5, 8.5]],
    ["Hoàng Minh", [9.5, 9.0, 8.0]]
]

def calculate_statistics(class_scores):
    """Tính toán thống kê điểm số"""
    subjects = ["Toán", "Lý", "Hóa"]
    
    # Điểm trung bình mỗi môn
    subject_averages = []
    for subject_index in range(3):
        total = sum(student[1][subject_index] for student in class_scores)
        average = total / len(class_scores)
        subject_averages.append(average)
    
    # Điểm trung bình mỗi học sinh
    student_averages = []
    for student in class_scores:
        avg = sum(student[1]) / len(student[1])
        student_averages.append([student[0], avg])
    
    # Học sinh xuất sắc (điểm TB >= 8.5)
    excellent_students = [s for s in student_averages if s[1] >= 8.5]
    
    return {
        'subject_averages': list(zip(subjects, subject_averages)),
        'student_averages': student_averages,
        'excellent_students': excellent_students
    }

# Phân tích kết quả
stats = calculate_statistics(class_scores)
print("Điểm trung bình từng môn:")
for subject, avg in stats['subject_averages']:
    print(f"  {subject}: {avg:.2f}")

print("\nHọc sinh xuất sắc:")
for name, avg in stats['excellent_students']:
    print(f"  {name}: {avg:.2f}")
```

## Mẹo và thủ thuật nâng cao

### 1. Sử dụng enumerate thông minh

```python
# Tìm tất cả vị trí của một phần tử
def find_all_indices(lst, target):
    return [i for i, x in enumerate(lst) if x == target]

numbers = [1, 3, 2, 3, 4, 3, 5]
indices_of_3 = find_all_indices(numbers, 3)
print(indices_of_3)  # [1, 3, 5]
```

### 2. List comprehension với điều kiện phức tạp

```python
# Lọc và biến đổi đồng thời
numbers = [-5, -2, 0, 3, 8, -1, 6]
positive_squares = [x**2 for x in numbers if x > 0]
print(positive_squares)  # [9, 64, 36]

# Nested list comprehension
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened = [item for row in matrix for item in row]
print(flattened)  # [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

#### 🔸 **Sử dụng zip cho nhiều mục đích**

```python
# Transpose ma trận
matrix = [[1, 2, 3], [4, 5, 6]]
transposed = list(zip(*matrix))
print(transposed)  # [(1, 4), (2, 5), (3, 6)]

# So sánh hai danh sách
list1 = [1, 2, 3, 4]
list2 = [1, 2, 5, 4]
differences = [(a, b) for a, b in zip(list1, list2) if a != b]
print(differences)  # [(3, 5)]
```

#### 🔸 **Xử lý danh sách lớn hiệu quả**

```python
# Sử dụng generator expression thay vì list comprehension cho dữ liệu lớn
large_numbers = range(1000000)
sum_of_squares = sum(x**2 for x in large_numbers if x % 2 == 0)
# Tiết kiệm bộ nhớ hơn so với tạo list trung gian
```

#### 🔸 **Xử lý lỗi khi làm việc với danh sách**

```python
def safe_get_item(lst, index, default=None):
    """Lấy phần tử an toàn, không gây lỗi IndexError"""
    try:
        return lst[index]
    except IndexError:
        return default

def safe_remove(lst, item):
    """Xóa phần tử an toàn, không gây lỗi ValueError"""
    try:
        lst.remove(item)
        return True
    except ValueError:
        return False

# Sử dụng
my_list = [1, 2, 3]
print(safe_get_item(my_list, 10, "Không tồn tại"))  # "Không tồn tại"
print(safe_remove(my_list, 5))  # False
```

## Tối ưu hóa hiệu suất

#### 🔸 **1. So sánh hiệu suất các phương pháp xử lý danh sách**

```python
import time

# Tạo danh sách lớn
large_list = list(range(100000))

# Phương pháp 1: List comprehension
start = time.time()
squares1 = [x**2 for x in large_list]
time1 = time.time() - start

# Phương pháp 2: Vòng lặp for thông thường
start = time.time()
squares2 = []
for x in large_list:
    squares2.append(x**2)
time2 = time.time() - start

# Phương pháp 3: map()
start = time.time()
squares3 = list(map(lambda x: x**2, large_list))
time3 = time.time() - start

print(f"List comprehension: {time1:.4f}s")
print(f"For loop: {time2:.4f}s")
print(f"Map: {time3:.4f}s")

```
#### 🔸 **2. Mẹo tối ưu bộ nhớ**
```python
# Sử dụng generator thay vì list cho dữ liệu lớn
def fibonacci_generator(n):
    """Generator cho dãy Fibonacci"""
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Thay vì tạo list lớn
# fib_list = [fibonacci(i) for i in range(1000)]

# Sử dụng generator
fib_gen = fibonacci_generator(1000)
for i, fib in enumerate(fib_gen):
    if i < 10:  # In 10 số đầu
        print(fib, end=" ")
    else:
        break
```
### Kết luận
Danh sách (List) là một cấu trúc dữ liệu mạnh mẽ và linh hoạt trong Python. Từ các thao tác cơ bản như thêm, xóa, sửa đổi phần tử, đến các ứng dụng phức tạp như xử lý ma trận 2D và triển khai thuật toán, danh sách cung cấp nền tảng vững chắc cho việc lập trình Python. \
Các điểm quan trọng cần nhớ: \
  🔸Đặc tính của danh sách: Có thứ tự, có thể trùng lặp, có thể truy cập bằng chỉ mục, và đa dạng kiểu dữ liệu \
  🔸Các phương thức quan trọng: append(), insert(), remove(), pop(), sort(), reverse() \
  🔸Slicing: Công cụ mạnh mẽ để truy cập và thao tác với các phần của danh sách \
  🔸List comprehension: Cách viết ngắn gọn và hiệu quả để tạo danh sách mới \
  🔸Hàm dựng sẵn: len(), min(), max(), sum(), sorted(), zip(), enumerate() \
  🔸Danh sách 2D: Mở rộng khả năng xử lý dữ liệu dạng bảng và ma trận \
Việc thành thạo các khái niệm này sẽ giúp bạn xây dựng các chương trình Python hiệu quả, dễ đọc và dễ bảo trì. Hãy thực hành thường xuyên với các bài tập và ứng dụng thực tế để củng cố kiến thức! 

---
# Tuple, Set, Dictionary trong Python

Trong Python, việc chọn đúng kiểu dữ liệu là bước quan trọng giúc chúng ta thiết kế chương trình dễ đọc, bảo trì và tối ưu về hiệu năng. Ba cấu trúc phổ biến nhất trong Python – Tuple, Set và Dictionary – đều có những tính chất riêng và ứng dụng đặc thùng trong Trí tuệ nhân tạo (AI).

## 1. Tuple - Bộ dữ liệu bất biến, truy cập nhanh
### Tính chất:

- Immutable: không thể thay đổi sau khi tạo.
- Ordered: bảo toàn thứ tự.
- Hợp với việc lưu dữ liệu đồng nhất như toạ độ, vector.

Cú pháp:
```python
my_tuple =("AIO205", 2025, True)
```

Ngoài ra, Tuple còn thường dược được dùng ứng dụng để tính IoU (Intersection over Union) trong thị giác máy tính:
IoU dùng Tuple để biểu diễn tọa độ trong bounding box (x_min, y_min, x_max, y_max):
```python

def calculate_iou(box1, box2):
    xA = max(box1[0], box2[0])
    yA = max(box1[1], box2[1])
    xB = min(box1[2], box2[2])
    yB = min(box1[3], box2[3])
    
    inter_area = max(0, xB - xA) * max(0, yB - yA)
    box1_area = (box1[2] - box1[0]) * (box1[3] - box1[1])
    box2_area = (box2[2] - box2[0]) * (box2[3] - box2[1])
    union_area = box1_area + box2_area - inter_area
    
    return inter_area / union_area

```

## 2. Set - Bộ tập không trùng lặp, linh hoạt trong phân tích ngôn ngữ

### Tính chất:
- Không có thứ tự (Unordered).
- Không chứa phần tử trùng lặp.
- Có thể thao tác toán học (giao, hợp, hiệu).
  
```python
my_set = {"AIO", "ML", "DL"}
```

Ứng dụng: Biểu diễn văn bản trong Text Classification
Sử dụng Set để xây dựng từ điển từ corpus:

```python
corpus = ["we are learning AI", "AI is a CS topic"]
vocab = set()

for sentence in corpus:
    for word in sentence.lower().split():
        vocab.add(word)

print("Vocabulary:", vocab)

###Output: Vocabulary: {'we', 'ai', 'cs', 'learning', 'topic', 'are', 'is'}
```

## 3. Dictionary  Ánh xạ khóa-giá trị mạnh mẽ
###Tính chất:

- Có dạng key: value
- Truy xuất nhanh, phù hợp với dữ liệu dạng ánh xạ.

```
my_dict = {"AI": 95, "ML": 90}
```
Ứng dụng: Tính histogram ảnh trong thị giác máy tính

```python
def compute_histogram(image_matrix):
    histogram = {}
    for row in image_matrix:
        for pixel in row:
            histogram[pixel] = histogram.get(pixel, 0) + 1
    return histogram

image = [
    [255, 0, 255],
    [0, 0, 255],
    [255, 255, 0]
]

print(compute_histogram(image))
###Output:
{255: 5, 0: 4}
```

Ứng dụng mở rộng: Non-Maximum Suppression (NMS)
Trong thuật toán NMS, Tuple dùng để biểu diễn bounding boxes, List để chứa danh sách, còn IoU (sử dụng Tuple) quyết định việc loại bỏ box nào:
```python
def nms(boxes, scores, iou_thresh):
    indices = sorted(range(len(scores)), key=lambda i: scores[i], reverse=True)
    keep = []

    while indices:
        current = indices.pop(0)
        keep.append(current)
        indices = [
            i for i in indices
            if calculate_iou(boxes[current], boxes[i]) < iou_thresh
        ]
    return keep
```

### Kết luận

- Việc nắm vững và sử dụng thành thạo Tuple, Set, Dictionary là nền tảng quan trọng cho bất kỳ ai theo học Python và AI. Bạn có thể tối ưu hoá hiệu suất, tổ chức dữ liệu tốt hơn và giãi quyết bài toán nhanh chóng.
---
# Cơ sở dữ liệu và SQL

## 1. Tổng quan về SQL trong phân tích dữ liệu

SQL (Structured Query Language) là ngôn ngữ truy vấn có cấu trúc được sử dụng phổ biến để quản lý và truy vấn dữ liệu trong các hệ quản trị cơ sở dữ liệu quan hệ (RDBMS). Trong bối cảnh phân tích dữ liệu, SQL đóng vai trò là công cụ cốt lõi giúp kết xuất thông tin từ kho dữ liệu lớn một cách hiệu quả. SQL được thiết kế để xử lý lượng dữ liệu khổng lồ với hiệu suất cao; các hệ quản trị phổ biến như MySQL, PostgreSQL, SQL Server, cũng như các hệ thống dữ liệu lớn như Hadoop hay Spark SQL, đều cho phép truy vấn hàng triệu thậm chí hàng tỷ bản ghi chỉ trong tích tắc. Tính chất **mệnh lệnh tuyên bố (declarative)** của SQL cho phép người dùng chỉ định **kết quả mong muốn** mà không cần mô tả chi tiết cách thực hiện, giúp tối ưu hóa quá trình truy vấn và phân tích.

SQL cung cấp các lệnh truy vấn linh hoạt như `SELECT`, `JOIN`, `GROUP BY`, `HAVING`, `ORDER BY`, v.v., giúp lọc, kết hợp và tổng hợp dữ liệu theo nhiều tiêu chí khác nhau. Ví dụ, câu lệnh đơn giản sau truy vấn tên và điểm của các sinh viên có điểm lớn hơn 8.0 trong bảng `SinhVien`:

```sql
SELECT MaSV, HoTen, Diem
FROM SinhVien
WHERE Diem > 8.0;
```

Thông qua những lệnh này, chuyên gia dữ liệu có thể xây dựng các báo cáo, thống kê và mô hình phân tích để hỗ trợ ra quyết định. Thêm nữa, SQL còn tích hợp tốt với các công cụ phân tích dữ liệu và BI (Business Intelligence) như Tableau, Power BI hay các ngôn ngữ lập trình như Python, giúp kết nối và chuyển tiếp dữ liệu liền mạch. Nhờ cộng đồng người dùng lớn và các tính năng tối ưu hóa (chỉ mục, phân vùng, bộ nhớ trong), SQL ngày càng trở thành công cụ không thể thiếu trong xử lý và phân tích dữ liệu lớn.

## 2. Entity Relationship Diagram (ERD)

Sơ đồ quan hệ thực thể (Entity-Relationship Diagram – ERD) là biểu đồ trực quan mô tả cấu trúc và mối liên hệ của dữ liệu trong hệ thống. ERD minh họa cách các **thực thể** (entity) – các đối tượng như người, sản phẩm hay khái niệm – tương tác với nhau qua các **mối quan hệ** (relationship). Thực thể thường được biểu diễn bằng hình chữ nhật, thuộc tính của thực thể (attributes) bằng hình bầu dục, và mối quan hệ giữa các thực thể bằng hình thoi kết nối chúng. Ví dụ, trong hệ thống quản lý bán hàng, có thể có các thực thể “Khách hàng”, “Đơn hàng”, “Sản phẩm” kết nối qua các mối quan hệ “Đặt” hoặc “Chứa” để phản ánh cấu trúc dữ liệu của quy trình bán hàng.

### Các thành phần chính của ERD bao gồm:
*   **🔸Thực thể (Entity):** Là đối tượng hoặc khái niệm cụ thể trong thế giới thực, có tập các thuộc tính đặc trưng. Mỗi thực thể phải có ít nhất một thuộc tính định danh duy nhất (khóa chính) để phân biệt. Ví dụ: thực thể “Nhân viên” với các thuộc tính MÃNV, Họ tên, Ngày sinh.
*   **🔸Thuộc tính (Attribute):** Là đặc trưng của thực thể. Ví dụ, thực thể “Nhân viên” có thể có thuộc tính HoTen, NgaySinh, DiaChi. Một thuộc tính có thể là đơn trị hoặc phức hợp, nhưng trong ERD thường biểu diễn ở mức giá trị đơn.
*   **🔸Khóa chính (Primary Key):** Là thuộc tính (hoặc tổ hợp thuộc tính) định danh duy nhất từng bản ghi trong một tập thực thể.
*   **🔸Khóa ngoại (Foreign Key):** Là thuộc tính trong một thực thể tham chiếu đến khóa chính của thực thể khác, tạo ra liên kết giữa hai bảng khi thiết kế cơ sở dữ liệu.
*   **🔸Mối quan hệ (Relationship):** Là sự liên kết giữa hai hoặc nhiều tập thực thể. Mỗi mối quan hệ được biểu diễn bằng đường nối với ký hiệu phản ánh tính chất của liên kết.

Trong ERD, người thiết kế cũng xác định **độ đa (cardinality)** của mỗi quan hệ, tức là số lượng bản ghi liên quan giữa hai thực thể:
*   **🔸Quan hệ 1-1 (One-to-One):** Mỗi bản ghi của thực thể thứ nhất liên kết với đúng một bản ghi của thực thể thứ hai, và ngược lại. Ví dụ: mỗi người có một số CMND duy nhất và mỗi CMND chỉ thuộc về một người.
*   **🔸Quan hệ 1-N (One-to-Many):** Một bản ghi của thực thể thứ nhất có thể liên kết với nhiều bản ghi của thực thể thứ hai, nhưng mỗi bản ghi ở thực thể thứ hai chỉ liên kết với một bản ghi ở thực thể thứ nhất. Ví dụ: một phòng ban (Department) có nhiều nhân viên (Employee), nhưng mỗi nhân viên chỉ thuộc một phòng ban.
*   **🔸Quan hệ N-N (Many-to-Many):** Nhiều bản ghi ở thực thể thứ nhất có thể liên kết với nhiều bản ghi ở thực thể thứ hai. Ví dụ: sinh viên và môn học có quan hệ nhiều-nhiều, vì một sinh viên có thể đăng ký nhiều môn, và một môn học có thể có nhiều sinh viên. Thông thường, quan hệ N-N sẽ được chia thành hai quan hệ 1-N với một bảng trung gian chứa khóa ngoại.

Trong quá trình thiết kế ERD, cần tuân thủ các quy tắc cơ bản: Xác định đúng thực thể và tập thực thể, gán khóa chính, xác định đầy đủ thuộc tính quan trọng, và vẽ các mối quan hệ kèm theo độ đa chính xác. Ví dụ, trong ERD bán hàng, ta sẽ có thực thể Khách hàng, Đơn hàng, Sản phẩm; mối quan hệ Khách hàng Đặt Đơn hàng (1-N) và Đơn hàng Chứa Sản phẩm (N-N). Sơ đồ ERD như vậy sẽ giúp hình dung cấu trúc logic của cơ sở dữ liệu trước khi triển khai thực tế.

## 3. Chuẩn hóa cơ sở dữ liệu

**Chuẩn hóa cơ sở dữ liệu** là quá trình tổ chức dữ liệu trong các bảng nhằm **giảm thiểu sự dư thừa** và **đảm bảo tính toàn vẹn** của dữ liệu. Mục tiêu của chuẩn hóa là chia dữ liệu thành các bảng nhỏ hơn, mỗi bảng chỉ chứa các thông tin liên quan, đồng thời thiết lập mối quan hệ thông qua các khóa để tránh tình trạng lặp dữ liệu. Việc chuẩn hóa giúp hệ quản trị cơ sở dữ liệu tiết kiệm không gian lưu trữ, giảm thiểu rủi ro khi cập nhật dữ liệu và đơn giản hóa việc bảo trì về lâu dài.

Lý do cần chuẩn hóa bao gồm:
1.  **🔸Loại bỏ trùng lặp dữ liệu** để giảm yêu cầu lưu trữ và tránh dữ liệu không nhất quán;
2.  **🔸Đảm bảo tính toàn vẹn** nhờ mỗi thông tin chỉ xuất hiện ở một nơi duy nhất;
3.  **🔸Đơn giản hóa việc bảo trì** bằng cách giảm quy mô bảng, dễ theo dõi và sửa đổi.
Quá trình chuẩn hóa được chia thành nhiều **dạng chuẩn (Normal Form)** khác nhau. Các dạng chuẩn cơ bản thường gặp bao gồm:

*   **Dạng chuẩn thứ nhất (1NF):** Yêu cầu mỗi ô (cell) trong bảng chỉ chứa một giá trị nguyên tử (không có nhóm giá trị lặp trong cùng một ô) và mỗi bảng có khóa chính.
    *   *Ví dụ:* Thay vì lưu `CourseIDs` là một chuỗi các giá trị ngăn cách bằng dấu phẩy, ta cần tách thành các hàng riêng biệt.

*   **Dạng chuẩn thứ hai (2NF):** Yêu cầu bảng ở 1NF và loại bỏ các **phụ thuộc hàm một phần**. Điều này nghĩa là mọi thuộc tính không phải khóa phải phụ thuộc hoàn toàn vào toàn bộ khóa chính (nếu khóa chính là tổ hợp nhiều cột).
    *   *Ví dụ:* Nếu bảng `DonHang` có khóa chính là `(OrderID, ProductID)` nhưng `ProductName` chỉ phụ thuộc vào `ProductID`, thì cần tách `ProductName` ra bảng `Product` riêng.

*   **Dạng chuẩn thứ ba (3NF):** Yêu cầu bảng ở 2NF và không có **phụ thuộc bắc cầu (transitive dependency)** giữa các cột không phải khóa. Điều này có nghĩa là một thuộc tính không khóa không được phụ thuộc vào một thuộc tính không khóa khác.
    *   *Ví dụ:* Nếu thông tin `Country` phụ thuộc vào `City`, và `City` phụ thuộc vào `KhachHang`, ta phải tách thành hai bảng để tránh phụ thuộc bắc cầu.

*   **Dạng chuẩn Boyce-Codd (BCNF):** Là một dạng chuẩn mở rộng của 3NF, yêu cầu với mọi phụ thuộc hàm, vế trái phải là một siêu khóa. BCNF giải quyết các trường hợp đặc biệt mà 3NF không xử lý đủ.

Quá trình chuyển đổi lên dạng cao hơn thường được thực hiện tuần tự: `1NF` → `2NF` → `3NF` → `BCNF`. Nhìn chung, cơ sở dữ liệu được coi là **chuẩn hóa đầy đủ** khi đạt 3NF, trong đó mỗi thông tin chỉ lưu ở một nơi duy nhất.

## 4. SQL nâng cao

### 4.1. JOIN (INNER, LEFT, RIGHT, FULL)
Các phép nối (`JOIN`) trong SQL cho phép kết hợp dữ liệu từ hai hay nhiều bảng dựa trên một giá trị chung. Có bốn kiểu `JOIN` cơ bản:

*   **🔸INNER JOIN:** Chỉ trả về các hàng có giá trị trùng khớp ở cả hai bảng.
*   **🔸LEFT JOIN (LEFT OUTER JOIN):** Trả về tất cả các hàng từ bảng bên trái (`left table`) và các hàng phù hợp từ bảng bên phải. Nếu không có bản ghi tương ứng ở bảng phải, các cột của bảng phải sẽ có giá trị `NULL`.
*   **🔸RIGHT JOIN (RIGHT OUTER JOIN):** Ngược lại với `LEFT JOIN`, trả về tất cả các hàng từ bảng bên phải và các hàng khớp ở bảng trái.
*   **🔸FULL JOIN (FULL OUTER JOIN):** Trả về tất cả các hàng khi có sự trùng khớp ở một trong hai bảng. Nếu một hàng ở bảng nào đó không có bản ghi tương ứng ở bảng kia, các cột của bảng kia sẽ là `NULL`.

**Ví dụ `INNER JOIN`:**
```sql
SELECT e.name, d.department_name
FROM Employees AS e
INNER JOIN Departments AS d
ON e.deptId = d.id;
```
Kết quả của `INNER JOIN` sẽ chỉ bao gồm những nhân viên có `deptId` trùng với `id` phòng ban.

**Bảng kết quả ví dụ:**
| COURSE_ID | NAME    | AGE |
|:----------|:--------|:----|
| 13        | Davolio | 29  |
| 14        | Fuller  | 35  |

Bảng trên cho thấy `INNER JOIN` giữa hai bảng `Student` và `StudentCourse` dựa trên `ROLL_NO`, chỉ lấy những sinh viên có dữ liệu trong cả hai bảng.

### 4.2. GROUP BY và HAVING
*   **GROUP BY:** Mệnh đề `GROUP BY` được sử dụng để nhóm các bản ghi có cùng giá trị ở một hoặc nhiều cột. Sau khi nhóm, ta thường áp dụng các hàm tổng hợp (`SUM`, `COUNT`, `AVG`, `MIN`, `MAX`,...) lên từng nhóm dữ liệu.

    **Ví dụ:** Đếm số nhân viên trong mỗi phòng ban.
    ```sql
    SELECT Department, COUNT(*) AS NumEmployees
    FROM Employees
    GROUP BY Department;
    ```

*   **HAVING:** Sau khi đã nhóm dữ liệu, nếu muốn lọc các nhóm dựa trên điều kiện liên quan đến kết quả tính toán, ta dùng mệnh đề `HAVING`. Khác với `WHERE` (áp dụng trước khi nhóm), `HAVING` áp dụng **sau khi đã tính các hàm tổng hợp**.

    **Ví dụ:** Tìm các phòng ban có nhiều hơn 10 nhân viên.
    ```sql
    SELECT Department, COUNT(*) AS NumEmployees
    FROM Employees
    GROUP BY Department
    HAVING COUNT(*) > 10;
    ```
    Lưu ý rằng `WHERE` lọc các bản ghi ban đầu, còn `HAVING` lọc các nhóm kết quả. Bạn không thể dùng các hàm tổng hợp trong `WHERE`.

### 4.3. Truy vấn con (Subquery)

**Truy vấn con** là một truy vấn lồng bên trong một truy vấn khác. Subquery có thể nằm trong mệnh đề `SELECT`, `FROM`, `WHERE` hoặc `HAVING` của câu SQL và thường được đóng trong ngoặc. Nó cho phép chúng ta lấy kết quả của một truy vấn để sử dụng như một điều kiện hoặc một bảng tạm.

*   **Trong `WHERE`:** Lọc dữ liệu theo kết quả từ truy vấn khác. Ví dụ, lấy tên sinh viên có điểm vượt trung bình:

    ```sql
    SELECT name
    FROM Students
    WHERE score > (
        SELECT AVG(score) FROM Students
    );
    ```

*   **Trong `FROM`:** Sử dụng subquery như một bảng tạm (đặt nhãn alias) để tham gia `JOIN` hoặc nhóm tiếp.

*   **Trong `SELECT`:** Tính toán cột phụ ở mỗi hàng dựa trên một truy vấn khác.

**Ví dụ khác, truy vấn lồng trong `FROM`:**

```sql
SELECT t.Class, t.AvgScore
FROM (
    SELECT Class, AVG(score) AS AvgScore
    FROM ExamResults
    GROUP BY Class
) AS t
WHERE t.AvgScore > 80;
```
Trong đó, subquery tính điểm trung bình từng lớp, rồi kết quả được lọc ở truy vấn bao ngoài.

### 4.4. CTE và hàm cửa sổ (Window Functions)

**CTE (Common Table Expression)** là cú pháp `WITH` tạo ra một bảng tạm có tên trong phạm vi một truy vấn. CTE giúp chia nhỏ truy vấn phức tạp thành các phần có tên rõ ràng, dễ đọc và tái sử dụng trong cùng một câu lệnh. Ví dụ:

```sql
WITH TopStudents AS (
    SELECT name, score
    FROM Students
    WHERE score > 90
)
SELECT * FROM TopStudents;
```
Đoạn trên định nghĩa CTE `TopStudents` chứa danh sách sinh viên có điểm > 90, sau đó truy vấn CTE này như một bảng thông thường. CTE có thể dùng trong `SELECT`, `INSERT`, `UPDATE`, `DELETE` và được đánh giá trước câu lệnh chính để cải thiện khả năng bảo trì mã.

**Window function (Hàm cửa sổ)** cho phép thực hiện các phép tính trên một tập con (partition) của kết quả, không gộp nhóm dữ liệu như `GROUP BY`. Chúng thường sử dụng cú pháp `OVER (PARTITION BY ... ORDER BY ...)` . Ví dụ, `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()` đánh số thứ tự các hàng trong từng nhóm. Ví dụ:

```sql
SELECT name, class, RANK() OVER (PARTITION BY class ORDER BY score DESC) AS RankInClass
FROM ExamResults;
```
Trong ví dụ trên, mỗi học sinh sẽ nhận thứ hạng dựa trên điểm trong từng lớp (mục `PARTITION BY class`). `ROW_NUMBER()` gán thứ tự duy nhất cho từng hàng, trong khi `RANK()` cho phép hai giá trị bằng điểm sẽ có cùng thứ hạng (và bỏ thứ hạng kế tiếp). Window functions rất hữu ích khi cần phân tích dữ liệu theo từng nhóm con mà vẫn giữ lại mọi hàng trong kết quả.
---
# Git & Github For version control

## 1: Giới thiệu hệ thống quản lý phiên bản và Git

### 1.1. Khái niệm Version Control System (VCS)
**Version Control System** là hệ thống theo dõi và lưu lại các thay đổi của tập tin theo thời gian. VCS giúp ghi lại ai thực hiện thay đổi, thay đổi gì và khi nào.

**Lợi ích:**
- ✅ Khôi phục phiên bản cũ khi có lỗi.
- ✅ So sánh sự khác biệt giữa các phiên bản.
- ✅ Biết rõ ai thay đổi, thay đổi gì và khi nào.
- ✅ Bảo vệ dữ liệu và hỗ trợ làm việc nhóm.

### 1.2. Các loại VCS
Bên cạnh local VCS có 2 loại VCS chính là Centralized VCS (CVCS) và Distributed VCS (DVCS). Mỗi loại VCS đều có đặc trưng riêng biệt.
*   **Centralized VCS (CVCS):** Như Subversion, CVS - dùng máy chủ trung tâm, gặp rủi ro khi server hỏng.
*   **Distributed VCS (DVCS):** Như Git, Mercurial - mỗi người có bản sao đầy đủ, an toàn và linh hoạt hơn.

### 1.3. Lược sử Git
-   **Bối cảnh ra đời (2005):** Do mâu thuẫn về quyền sử dụng giữa nhóm Linux và công cụ BitKeeper.
-   **Người sáng lập:** **Linus Torvalds** tạo ra Git để quản lý mã nguồn Linux.
-   **Mục tiêu thiết kế:** Nhanh, đơn giản, dễ phân nhánh, làm việc phân tán.

### 1.4. Nguyên lý hoạt động của Git
1.  **Snapshot thay vì Diff:** Khác với các hệ thống VCS cũ chỉ lưu các thay đổi, Git lưu "bản chụp" toàn bộ dự án mỗi khi commit. Nếu file không thay đổi, Git chỉ tạo liên kết đến bản chụp cũ, giúp tiết kiệm dung lượng nhưng vẫn nhanh.
2.  **Toàn vẹn dữ liệu với SHA-1:** Git bảo vệ dữ liệu bằng hàm băm SHA-1. Mỗi thứ trong Git đều có mã định danh 40 ký tự. Khi nội dung thay đổi, mã hash cũng thay đổi hoàn toàn, giúp đảm bảo dữ liệu không bị hỏng.
3.  **Nguyên lý "Offline-first":** Git cho phép làm việc mà không cần kết nối mạng. Hầu hết các thao tác như commit, tạo nhánh, gộp nhánh đều thực hiện trên máy tính của bạn. Chỉ khi cần chia sẻ code (push/pull), bạn mới cần Internet.

### 1.5. Cài đặt và cấu hình Git
#### Cài đặt Git
-   **🔸Linux (Debian/Ubuntu):** `sudo apt install git`
-   **🔸Linux (Fedora/RHEL):** `sudo dnf install git`
-   **🔸macOS:** `xcode-select --install` hoặc tải từ [git-scm.com](https://git-scm.com)
-   **🔸Windows:** cài đặt từ [git-scm.com](https://git-scm.com) hoặc `choco install git`

#### Cấu hình cơ bản
Thiết lập thông tin người dùng và các tùy chọn căn bản:
```bash
git config --global user.name "Tên Của Bạn"
git config --global user.email "email@example.com"
git config --global core.editor "code --wait"
git config --global color.ui auto```

#### Thiết lập Alias hữu ích
Tạo lệnh tắt cho các câu lệnh Git thường dùng:
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
```

### 1.6. Hỗ trợ và trợ giúp
-   **Tài liệu chính thức:** Trang web [git-scm.com](https://git-scm.com) cung cấp tài liệu đầy đủ về Git.
-   **Trợ giúp từ dòng lệnh:** Gõ `git help`, `git --help` hoặc `man git-{lệnh}` để xem hướng dẫn.
-   **Cộng đồng hỗ trợ:** Stack Overflow, GitHub Discussions và các diễn đàn Git.
-   **Sách và tài nguyên học tập:** Sách "Pro Git" của Scott Chacon có tại [git-scm.com/book](https://git-scm.com/book).

---

## 2: Quy trình làm việc Git cơ bản

### 2.1. Khởi tạo và Sao chép kho (Repository)
#### Khởi tạo repository mới
Để bắt đầu dùng Git cho dự án mới, tạo repository trong thư mục dự án. Lệnh `git init` sẽ tạo thư mục ẩn `.git/` để Git lưu trữ dữ liệu và theo dõi dự án.
```bash
mkdir <new_project_name>
cd <new_project_name>
git init
```

#### Sao chép repository từ xa
Để làm việc với dự án có sẵn, cần sao chép (clone) repository từ máy chủ về máy tính. Lệnh `git clone` sẽ tải về toàn bộ lịch sử và các nhánh của dự án.
```bash
git clone https://github.com/username/repository.git
git clone git@github.com:username/repository.git

# Clone với tên thư mục khác
git clone https://github.com/username/repository.git <new_name>
```

### 2.2. Theo dõi và Lưu trữ thay đổi
#### Trạng thái file trong Git
Trong Git, mỗi file trong thư mục làm việc thuộc một trong bốn trạng thái:
-   **🔸Untracked:** File mới chưa được Git theo dõi, chưa có trong lần lưu trước.
-   **🔸Modified:** File đã thay đổi so với phiên bản trước, nhưng chưa sẵn sàng để lưu.
-   **🔸Staged:** File đã được đưa vào vùng chuẩn bị, sẵn sàng cho lần lưu tiếp theo.
-   **🔸Committed:** File đã được lưu trữ an toàn trong Git.

#### Thao tác cơ bản
-   Để xem trạng thái hiện tại của các file, dùng lệnh: `git status`
-   Để đưa file vào vùng chuẩn bị (staging area):
    ```bash
    git add ten-file.txt # Thêm một file
    git add .            # Thêm tất cả file đã thay đổi
    ```
-   Để lưu các thay đổi đã chuẩn bị:
    ```bash
    git commit -m "Mô tả ngắn về thay đổi"
    ```

#### Sử dụng `.gitignore`
File `.gitignore` liệt kê các file và thư mục mà Git sẽ bỏ qua, không theo dõi. Thường là:
-   File log và dữ liệu tạm
-   Thư mục build
-   File cấu hình cá nhân (như .env)
-   Thư mục chứa thư viện (node_modules, vendor)

**Ví dụ:**
```
# Bỏ qua thư mục build
/build/

# Bỏ qua tất cả file có đuôi .log
*.log

# Bỏ qua file cấu hình cụ thể
config.ini
.env
```

#### Sơ đồ trạng thái
| Trạng thái | Mô tả | Xuất hiện trong "git status" | Hành động tiếp theo |
|:-----------|:----------------------------------------------------------|:-------------------------------|:--------------------|
| **Untracked** | File mới chưa được Git theo dõi, chưa có trong lần lưu trước. | `Untracked files:` | `git add` |
| **Modified** | File đã thay đổi so với phiên bản trước, nhưng chưa sẵn sàng để lưu. | `Changes not staged for commit:` | `git add` |
| **Staged** | File đã được đưa vào vùng chuẩn bị, sẵn sàng cho lần lưu tiếp theo (commit). | `Changes to be committed:` | `git commit` |
| **Committed** | File đã được ghi lại (commit) trong repository, nằm trong lịch sử Git. | Không hiển thị trong git status | Không cần làm gì thêm |

### 2.3. Xem lịch sử commit
Lệnh `git log` hiển thị lịch sử commit với mã hash, tác giả, thời gian và nội dung.
-   🔸`git log -p`: Hiển thị sự khác biệt của mỗi commit.
-   🔸`git log --stat`: Hiện số file và dòng thay đổi trong mỗi commit.
-   🔸`git log --since="2 weeks ago"`: Lọc commit trong 2 tuần gần đây.
-   🔸`git log --author="Tên"`: Lọc commit theo tên người tạo.
-   🔸`git log --oneline --graph --all`: Hiển thị lịch sử đồ họa ngắn gọn cho tất cả nhánh.

### 2.4. Hoàn tác thay đổi
| Tình huống | Lệnh | Mô tả |
|:-----------------------------|:----------------------------|:-------------------------------------------------|
| Đã sửa file nhưng chưa staged | `git restore <file>` | Khôi phục file về trạng thái của commit trước. |
| Đã staged nhưng muốn bỏ stage | `git restore --staged <file>`| Đưa file từ staged về modified. |
| Muốn sửa commit gần nhất | `git commit --amend` | Sửa message hoặc thêm file vào commit cuối. |
| Muốn hoàn tác commit | `git revert <commit-hash>` | Tạo commit mới để hoàn tác thay đổi. |
| Cần lưu các thay đổi tạm thời | `git stash` / `git stash pop` | Lưu tạm và áp dụng lại thay đổi đã lưu. |

**Lưu ý:** `git reset` có thể quay lại phiên bản trước đó, nhưng hãy cẩn trọng vì lệnh này ảnh hưởng đến lịch sử commit.

### 2.5. Làm việc với remote repository
Remote repository là phiên bản lưu trữ dự án từ xa trên máy chủ như GitHub, GitLab.
-   **Xem danh sách remote:** `git remote -v`
-   **Thêm remote mới:** `git remote add origin https://github.com/username/repository.git`
-   **Đẩy commit lên remote:** `git push origin main`
-   **Kéo thay đổi từ remote về local:** `git pull origin main` (là kết hợp của `fetch` và `merge`). Để kiểm soát chi tiết hơn, dùng:
    ```bash
    git fetch --all
    git merge origin/main
    ```

### 2.6. Tagging – Đánh dấu phiên bản
Tag đánh dấu các điểm quan trọng trong lịch sử repository, thường là các phiên bản phát hành.
-   **Annotated tag (tag đầy đủ):**
    -   Có thông tin người tạo, ngày tạo và message. Được khuyến nghị cho release.
    -   `git tag -a v1.0 -m "Version 1.0 - Phát hành chính thức"`
-   **Lightweight tag (tag nhẹ):**
    -   Là con trỏ đơn giản đến một commit. Thích hợp cho đánh dấu tạm thời.
    -   `git tag v1.0-beta`
-   **Đẩy tag lên remote:**
    ```bash
    # Đẩy tag cụ thể
    git push origin v1.0
    # Đẩy tất cả tag
    git push origin --tags
    ```

---
## 3: Quản lý Nhánh và Lịch sử

### 3.1. Khái niệm Nhánh (Branch)
-   **Nhánh là Con trỏ:** Nhánh trong Git là con trỏ đến một commit cụ thể. Việc tạo và xóa nhánh diễn ra rất nhanh chóng.
-   **Phát triển Song song:** Nhánh tạo môi trường làm việc riêng để phát triển tính năng mới, sửa lỗi, hoặc thử nghiệm mà không ảnh hưởng mã nguồn chính.
-   **Lịch sử Phân nhánh:** Lịch sử Git như một cây với nhiều nhánh phát triển riêng biệt, sau đó được gộp (merge) hoặc tái cơ sở (rebase) tạo lịch sử thống nhất.

### 3.2. Tạo, Chuyển, và Gộp Nhánh
| Bước | Mục đích | Lệnh ví dụ |
|:------|:----------------------|:-----------------------------|
| 1 | **Tạo và chuyển nhánh** | `git checkout -b feature/login` |
| 2 | **Phát triển tính năng** | (code và commit trên nhánh mới) |
| 3 | **Gộp nhánh** | `git checkout main`<br>`git merge feature/login` |
| 4 | **Giải quyết xung đột** | (sửa file) <br>`git add .`<br>`git commit` |

### 3.3. Quản lý Nhánh
-   **Liệt kê nhánh:**
    -   🔸`git branch`: Nhánh local.
    -   🔸`git branch -r`: Nhánh remote-tracking.
    -   🔸`git branch -a`: Tất cả nhánh.
-   **Đổi tên nhánh:** `git branch -m <tên-cũ> <tên-mới>`
-   **Xóa nhánh:**
    -   🔸`git branch -d <tên-nhánh>`: Xóa nhánh đã merge.
    -   🔸`git branch -D <tên-nhánh>`: Ép xóa nhánh chưa merge (cẩn trọng).
    -   🔸`git push origin --delete <tên-nhánh>`: Xóa nhánh trên remote.

### 3.4. Rebase
Rebase là tính năng tạo lịch sử commit gọn gàng và tuyến tính bằng cách "tái áp dụng" các commit từ nhánh hiện tại lên đầu nhánh đích.
-   **Cơ bản:** `git checkout feature-branch` và `git rebase main`.
-   **Tương tác:** `git rebase -i HEAD~3` để "dọn dẹp" lịch sử.
-   **Lưu ý quan trọng:** Không rebase các nhánh đã chia sẻ công khai.

### 3.5. Các workflow & mô hình nhánh phổ biến
-   **🔸GitFlow:** Phù hợp với dự án có chu kỳ phát hành rõ ràng. Sử dụng các nhánh `main`, `develop`, `feature/*`, `release/*`, `hotfix/*`.
-   **🔸GitHub Flow:** Quy trình đơn giản cho triển khai liên tục. `main` -> `nhánh mới` -> `Pull Request` -> `merge` -> `deploy`.
-   **🔸Trunk-based Development:** Công việc diễn ra trực tiếp trên nhánh "trunk" (`main`), phù hợp với DevOps và tích hợp liên tục (CI).

---
## Phần 4: Cộng tác qua GitHub

### 4.1. Thiết lập tài khoản & bảo mật
1.  **Đăng ký tài khoản** tại github.com.
2.  **Thiết lập phương thức xác thực:** Dùng SSH (`ssh-keygen -t ed25519 -C "email@example.com"`) để bảo mật hơn và không cần nhập mật khẩu.
3.  **Tùy chỉnh hồ sơ cá nhân.**
4.  **Bảo mật tài khoản:** Bật xác thực hai yếu tố (2FA).

### 4.2. Quy trình Fork & Pull Request
1.  **Fork repository:** Tạo bản sao của repo về tài khoản GitHub của bạn.
2.  **Clone về máy local:** `git clone https://github.com/username-của-bạn/tên-repository.git`
3.  **Thiết lập upstream remote:** `git remote add upstream https://github.com/owner-gốc/tên-repository.git`
4.  **Tạo nhánh chủ đề:** `git checkout -b tên-nhánh-mới`
5.  **Thực hiện thay đổi và push:** `git add .`, `git commit -m "..."`, `git push origin tên-nhánh-mới`
6.  **Tạo Pull Request:** Truy cập repository gốc, nhấn "New pull request".

### 4.3. Quản lý Repository trên GitHub
-   **Tạo và cấu hình:** Đặt tên, mô tả, thêm collaborator.
-   **Tài liệu:** Cung cấp `README.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`.
-   **Mẫu Issue và Pull Request:** Tạo trong thư mục `.github` để chuẩn hóa thông tin.
-   **Thiết lập branch và bảo vệ:** Kích hoạt bảo vệ nhánh chính trong Settings > Branches để yêu cầu review, CI/CD.

### 4.4. Mẹo làm việc hiệu quả
-   **Sử dụng Draft Pull Request:** Nhận phản hồi sớm về code đang phát triển.
-   **Tạo review checklist:** Đảm bảo chất lượng code nhất quán.
-   **Đồng bộ hóa fork thường xuyên:**
    ```bash
    git fetch upstream
    git checkout main
    git merge upstream/main
    git push origin main
    ```

---
## Phần 5: Tùy chỉnh & Mở rộng Git

### 5.1. Cấu hình nâng cao (`.gitconfig`)
-   **Thiết lập nhánh mặc định:** `git config --global init.defaultBranch main`
-   **Tạo mẫu commit message:** `git config --global commit.template ~/.gitmessage.txt`
-   **Công cụ xử lý merge và diff:** `git config --global merge.tool vscode`
-   **Thiết lập proxy và lưu thông tin đăng nhập.**

### 5.2. Git Attributes (`.gitattributes`)
Quy định cách Git xử lý các loại file khác nhau, ví dụ:
-   Xử lý ký tự xuống dòng (line endings): `* text=auto`
-   Đánh dấu file binary: `*.png binary`
-   Xác định chiến lược merge: `database.xml merge=ours`

### 5.3. Git Hooks – Tự động hóa
Là script tự động chạy tại các thời điểm cụ thể trong quy trình Git (ví dụ: `pre-commit` để kiểm tra code trước khi commit, `post-receive` để kích hoạt CI/CD). Để sử dụng, chỉ cần bỏ đuôi `.sample` từ các file mẫu trong `.git/hooks/` và cấp quyền thực thi (`chmod +x`).

### 5.4. Alias & Scripts
Tạo lệnh tắt phức tạp hơn bằng cách kết hợp nhiều lệnh shell trong `.gitconfig`.
```ini
[alias]
    # Xóa tất cả nhánh đã merge vào nhánh hiện tại
    cleanup = "!git branch --merged | grep -v '\\*' | xargs -n 1 git branch -d"
    # Xem lịch sử với giao diện đẹp
    graph = "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

