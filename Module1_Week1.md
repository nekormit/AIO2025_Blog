# Python 101 For Beginners

## 1. Giới thiệu Python và hệ sinh thái

Python là một ngôn ngữ lập trình phổ biến được thiết kế bởi Guido van Rossum và phát hành lần đầu tiên vào năm 1991. Nó là ngôn ngữ thông dịch, có cú pháp rõ ràng và dễ đọc, đồng thời hỗ trợ các trường phái lập trình khác nhau, bao gồm lập trình hướng đối tượng. Với cú pháp đơn giản và trực quan, Python giúp giảm đáng kể thời gian viết và kiểm thử mã nguồn so với các ngôn ngữ lập trình khác.

Python được ứng dụng rộng rãi trong nhiều lĩnh vực như phân tích dữ liệu, khoa học máy tính, phát triển web, tự động hóa, v.v. do có khả năng xử lý linh hoạt và kho thư viện phong phú.

Python có một cộng đồng lập trình viên lớn và kho thư viện (framework) khổng lồ hỗ trợ. Ví dụ, NumPy và Pandas phục vụ cho tính toán khoa học và phân tích dữ liệu, TensorFlow và PyTorch hỗ trợ học máy (Machine Learning), còn Django và Flask hỗ trợ phát triển ứng dụng web. Nhờ đó, Python trở thành một công cụ mạnh mẽ cho cả người mới học và lập trình viên chuyên nghiệp, được sử dụng rộng rãi trong nghiên cứu, doanh nghiệp và các dự án thương mại trên khắp thế giới.

Python có thể được cài đặt từ trang chủ chính thức (python.org) hoặc thông qua các trình quản lý gói như Anaconda. Người dùng có thể viết code Python trong nhiều môi trường phát triển tích hợp (IDE) khác nhau như Visual Studio Code hoặc môi trường notebook như Jupyter Notebook, Google Colab để viết và chạy mã Python một cách tiện lợi.

Tóm lại: Python ra đời năm 1991 là một ngôn ngữ thông dịch phổ biến, hỗ trợ lập trình hướng đối tượng, với cú pháp đơn giản, thư viện phong phú và cộng đồng lớn. Python được ứng dụng rộng rãi trong phân tích dữ liệu, học máy, phát triển web, tự động hóa...

## 2. Biểu diễn dữ liệu (Data Representation)

Trong Python, biến là vùng nhớ để lưu trữ giá trị. Người dùng không cần khai báo kiểu dữ liệu của biến, Python sẽ tự động xác định kiểu dữ liệu dựa trên giá trị được gán. Ví dụ:

```python
a = 5
# a sẽ tự động là kiểu số nguyên (int)
```

### Các kiểu dữ liệu cơ bản

*   **Boolean (`bool`)**: Kiểu chỉ bao gồm hai giá trị `True` và `False`, thường dùng trong kiểm tra điều kiện.
    ```python
    flag = True
    check = 5 > 3  # Kết quả là True
    ```
    Các toán tử so sánh `==, !=, <, >, <=, >=` cho phép so sánh hai giá trị.

*   **Số (Number)**: Gồm `int` (số nguyên), `float` (số thực), và `complex` (số phức).
    ```python
    a = 10         # int
    b = 3.14       # float
    c = 2+3j       # complex
    ```

*   **Chuỗi (`str`)**: Kiểu dữ liệu để lưu trữ văn bản. Chuỗi được đặt trong dấu nháy đơn hoặc kép.
    ```python
    s = "Xin chào, Python!"
    # Nối chuỗi
    s2 = s + " " + "hahaha" 
    ```

*   **Danh sách (`list`)**: Là tập hợp các phần tử có thứ tự và có thể thay đổi.
    ```python
    a =
    ```
    Với danh sách `a`, bạn có thể truy cập các phần tử qua chỉ số (index) bắt đầu từ 0 (`a[0]`), lấy một phần tử (`a[1:4]`), và có thể thêm, xóa, sửa các phần tử.

*   **Tuple**: Tương tự danh sách nhưng không thể thay đổi (immutable).
    ```python
    b = (1, 2, 3)
    ```

*   **Tập hợp (`set`)**: Là tập hợp không có thứ tự và không cho phép các phần tử trùng lặp.
    ```python
    c = {1, 2, 3, 3}
    print(c) # Output: {1, 2, 3}
    ```

*   **Từ điển (`dict`)**: Bao gồm các cặp `key-value`.
    ```python
    d = {'name': 'Alice', 'age': 30}
    # Truy xuất qua key
    print(d['name']) # Output: 'Alice'
    ```

### Các hàm tích hợp (Built-in Functions)
Python có nhiều hàm tích hợp hữu ích:
*   `print(x)`: In giá trị ra màn hình.
*   `type(x)`: Trả về kiểu dữ liệu của biến.
*   `input(prompt)`: Nhận đầu vào từ người dùng.
*   Các hàm chuyển đổi kiểu: `int()`, `float()`, `str()`, `list()`, `tuple()`, `set()`, `dict()`.

```python
# Ví dụ
s_number = "123"
number = int(s_number)
print(type(number)) # Output: <class 'int'>
```

## 3. Hàm (Functions)

Trong Python, hàm (function) là một khối mã được tổ chức và có thể tái sử dụng để thực hiện một nhiệm vụ nhất định. Hàm giúp làm cho chương trình có cấu trúc, dễ quản lý, và giảm thiểu sự lặp lại mã.

**Định nghĩa hàm:**
```python
def tinh_tong(a, b):
  """Hàm này tính tổng hai số a và b."""
  return a + b
```

**Gọi hàm:**
```python
tong = tinh_tong(3, 5)
print(tong) # Kết quả: 8
```

Trong ví dụ trên, `tinh_tong` là tên hàm, `a` và `b` là các tham số, `return` là từ khóa trả về kết quả.

## 4. Câu lệnh điều kiện (Conditions / Branching)

Câu lệnh điều kiện cho phép chương trình thực thi các nhánh mã khác nhau tùy theo điều kiện logic. Python sử dụng các từ khóa `if`, `elif` (else if), và `else` để xây dựng cấu trúc điều khiển.

**Cấu trúc cơ bản:**
```python
x = 10

if x > 0:
  print("x là số dương")
elif x == 0:
  print("x bằng 0")
else:
  print("x là số âm")
```

**Toán tử logic:**
Python sử dụng `and`, `or`, `not` để kết hợp các điều kiện.
```python
x = 10
y = -5

if x > 0 and y < 0:
  print("Điều kiện đúng, được thực thi")
```

## 5. Ứng dụng: Chatbot dựa trên luật (Rule-based Chatbot)

Chatbot dựa trên luật là một chatbot đơn giản, hoạt động bằng cách dựa trên các quy tắc và mẫu đã được định nghĩa. Khi nhận đầu vào từ người dùng, chatbot sẽ đối chiếu với các quy tắc để tìm câu trả lời phù hợp.

**Luồng xử lý của một chatbot dựa trên luật:**
Đầu tiên, chatbot kiểm tra xem đầu vào của người dùng có khớp với bất kỳ mẫu (pattern) nào được định trước hay không. Nếu có, nó sẽ trả về câu trả lời tương ứng; nếu không, nó có thể báo lỗi hoặc yêu cầu người dùng nhập lại.

**Ví dụ một hàm chatbot đơn giản trong Python:**
```python
def tra_loi_chatbot(cau_hoi):
  """Hàm xử lý câu hỏi và trả lời dựa trên luật."""
  cau_hoi = cau_hoi.lower() # Chuyển về chữ thường để dễ xử lý

  if "xin chào" in cau_hoi:
    return "Xin chào! Bạn cần hỗ trợ gì?"
  elif "bảo hành" in cau_hoi:
    return "Vui lòng cung cấp số seri của sản phẩm để tra cứu bảo hành."
  else:
    return "Xin lỗi, tôi không hiểu. Bạn có thể hỏi lại?"
```

Đoạn mã trên sử dụng các câu lệnh điều kiện để đối chiếu đầu vào với một số từ khóa nhất định ("xin chào", "bảo hành") và trả về câu trả lời tương ứng. Đây là phương pháp xây dựng chatbot dựa trên luật đơn giản nhất.

---
#2. Các loại vòng lặp
 Bạn mới học và tìm hiểu về Python, và bạn không muốn phải gõ đi gõ lại những đoạn code giống hệt nhau, cùng thực hiện một công việc? Công việc này quả thực rất nhàm chán, vì thế cũng như các ngôn ngữ lập trình khác thì vòng lặp (loop) là thứ "khổng thể thiếu". Sử dụng vòng lặp giúp bạn lặp lại một hoạt động nhiều lần và sẽ cực kỳ hữu dụng trong việc xử lý dữ liệu, tính toán, ...

## 1. Vòng lặp for
```python
  for element in iterable:
     #khối lệnh lặp lại
```
element: phần tử trong iterable

  iterable: chuỗi, danh sách, tuple, dictionary hoặc range()
Ví dụ:
```python
  for i in range(5):
    print(i, end=" ")
#Output: 0 1 2 3 4
```
##2. While loop
```python
  while condition:
    #hành động lặp lại:
```
condition: điều kiện đúng thì vòng lặp sẽ hoạt động
Ví dụ:
```python
sum = 0
i = 1
while i <= 5: ##tính tổng từ 1-5
    sum += i
    i++
print(sum)
# Output: 15
```
Ghi chú: Nếu là một người mới bắt đầu, bạn còn đang lăn tăn không biết khi nào sài for hay while thì đây là một vài lời khuyên dành cho bạn:
- Nếu có thể đếm được hoặc duyệt qua cái gì đó -> For là lựa chọn tốt
- Nếu bạn không biết lặp bao nhiêu lần hoặc phải lặp đi lặp lại đến một trạng thái nào đó -> Hãy chọn While.
  
#Break và Continue - Điều kiển vòng lặp

Nếu bạn muốn vòng lặp của mình dừng lại khi đặt điều kiện nào hay đơn giản là bỏ qua giá trị không phù hợp thì break và countine hoàn toàn đáp ứng được nhu cầu của bạn.
- Break: thoát khỏi vòng lặp ngay lập tức.
- Continue: bỏ qua bước hiện tại và tiếp tục vòng kế tiếp.

Ví dụ:
```python
#Break - in các số nhỏ hơn 5 và dừng lại khi i = 3
  for i in range(5):
    if i == 3:
      break
    print(i)
#Output: 0 1 2

#Continue - in các số từ 1 đến 9 và bỏ qua i = 5
for i in range(10):
    if i == 5:
        continue
    print(i)
#Output: 0 1 2 3 4 6 7 8 9
```
🧠 Ứng dụng thực tế vòng lặp
```python
#Tính số Pi:
n = 1000
pi = 0
for i in range(n):
    pi += (-1)**i / (2*i + 1)
pi *= 4
print(pi)

#Tính diện tích hình tròn:
import math
n = 1000
delta_x = 1/n
area = 0
for i in range(n):
    x = i * delta_x
    y = math.sqrt(1 - x**2)
    area += y * delta_x
area *= 4
print(area)
```

 **Làm việc với File trong Python – Đọc & Ghi Tệp Dễ Dàng Cho Người Mới**

Khi xây dựng chương trình thực tế, bạn sẽ cần tương tác với tệp dữ liệu — chẳng hạn đọc dữ liệu từ một file .txt, ghi kết quả tính toán ra một file log, hoặc xử lý dữ liệu CSV.

Python giúp bạn làm điều này một cách đơn giản qua các lệnh open(), read(), write(), và khối lệnh with.

🔑 Các bước cơ bản khi làm việc với file:
1. Mở file - open()
```python
f = open("filename.txt", "mode")
```
- "r": đọc (read)

- "w": ghi đè (write)

- "a": ghi thêm (append)

- "x": tạo mới, lỗi nếu file tồn tại

- "b": nhị phân

- "t": văn bản (mặc định)

2. Đọc nội dung file
```python
with open("data.txt", "r") as file:
    content = file.read()
    print(content)
```
3. Đọc từng dòng
```python
with open("data.txt", "r") as file:
    for line in file:
        print(line.strip())  # bỏ ký tự xuống dòng
```
4. Ghi nội dung vào file
```python
with open("output.txt", "w") as file:
    file.write("Hello, world!\n")
    file.write("Python is awesome!\n")
```
Lưu ý: Nếu file chưa tồn tại, Python sẽ tạo mới. Nếu đã tồn tại, w sẽ ghi đè toàn bộ nội dung cũ!

## Một số ví dụ thực tế
Đọc danh sách sinh viên từ file
```python
with open("students.txt", "r") as f:
    names = [line.strip() for line in f]
print(names)

scores = {"Alice": 95, "Bob": 82}
with open("scores.txt", "w") as f:
    for name, score in scores.items():
        f.write(f"{name}: {score}\n")
```

###Mẹo dùng with - Quản lý file an toàn
Câu lệnh with giúp mở file tự động và đóng lại sau khi dùng, tránh lỗi quên đóng file.
```python
with open("log.txt", "a") as log:
    log.write("New log entry\n")
```
###Kết hợp for + file
Bạn có thể dùng vòng lặp for để đọc ghi dữ liệu hàng loạt:
```python
#Ghi bảng cửu chương vào file:

with open("multiplication.txt", "w") as f:
    for i in range(1, 10):
        for j in range(1, 10):
            f.write(f"{i} x {j} = {i*j}\n")
```
# 3. Coding Methodology - Từ "Chạy Được" Đến "Clean Code"

Ai trong chúng ta cũng từng viết những dòng code... ờ thì, nó "chạy được". Nhưng để người khác (hoặc chính bạn của vài tháng sau đó) đọc vào mà không muốn "đấm" cái màn hình thì đó lại là một câu chuyện khác á.

Buổi học này chính để giải quyết vấn đề đó: Biến những dòng code lộn xộn, khó đọc thành những tác phẩm "sạch - đẹp - pythonic".

---

## Phần 1: Nền Móng Vững Chắc - Clean Code & PEP-8
\
### 1. Clean Code là gì mà "ghê" vậy?

Nói đơn giản, Clean Code là code được viết sao cho:

*   **Dễ đọc (Readable):** Nhìn vào là hiểu nó đang làm gì, không cần phải vò đầu suy nghĩ.
*   **Dễ bảo trì (Maintainable):** Khi cần sửa lỗi hay thêm tính năng, bạn không cần phải xoá đi viết lại nó.
*   **Dễ kiểm thử (Testable):** Viết unit test cho nó dễ dàng.
*   **Dễ mở rộng (Extensible):** Thêm tính năng mới mà không làm sập hệ thống cũ.


Viết code bẩn ban đầu có thể nhanh, nhưng nó sẽ tạo ra rất nhiều vấn đề lâu dài mà bạn và đồng đội sẽ phải trả giá bằng mồ hôi, nước mắt (và cả thời gian debug) trong tương lai.

\
### 2. PEP-8: "Kinh Thánh" về Phong Cách Code Python
\
**PEP-8** (Python Enhancement Proposal 8) là bộ quy tắc định dạng code Python chính thức. Mục tiêu của nó là làm cho code trở nên nhất quán và dễ đọc hơn trên mọi dự án.


> "Code is read more often that it is written" - Robert C. Martin


Hãy đi vào những quy tắc cốt lõi mà anh em AIO2025 cần khắc cốt ghi tâm.

\
####a. Quy tắc đặt tên (Naming Convention)

Đây là thứ đập vào mắt đầu tiên. Đặt tên sai thì làm việc với code rất mệt ngay lập tức.

*   `snake_case`: Dùng cho **biến** và **hàm**. Chữ thường, nối với nhau bằng dấu gạch dưới.
*   `PascalCase` (hoặc `CapWords`): Dùng cho **Class**. Viết hoa chữ cái đầu mỗi từ.
*   `UPPER_CASE_WITH_UNDERSCORES`: Dùng cho **hằng số**.

**Ví dụ:**

```python
# Hằng số
PASSING_SCORE = 5
COURSE_NAME = "Coding Methodology in Python"

# Class dùng PascalCase
class AIO2025Student:
    def __init__(self, student_name, student_id):
        self.student_name = student_name
        self.student_id = student_id
        self.assignments = {}

    # Hàm/method dùng snake_case
    def submit_assignment(self, assignment_name, score):
        """Hàm để nộp bài tập và ghi điểm."""

        print(f"Sinh viên {self.student_name} nộp bài '{assignment_name}'")
        self.assignments[assignment_name] = score

    def check_final_result(self):
        """Kiểm tra kết quả cuối kỳ."""
        if not self.assignments:
            return "Failed"
        total_score = sum(self.assignments.values())
        average_score = total_score /len(self.assignments)

        if average_score >= PASSING_SCORE:
            return "Passed"
        return "Failed"

# Biến dùng snake_case
student_khoa = AIO2025Student("Nguyễn Văn A", "AIO2025-001")
student_khoa.submit_assignment("PEP-8 Practice", 95)
print(f"Kết quả của Khoa: {student_khoa.check_final_result()}")
```

#### b. Căn lề, khoảng trắng và độ dài dòng

*   **Thụt lề:** Dùng **4 khoảng trắng**, tuyệt đối không dùng `Tab`.
*   **Khoảng trắng:** Đặt xung quanh các toán tử (`=`, `+`, `-`, `*`, `/`) và sau dấu phẩy.
*   **Độ dài dòng:**88-100 ký tự (hoặc 79 ký tự theo PEP-8). Nếu dòng quá dài, hãy ngắt dòng. Ưu tiên ngắt bên trong dấu `()`, `[]`, `{}`.

**Ví dụ "Tệ" vs "Đẹp":**

```python
# Tệ: Lộn xộn, khó đọc
def bad_function(arg1,arg2,arg3,arg4):
    result=arg1*arg2+arg3/arg4 #Thiếu space
    long_name_that_is_bad = "This is a very long string that absolutely violates the PEP-8 line length limit and is very hard to read"
    return result

# Đẹp: Tuân thủ PEP-8
def good_function(arg1, arg2, arg3, arg4):
    result = (arg1 * arg2) + (arg3 / arg4)
    
    # Ngắt dòng dài một cách hợp lý
    variable_name = (
        "This is a very long string that now respects "
        "the PEP-8 line length limit and is much easier to read."
    )
    return result
```

#### c. Docstrings & Type Hints: Tự ghi lại "hướng dẫn sử dụng"

*   **Docstring (`"""Docstring goes here"""`)**: Là chuỗi tài liệu mô tả một module, class, hoặc hàm. Giúp người khác hiểu code mình đó.
*   **Type Hints (`name: str`, `-> int`)**: Chỉ định kiểu dữ liệu cho biến, tham số và giá trị trả về. Giúp bắt lỗi sớm và làm code rõ ràng hơn rất nhiều luôn.

**Ví dụ hoàn chỉnh:**

```python
def create_student_greeting(student_name: str, course_name: str, is_formal: bool = False) -> str:
    """Tạo một lời chào cho sinh viên tham gia khoá học.

    Hàm này xây dựng một chuỗi chào mừng dựa trên tên của sinh viên,
    tên khóa học, vàvề mức độ trang trọng.

    Args:
        student_name: Tên của sinh viên.
        course_name: Tên của khóa học.
        is_formal: Mặc định là False. Nếu True, lời chào sẽ trang trọng.

    Returns:
        Lời chào đã được định dạng.
    """
    if is_formal:
        # Lời chào trang trọng
        greeting = f"Kính gửi bạn {student_name}, chào mừng bạn đến với khóa học {course_name}."
    else:
        # Lời chào thân mật
        greeting = f"Hey {student_name}! Chào mừng đến với {course_name} nhé!"
    
    return greeting


casual_greeting = create_student_greeting("Khoa", "AIO2025")
print(casual_greeting)
# Output: Hey Khoa! Chào mừng đến với AIO2025 nhé!

formal_greeting = create_student_greeting(" Nguyễn Thái Hà", "Coding Methodology", is_formal =True)
print(formal_greeting)
# Output: Kính gửi bạn  Nguyễn Thái Hà, chào mừng bạn đến với khóa học Coding Methodology.

#IDE và mypy sẽ cảnh báo nếu bạn đưa sai kiểu dữ liệu
# Ví dụ, nếu bạn viết: create_student_greeting(123, "AIO2025")
#IDE sẽ gạch chân số 123 và báo lỗi "Expected type 'str', got 'int'instead"
```

#### d. Công cụ hỗ trợ


*   **`flake8`**: Kiểm tra tổng hợp (cú pháp, style PEP-8, độ phức tạp).
*   **`black`**: "The uncompromising code formatter". Nó sẽ tự động format code của bạn theo một chuẩn duy nhất, không cần tranh cãi.
*   **`mypy`**: Kiểm tra type hints.

Cài đặt: `pip install flake8 black mypy`
Sử dụng trong terminal: `black your_file.py`, `flake8 your_file.py`, `mypy your_file.py`

---

## Phần 2: Viết Code "Pythonic"

\
Pythonic Code là việc tận dụng những tính năng độc đáo, mạnh mẽ của Python để viết code ngắn gọn, hiệu quả và chính xác.

### 1. Comprehensions: "Phép thuật" trong một dòng

Thay vì dùng vòng lặp `for` dài dòng để tạo list/dict/set, hãy dùng comprehensions.

**Ví dụ: Bình phương các số chẵn**

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]

# Cách truyền thống (Non-Pythonic)
squared_evens_old = []
for num in numbers:
    if num % 2 == 0:
        squared_evens_old.append(num * num)
print(f"{squared_evens_old}")

# Cách Pythonic
squared_evens_new = [num * num for num in numbers if num % 2 == 0]
print(f"{squared_evens_new}")
# Output cho cả hai: [4, 16, 36, 64]
```
Ngắn hơn, nhanh hơn, và một khi đã quen thì... "sướng" hơn!

### 2. Context Managers (`with`): Quản lý tài nguyên an toàn

Bạn đã bao giờ mở một file và quên đóng nó `file.close()`? Lỗi này có thể gây mất dữ liệu.
\
`with` statement sẽ đảm bảo tài nguyên (file, kết nối database...) luôn được giải phóng, kể cả khi có lỗi xảy ra.

```python
# Non-Pythonic: Dễ quên close() hoặc lỗi giữa file
try:
    f = open('my_model.txt', 'w')
    f.write('Training started...')
    # Giả sử có lỗi ở đây
    # result = 1 / 0
finally:
    # Phải nhớ gọi close() trong finally
    print("Đóng file (cách cũ).")
    f.close()

# Pythonic: Tự động, an toàn
with open('my_model_pythonic.txt', 'w') as f:
    f.write('Training started...')
    # Dù có lỗi hay không, file sẽ tự động được đóng khi ra khỏi khối with
```

###  3. So sánh kiểu Pythonic

Đừng viết những câu lệnh `if` rườm rà!

*   **Kiểm tra `None`**: Dùng `is` hoặc `is not`, không dùng `==`.
*   **Kiểm tra Boolean**: Không cần `== True` hay `== False`.
*   **Kiểm tra rỗng**: Các collection như (list, dict, string) được coi là `False`.
*   **Kiểm tra tồn tại**: Dùng `in`.
*   **Nối chuỗi so sánh**: Python cho phép `a < b < c`.

```python
# Thay vì
my_list = []
if my_list != None and len(my_list) > 0:
    print("List is not empty.")

# Hãy viết
if my_list: # Ngắn gọn, hiệu quả
    print("List is not empty.")
else:
    print("List is empty or None.")

#---------------------------------------

target = "AIO2025"
my_collection = ["AI", "AIO2025", "Python"]

# Thay vì
found = False
for item in my_collection:
    if item == target:
        found = True
        break
if found:
    print(f"Found {target}!")

# Hãy viết
if target in my_collection:
    print(f"Found {target}!")
    
#---------------------------------------

score = 85
# Thay vì
if score >= 0 and score <= 100:
    print("Valid score")

# Hãy viết
if 0 <= score <= 100:
    print("Valid score")
```

### 4. Underscores và `@property`: Che giấu và Phơi bày

*   **`_single_underscore`**: Quy ước là "biến/ method nội bộ", đừng nghịch nó từ bên ngoài
*   **`__double_underscore`**: Python sẽ tự đổi tên biến để tránh bị ghi đè ở class con.
*   **`@property`**: Biến một method thành một thuộc tính chỉ để đọc. Giúp code gọn gàng hơn.

```python

class AIModel:
    def __init__(self, name, layers: list):
        self.name = name
        self._layers = layers  # _layers là 'internal', không nên truy cập trực tiếp
        self._is_trained = False
    
    @property
    def complexity(self) -> int:
        """Tính độ phức tạp của model (chỉ đọc)."""
        # Đây là một method, nhưng được gọi như một attribute

        return len(self._layers) * sum(self._layers)

    def train(self):

        """Train the model."""
        print(f"Training {self.name}...")
        self._is_trained = True

# Sử dụng
model = AIModel("SimpleAIO", layers=[128, 64, 10])

# Gọi property như một attribute, không cần ()
print(f"Độ phức tạp của model: {model.complexity}")

# Bạn không thể gán giá trị cho property này
try:
    model.complexity = 100 # Báo lỗi AttributeError
except AttributeError as e:
    print(f"Lỗi: {e}")
```
### Tổng hợp

*   **Clean Code & PEP-8** là cú pháp cơ bản để mọi người có thể hiểu nhau dễ dàng hơn.
*   **Pythonic Code** là những thành ngữ diễn đạt code của bạn trở nên thuần Python hơn nhiều.

---
#4. Nguyên lý chung để viết code tốt

###  DRY - Don't Repeat Yourself
Nguyên tắc DRY nhấn mạnh việc **tránh lặp lại code**. Hãy:
*   Tách logic lặp lại thành các **hàm, class, hoặc module** riêng.
*   Việc này giúp giảm lỗi, tăng khả năng tái sử dụng và dễ dàng bảo trì khi cần thay đổi.

#### Như thế nào là vi phạm DRY?
```python
def print_morning_greeting(name):
    print(f"Good morning, {name}!")
    print("I hope you have a wonderful day.")
    print("Don't forget to drink water and take breaks.")
    print("-----------------------------------------")

def print_evening_greeting(name):
    print(f"Good evening, {name}!")
    print("I hope you had a wonderful day.")
    print("Don't forget to drink water and take breaks.")
    print("-----------------------------------------")```

#### Như thế nào là tuân thủ DRY?
```python
def print_greeting(name, time_of_day):
    print(f"Good {time_of_day}, {name}!")
    day_wish = "have" if time_of_day == "morning" else "had"
    print(f"I hope you {day_wish} a wonderful day.")
    print("Don't forget to drink water and take breaks.")
    print("-----------------------------------------")

print_greeting("Alice", "morning")
print_greeting("Bob", "evening")
```

### YAGNI - You Aren't Gonna Need It
Đừng viết code cho những tính năng chưa chắc sẽ dùng. Đây là một lời khuyên cho các lập trình viên có thói quen "code cho tương lai" (thêm các cấu trúc logic để phòng khi cần).
*   **Chỉ nên xây dựng thêm chức năng khi thực sự cần thiết.**

#### Như thế nào là vi phạm YAGNI?
Tạo hệ thống plugin khi mới có 1 loại chức năng.
```python
class SuperCalculator:
    """A calculator with many features we might not need."""
    def __init__(self):
        self.history = []
        self.memory = 0
        self.scientific_mode = False
        self.conversion_rates = {
            "USD_to_EUR": 0.85,
            "EUR_to_USD": 1.18,
            "USD_to_GBP": 0.73,
            "GBP_to_USD": 1.37,
            # ... dozens more conversion rates
        }
    # ...
```

#### Như thế nào là tuân thủ YAGNI?
Dùng cấu trúc đơn giản, rồi mở rộng khi cần.
```python
class SimpleCalculator:
    """A calculator that starts with just what we need."""
    def add(self, a, b):
        """Add two numbers."""
        return a + b

    def subtract(self, a, b):
        """Subtract b from a."""
        return a - b

# We can add more methods later when we actually need them
```

###  KISS - Keep It Simple, Stupid
"Đơn giản tốt hơn phức tạp". KISS ưu tiên giải pháp **đơn giản**, **dễ hiểu nhất**. Cố gắng tránh các giải pháp phức tạp.

#### Như thế nào là vi phạm KISS?
Chuyển số sang nhị phân, rồi kiểm tra xem đuôi là 0 hay 1. Bằng 0 thì là số chẵn, bằng 1 thì là số lẻ. -> Quá phức tạp.
```python
def is_even_complex(number):
    """Determine if a number is even using a complex algorithm."""
    # Convert to binary string
    binary = bin(number)[2:] # Remove '0b' prefix
    
    # Check last digit of binary (1 for odd, 0 for even)
    last_digit = binary[-1]

    # Convert to integer and check if it's zero
    return int(last_digit) == 0
```

#### Như thế nào là tuân thủ KISS?
Chỉ cần kiểm tra xem số đó có chia hết cho 2 không.
```python
def is_even_simple(number):
    """Determine if a number is even using the modulo operator."""
    return number % 2 == 0
```

### Defensive Programming - Lập trình phòng thủ
Viết code với suy nghĩ "mọi thứ có thể sai" (đầu vào không hợp lệ, thiếu file, API timeout, ...).

#### Kiểm tra rõ ràng
```python
# Defensive programming
def divide(a, b):
    if not isinstance(a, (int, float)) or not isinstance(b, (int, float)):
        raise TypeError("Tham số phải là số.")
    if b == 0:
        raise ValueError("Không thể chia cho 0.")
    return a / b

def get_element(lst, index):
    if not isinstance(lst, list):
        raise TypeError("Tham số phải là list.")
    if index < 0 or index >= len(lst):
        return None # Hoặc giá trị mặc định thay vì lỗi
    return lst[index]
```

#### Dùng try-except đúng cách
*   Ghi log lỗi thay vì `print`.
*   Tránh xử lý lỗi chung chung (tránh `except Exception:`).
```python
try:
    with open("file.txt") as f:
        data = f.read()
        parsed = json.loads(data)
        result = 10 / parsed["value"]
except FileNotFoundError:
    logger.error("Không tìm thấy file.")
    raise ConfigError("File cấu hình không tồn tại")
except json.JSONDecodeError:
    logger.error("File không đúng định dạng JSON.")
except KeyError:
    logger.error("Thiếu trường 'value' trong dữ liệu.")
except ZeroDivisionError:
    logger.error("Giá trị 'value' không thể bằng 0.")
```
> Code bền vững, giúp dễ dàng kiểm soát bug và phản ứng kịp khi hệ thống có sự cố.

### Separation of Concerns - Phân chia trách nhiệm
Một hàm/class chỉ nên làm **một việc cụ thể**. Mỗi mỗi phần chỉ lo một mảng, hệ thống sẽ dễ mở rộng, dễ test, dễ bảo trì.
```python
# Good example
def process_user_data(user):
    if validate_user(user):
        save_user(user)
        notify_user(user)
        log_activity(user)

def validate_user(user):
    return bool(user.email and '@' in user.email)

def save_user(user):
    repository = UserRepository()
    repository.add(user)

def notify_user(user):
    email_service = EmailService()
    email_service.send_welcome(user.email)

def log_activity(user):
    reporter = ActivityReporter()
    reporter.create_registration_report(user.id)
```
Trong ví dụ trên, mỗi hàm chỉ thực hiện một nhiệm vụ duy nhất.
---

# 5. Nguyên Tắc SOLID và Design Patterns

## Giới Thiệu Về SOLID Principles

SOLID là tập hợp 5 nguyên tắc cơ bản trong lập trình hướng đối tượng, được thiết kế để giúp các lập trình viên tạo ra những đoạn code dễ bảo trì, mở rộng và ít gây lỗi. Những nguyên tắc này không chỉ là lý thuyết mà còn là những hướng dẫn thực tiễn đã được kiểm chứng qua nhiều dự án phần mềm lớn. Tên **SOLID** thực chất là từ viết tắt của 5 nguyên tắc: **S**ingle Responsibility, **O**pen/Closed, **L**iskov Substitution, **I**nterface Segregation, và **D**ependency Inversion.

Việc hiểu và áp dụng đúng các nguyên tắc SOLID sẽ giúp bạn viết code có cấu trúc rõ ràng, dễ đọc hiểu, và quan trọng nhất là dễ dàng thay đổi khi yêu cầu kinh doanh thay đổi. Điều này đặc biệt quan trọng trong môi trường phát triển phần mềm hiện đại, nơi mà việc thay đổi và cập nhật liên tục là điều không thể tránh khỏi.

###  Single Responsibility Principle (SRP) - Nguyên Tắc Trách Nhiệm Đơn Lẻ

Nguyên tắc đầu tiên và có thể nói là quan trọng nhất của SOLID là **Single Responsibility Principle**. Nguyên tắc này khẳng định rằng mỗi class chỉ nên có một lý do để thay đổi, hay nói cách khác, mỗi class chỉ nên đảm nhận một trách nhiệm duy nhất. Điều này có nghĩa là khi chúng ta thiết kế một class, chúng ta cần tự hỏi: "Class này đang làm những gì? Liệu nó có đang làm quá nhiều việc cùng lúc không?"

Khi một class vi phạm SRP, nó sẽ trở nên khó hiểu, khó test, và đặc biệt khó bảo trì. Mỗi khi có một thay đổi nhỏ trong một phần của class, bạn có nguy cơ phải sửa đổi nhiều phần khác, dẫn đến việc tạo ra lỗi không mong muốn. Hãy xem ví dụ sau để hiểu rõ hơn về vấn đề này.

**Ví dụ Vi Phạm SRP:**

```python
class User:
    def __init__(self, name, email):
        self.name = name
        self.email = email
    
    def save_to_database(self):
        # Lưu user vào database
        print(f"Saving {self.name} to database")
    
    def send_email(self):
        # Gửi email
        print(f"Sending email to {self.email}")
    
    def validate_email(self):
        # Kiểm tra email hợp lệ
        return "@" in self.email
```

Trong ví dụ trên, class `User` đang vi phạm SRP vì nó đang đảm nhận quá nhiều trách nhiệm. Nó vừa quản lý thông tin người dùng, vừa xử lý việc lưu trữ database, vừa gửi email, và còn validate dữ liệu. Điều này có nghĩa là class này sẽ phải thay đổi khi có bất kỳ thay đổi nào trong logic business về user, cách thức lưu trữ database, cách gửi email, hay cách validate dữ liệu.

**Cải Thiện Theo SRP:**

```python
class User:
    def __init__(self, name, email):
        self.name = name
        self.email = email

class UserRepository:
    def save(self, user):
        print(f"Saving {user.name} to database")

class EmailService:
    def send_email(self, user):
        print(f"Sending email to {user.email}")

class EmailValidator:
    def validate(self, email):
        return "@" in email
```

Sau khi refactor, mỗi class chỉ có một trách nhiệm cụ thể. Class `User` chỉ quản lý thông tin người dùng, `UserRepository` chịu trách nhiệm về việc lưu trữ, `EmailService` xử lý việc gửi email, và `EmailValidator` validate dữ liệu email. Bây giờ, khi có thay đổi về cách lưu trữ database, chúng ta chỉ cần sửa `UserRepository` mà không ảnh hưởng đến các class khác.

### Open/Closed Principle (OCP) - Nguyên Tắc Mở/Đóng

Nguyên tắc thứ hai của SOLID có thể nghe có vẻ mâu thuẫn khi lần đầu tiếp xúc: *"Software entities should be open for extension but closed for modification"* - tạm dịch là *"Các thực thể phần mềm nên mở cho việc mở rộng nhưng đóng cho việc sửa đổi"*. Điều này có nghĩa là chúng ta nên thiết kế code sao cho khi cần thêm tính năng mới, chúng ta có thể mở rộng hành vi của hệ thống mà không cần phải sửa đổi code đã tồn tại và đã được test.

Nguyên tắc này đặc biệt quan trọng trong môi trường phát triển phần mềm thương mại, nơi mà code đã được test kỹ lưỡng và đang chạy ổn định trong production. Việc sửa đổi code cũ luôn mang theo nguy cơ tạo ra bug mới, trong khi việc thêm code mới (extension) tương đối an toàn hơn.

**Ví dụ Vi Phạm OCP:**

```python
class DiscountCalculator:
    def calculate_discount(self, customer_type, amount):
        if customer_type == "regular":
            return amount * 0.05
        elif customer_type == "premium":
            return amount * 0.10
        elif customer_type == "vip":
            return amount * 0.20
        # Mỗi lần thêm loại khách hàng mới phải sửa code này
```

Đoạn code trên vi phạm OCP vì mỗi khi có loại khách hàng mới, chúng ta buộc phải sửa đổi method `calculate_discount`. Điều này không chỉ vi phạm nguyên tắc "closed for modification" mà còn có thể gây ra lỗi cho các loại khách hàng đã tồn tại.

**Cải Thiện Theo OCP:**

```python
from abc import ABC, abstractmethod

class DiscountStrategy(ABC):
    @abstractmethod
    def calculate(self, amount):
        pass

class RegularDiscount(DiscountStrategy):
    def calculate(self, amount):
        return amount * 0.05

class PremiumDiscount(DiscountStrategy):
    def calculate(self, amount):
        return amount * 0.10

class VIPDiscount(DiscountStrategy):
    def calculate(self, amount):
        return amount * 0.20

class DiscountCalculator:
    def __init__(self, strategy: DiscountStrategy):
        self.strategy = strategy
    
    def calculate_discount(self, amount):
        return self.strategy.calculate(amount)

# Sử dụng
calculator = DiscountCalculator(PremiumDiscount())
discount = calculator.calculate_discount(1000)
```

Với cách thiết kế mới này, khi cần thêm loại khách hàng mới, chúng ta chỉ cần tạo một class mới implement `DiscountStrategy` interface mà không cần sửa đổi bất kỳ code nào đã tồn tại. Đây chính là thể hiện của nguyên tắc "open for extension, closed for modification".

### Liskov Substitution Principle (LSP) - Nguyên Tắc Thay Thế Liskov

Nguyên tắc **Liskov Substitution** được đặt theo tên nhà khoa học máy tính Barbara Liskov. Nguyên tắc này phát biểu rằng các đối tượng của class con phải có thể thay thế được cho class cha mà không làm thay đổi tính đúng đắn của chương trình. Nói một cách đơn giản hơn, nếu chúng ta có một function hoạt động với class cha, thì function đó cũng phải hoạt động bình thường với bất kỳ class con nào.

Nguyên tắc này không chỉ đơn thuần về mặt cú pháp mà còn về mặt ngữ nghĩa. Một class con không chỉ cần implement đúng interface của class cha mà còn phải duy trì được hành vi mong đợi.

**Ví dụ Vi Phạm LSP:**

```python
class Bird:
    def fly(self):
        return "Flying"

class Penguin(Bird):
    def fly(self):
        raise Exception("Penguins can't fly!")  # Vi phạm LSP

# Vấn đề khi sử dụng
def make_bird_fly(bird: Bird):
    return bird.fly()

penguin = Penguin()
# make_bird_fly(penguin)  # Sẽ gây lỗi!
```

Ví dụ trên cho thấy một vi phạm LSP rất điển hình. Mặc dù về mặt sinh học, chim cánh cụt là một loài chim, nhưng trong context của việc bay thì việc cho `Penguin` inherit từ `Bird` là không phù hợp.

**Cải Thiện Theo LSP:**

```python
class Bird:
    def move(self):
        pass

class FlyingBird(Bird):
    def fly(self):
        return "Flying"
    
    def move(self):
        return self.fly()

class SwimmingBird(Bird):
    def swim(self):
        return "Swimming"
    
    def move(self):
        return self.swim()

class Eagle(FlyingBird):
    pass

class Penguin(SwimmingBird):
    pass
```

Trong cách thiết kế mới, chúng ta tạo ra một hierarchy hợp lý hơn. Tất cả các loài chim đều có thể di chuyển (`move`), nhưng cách thức di chuyển khác nhau. Bây giờ, bất kỳ function nào hoạt động với `Bird` cũng sẽ hoạt động tốt với `Eagle` hay `Penguin` thông qua method `move()`.

### Interface Segregation Principle (ISP) - Nguyên Tắc Phân Tách Interface

**Interface Segregation Principle** khuyên rằng không nên ép buộc client phụ thuộc vào các interface mà chúng không sử dụng. Thay vì tạo ra một interface lớn chứa nhiều method, chúng ta nên tạo ra nhiều interface nhỏ, mỗi interface tập trung vào một nhóm chức năng liên quan.

**Ví dụ Vi Phạm ISP:**

```python
from abc import ABC, abstractmethod

class AllInOneInterface(ABC):
    @abstractmethod
    def print_document(self):
        pass
    
    @abstractmethod
    def scan_document(self):
        pass
    
    @abstractmethod
    def fax_document(self):
        pass

class SimplePrinter(AllInOneInterface):
    def print_document(self):
        print("Printing...")
    
    def scan_document(self):
        # Không cần scan nhưng bắt buộc phải implement
        raise NotImplementedError("This printer can't scan")
    
    def fax_document(self):
        # Không cần fax nhưng bắt buộc phải implement
        raise NotImplementedError("This printer can't fax")
```

Trong ví dụ này, `SimplePrinter` chỉ cần chức năng in ấn nhưng lại bị buộc phải implement các method `scan` và `fax` mà nó không hỗ trợ.

**Cải Thiện Theo ISP:**

```python
class Printer(ABC):
    @abstractmethod
    def print_document(self):
        pass

class Scanner(ABC):
    @abstractmethod
    def scan_document(self):
        pass

class FaxMachine(ABC):
    @abstractmethod
    def fax_document(self):
        pass

class SimplePrinter(Printer):
    def print_document(self):
        print("Printing...")

class AllInOnePrinter(Printer, Scanner, FaxMachine):
    def print_document(self):
        print("Printing...")
    
    def scan_document(self):
        print("Scanning...")
    
    def fax_document(self):
        print("Faxing...")
```

Sau khi áp dụng ISP, chúng ta có ba interface riêng biệt. `SimplePrinter` chỉ cần implement `Printer` interface, trong khi `AllInOnePrinter` có thể implement cả ba.

### Dependency Inversion Principle (DIP) - Nguyên Tắc Đảo Ngược Phụ Thuộc

Nguyên tắc cuối cùng của SOLID, **DIP**, gồm hai phần:
1.  Các module cấp cao không nên phụ thuộc vào các module cấp thấp. Cả hai nên phụ thuộc vào abstraction.
2.  Abstraction không nên phụ thuộc vào chi tiết. Chi tiết nên phụ thuộc vào abstraction.

Nguyên tắc này đảo ngược cách chúng ta thường nghĩ về dependency. Thay vì để business logic phụ thuộc vào implementation details (như database cụ thể), chúng ta tạo ra các abstraction và để cả hai phụ thuộc vào đó.

**Ví dụ Vi Phạm DIP:**

```python
class MySQLDatabase:
    def save(self, data):
        print(f"Saving {data} to MySQL")

class UserService:
    def __init__(self):
        self.database = MySQLDatabase()  # Phụ thuộc trực tiếp vào MySQL
    
    def create_user(self, user_data):
        # Business logic
        self.database.save(user_data)
```

Ở đây, `UserService` (module cấp cao) đang phụ thuộc trực tiếp vào `MySQLDatabase` (module cấp thấp). Nếu muốn chuyển sang PostgreSQL, chúng ta phải sửa đổi `UserService`.

**Cải Thiện Theo DIP:**

```python
from abc import ABC, abstractmethod

class DatabaseInterface(ABC):
    @abstractmethod
    def save(self, data):
        pass

class MySQLDatabase(DatabaseInterface):
    def save(self, data):
        print(f"Saving {data} to MySQL")

class PostgreSQLDatabase(DatabaseInterface):
    def save(self, data):
        print(f"Saving {data} to PostgreSQL")

class UserService:
    def __init__(self, database: DatabaseInterface):
        self.database = database  # Phụ thuộc vào abstraction
    
    def create_user(self, user_data):
        # Business logic
        self.database.save(user_data)

# Sử dụng
mysql_db = MySQLDatabase()
user_service = UserService(mysql_db)
user_service.create_user("John Doe")
```

Bây giờ, `UserService` phụ thuộc vào `DatabaseInterface` (abstraction). Điều này cho phép chúng ta dễ dàng thay đổi database implementation mà không cần sửa đổi business logic, chỉ cần "inject" một dependency khác vào.

---

## Áp Dụng SOLID Vào Python

Python, với tính chất linh hoạt, cung cấp nhiều tính năng giúp việc áp dụng các nguyên tắc SOLID trở nên tự nhiên.

### Tính Linh Hoạt (Flexibility)

Dynamic typing của Python hỗ trợ rất tốt cho **OCP**. Khả năng thay đổi hành vi của object tại runtime cho phép chúng ta mở rộng chức năng mà không cần sửa đổi code gốc.

```python
class PaymentProcessor:
    def __init__(self):
        self.strategies = {}
    
    def register_strategy(self, payment_type, strategy):
        self.strategies[payment_type] = strategy
    
    def process(self, payment_type, amount):
        strategy = self.strategies.get(payment_type)
        if strategy:
            return strategy.process(amount)
        raise ValueError(f"Unknown payment type: {payment_type}")

# Có thể thêm strategy mới tại runtime
# processor = PaymentProcessor()
# processor.register_strategy("credit_card", CreditCardStrategy())
# processor.register_strategy("paypal", PayPalStrategy())
```

### Duck Typing

*"If it walks like a duck and quacks like a duck, then it must be a duck."* Python quan tâm đến hành vi (object có method cần thiết không) chứ không phải kiểu (object thuộc class nào). Điều này hỗ trợ rất tốt cho **LSP** và **ISP**.

```python
class Duck:
    def quack(self):
        return "Quack!"
    
    def fly(self):
        return "Flying"

class Robot:
    def quack(self):
        return "Beep beep!"
    
    def fly(self):
        return "Jet propulsion"

def make_it_quack_and_fly(duck_like_object):
    print(duck_like_object.quack())
    print(duck_like_object.fly())

# Cả Duck và Robot đều có thể sử dụng
duck = Duck()
robot = Robot()

make_it_quack_and_fly(duck)
make_it_quack_and_fly(robot)```

### Abstract Base Classes (ABC)

Module `abc` cung cấp công cụ mạnh mẽ để định nghĩa interface và abstract class, hỗ trợ tốt cho **DIP**.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass
    
    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)
```

### Protocol (Python 3.8+)

`Protocol` cho phép định nghĩa interface mà không cần kế thừa, hỗ trợ tốt cho **ISP** và **DIP** trong môi trường có type checking.

```python
from typing import Protocol

class Drawable(Protocol):
    def draw(self) -> None:
        ...

class Circle:
    def draw(self) -> None:
        print("Drawing circle")

class Square:
    def draw(self) -> None:
        print("Drawing square")

def render_shape(shape: Drawable) -> None:
    shape.draw()

# Cả Circle và Square đều implement Protocol một cách ngầm định
render_shape(Circle())
render_shape(Square())
```

---

## Design Patterns Phổ Biến

Design Patterns là những giải pháp đã được thử nghiệm cho các vấn đề thường gặp trong thiết kế phần mềm. Chúng được chia thành ba nhóm chính: Creational, Structural, và Behavioral.

### Creational Patterns (Mẫu khởi tạo)

Tập trung vào việc tạo object một cách linh hoạt.

#### Factory Pattern
Cho phép tạo object mà không cần chỉ định cụ thể class.

```python
class Animal(ABC):
    @abstractmethod
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

class AnimalFactory:
    @staticmethod
    def create_animal(animal_type):
        if animal_type == "dog":
            return Dog()
        elif animal_type == "cat":
            return Cat()
        else:
            raise ValueError(f"Unknown animal type: {animal_type}")

# Sử dụng
factory = AnimalFactory()
dog = factory.create_animal("dog")
print(dog.speak())  # Woof!
```

#### Singleton Pattern
Đảm bảo rằng một class chỉ có một instance duy nhất.

```python
class DatabaseConnection:
    _instance = None
    _initialized = False
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance
    
    def __init__(self):
        if not self._initialized:
            self.connection = "Connected to database"
            self._initialized = True
    
    def query(self, sql):
        return f"Executing: {sql}"

# Test
db1 = DatabaseConnection()
db2 = DatabaseConnection()
print(db1 is db2)  # True
```

###  Structural Patterns (Mẫu cấu trúc)

Tập trung vào việc định nghĩa mối quan hệ giữa các object.

#### Adapter Pattern
Cho phép các interface không tương thích làm việc với nhau.

```python
class EuropeanSocket:
    def voltage(self): return 230

class USASocket:
    def voltage(self): return 120

class Adapter:
    def __init__(self, socket):
        self.socket = socket
    
    def voltage(self):
        # Giả sử adapter chuyển đổi điện áp
        if self.socket.voltage() > 200:
            return 110
        return self.socket.voltage()

# Sử dụng
european_socket = EuropeanSocket()
adapter = Adapter(european_socket)
print(f"Voltage: {adapter.voltage()}V")  # 110V
```

#### Decorator Pattern
Thêm chức năng mới vào object mà không cần thay đổi cấu trúc của nó.

```python
class Coffee(ABC):
    @abstractmethod
    def cost(self): pass
    @abstractmethod
    def description(self): pass

class SimpleCoffee(Coffee):
    def cost(self): return 10
    def description(self): return "Simple coffee"

class CoffeeDecorator(Coffee):
    def __init__(self, coffee): self.coffee = coffee
    def cost(self): return self.coffee.cost()
    def description(self): return self.coffee.description()

class MilkDecorator(CoffeeDecorator):
    def cost(self): return self.coffee.cost() + 5
    def description(self): return self.coffee.description() + ", milk"

class SugarDecorator(CoffeeDecorator):
    def cost(self): return self.coffee.cost() + 2
    def description(self): return self.coffee.description() + ", sugar"

# Sử dụng
coffee = SimpleCoffee()
coffee = MilkDecorator(coffee)
coffee = SugarDecorator(coffee)

print(f"{coffee.description()}: ${coffee.cost()}")
# Output: Simple coffee, milk, sugar: $17
```

### Behavioral Patterns (Mẫu hành vi)

Tập trung vào việc định nghĩa cách các object giao tiếp.

#### Command Pattern
Encapsulate một request thành một object, hỗ trợ undo, redo, logging.

```python
class Command(ABC):
    @abstractmethod
    def execute(self): pass
    @abstractmethod
    def undo(self): pass

class Light:
    def turn_on(self): print("Light is ON")
    def turn_off(self): print("Light is OFF")

class LightOnCommand(Command):
    def __init__(self, light): self.light = light
    def execute(self): self.light.turn_on()
    def undo(self): self.light.turn_off()

class LightOffCommand(Command):
    def __init__(self, light): self.light = light
    def execute(self): self.light.turn_off()
    def undo(self): self.light.turn_on()

class RemoteControl:
    def __init__(self):
        self.history = []
    
    def press_button(self, command):
        self.history.append(command)
        command.execute()
    
    def press_undo(self):
        if self.history:
            self.history.pop().undo()

# Sử dụng
light = Light()
remote = RemoteControl()

remote.press_button(LightOnCommand(light))   # Light is ON
remote.press_button(LightOffCommand(light))  # Light is OFF
remote.press_undo()                         # Light is ON
```

#### Template Method Pattern
Định nghĩa skeleton của một algorithm, để các subclass override một số step cụ thể.

```python
class DataProcessor(ABC):
    def process_data(self):
        """Template method"""
        data = self.read_data()
        processed_data = self.process(data)
        self.save_data(processed_data)
    
    @abstractmethod
    def read_data(self): pass
    
    @abstractmethod
    def process(self, data): pass
    
    @abstractmethod
    def save_data(self, data): pass

class CSVProcessor(DataProcessor):
    def read_data(self):
        print("Reading CSV file")
        return "CSV data"
    
    def process(self, data):
        print("Processing CSV data")
        return f"Processed {data}"
    
    def save_data(self, data):
        print(f"Saving to database: {data}")

# Sử dụng
csv_processor = CSVProcessor()
csv_processor.process_data()
```

---

## Cách Sử Dụng Design Patterns Hiệu Quả

Sử dụng Design Patterns không chỉ là implement đúng mà còn phải biết khi nào nên và không nên áp dụng.

### Khi Nào Nên Áp Dụng
- Khi code đang trở nên phức tạp, khó bảo trì, hoặc có nhiều đoạn lặp lại.
- Khi dự đoán sẽ có nhiều thay đổi trong tương lai (ví dụ, hỗ trợ nhiều loại database).
- Trong môi trường team để tạo ra ngôn ngữ chung và kiến trúc nhất quán.

###Khi Nào Không Nên Áp Dụng
- Khi code đơn giản và hoạt động tốt (tránh over-engineering).
- Khi chưa hiểu rõ vấn đề cần giải quyết.
- Áp dụng mù quáng mà không hiểu context và trade-off.

### Trade-offs Cần Cân Nhắc
- **Ưu điểm**: Tăng khả năng đọc, bảo trì, tái sử dụng, và giảm coupling.
- **Nhược điểm**: Có thể tăng độ phức tạp ban đầu, tăng số lượng class/interface, và có thể ảnh hưởng đến performance do các lớp trừu tượng.

### Ví Dụ Tổng Hợp Áp Dụng SOLID + Design Patterns

Xây dựng một hệ thống xử lý đơn hàng đơn giản.

```python
from abc import ABC, abstractmethod
from typing import List

# SRP: Mỗi class có một trách nhiệm riêng
class Order:
    def __init__(self, items: List[str], total: float):
        self.items = items
        self.total = total

# ISP: Interface nhỏ và cụ thể
class PaymentProcessor(ABC):
    @abstractmethod
    def process_payment(self, amount: float) -> bool:
        pass

class NotificationSender(ABC):
    @abstractmethod
    def send_notification(self, message: str) -> None:
        pass

# OCP: Mở rộng thông qua inheritance
class CreditCardProcessor(PaymentProcessor):
    def process_payment(self, amount: float) -> bool:
        print(f"Processing ${amount} via Credit Card")
        return True

class PayPalProcessor(PaymentProcessor):
    def process_payment(self, amount: float) -> bool:
        print(f"Processing ${amount} via PayPal")
        return True

class EmailNotification(NotificationSender):
    def send_notification(self, message: str) -> None:
        print(f"Email: {message}")

class SMSNotification(NotificationSender):
    def send_notification(self, message: str) -> None:
        print(f"SMS: {message}")

# Factory Pattern để tạo processors
class PaymentProcessorFactory:
    @staticmethod
    def create_processor(payment_type: str) -> PaymentProcessor:
        if payment_type == "credit_card":
            return CreditCardProcessor()
        elif payment_type == "paypal":
            return PayPalProcessor()
        else:
            raise ValueError(f"Unknown payment type: {payment_type}")

# DIP: Phụ thuộc vào abstraction
class OrderService:
    def __init__(self, payment_processor: PaymentProcessor, 
                 notification_sender: NotificationSender):
        self.payment_processor = payment_processor
        self.notification_sender = notification_sender
    
    def process_order(self, order: Order) -> bool:
        if self.payment_processor.process_payment(order.total):
            self.notification_sender.send_notification(
                f"Order processed successfully for ${order.total}"
            )
            return True
        return False

# Sử dụng
def main():
    order = Order(["Laptop", "Mouse"], 1200.0)
    payment_processor = PaymentProcessorFactory.create_processor("credit_card")
    notification_sender = EmailNotification()
    
    # DI: Inject dependencies
    order_service = OrderService(payment_processor, notification_sender)
    
    success = order_service.process_order(order)
    print(f"Order success: {success}")

if __name__ == "__main__":
    main()
```

## Tổng Kết

Nắm vững các nguyên tắc **SOLID** và **Design Patterns** là một hành trình dài và đòi hỏi thực hành liên tục. Chúng không phải là giáo điều cứng nhắc mà là những kim chỉ nam giúp chúng ta viết code tốt hơn. Điều quan trọng nhất là hiểu được tinh thần đằng sau chúng và biết cách áp dụng một cách linh hoạt.
Ban đầu có thể hơi nhiều kiến thức, nhưng dần dần nó sẽ trở thành phản xạ tự nhiên.

## Happy coding and make your code beautiful!
