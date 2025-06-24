# Week3_AIO Blog

# I. Cấu trúc dữ liệu cơ bản: Stack, Queue và Tree

## Giới thiệu

Trong thế giới lập trình, việc lựa chọn cấu trúc dữ liệu phù hợp có thể quyết định sự thành công hay thất bại của một chương trình. Hôm nay, chúng ta sẽ cùng khám phá ba cấu trúc dữ liệu quan trọng: **Stack**, **Queue** và **Tree** - những nền tảng không thể thiếu trong khoa học máy tính.

## Cấu trúc dữ liệu là gì?

Cấu trúc dữ liệu là một phương pháp tổ chức và lưu trữ dữ liệu trong máy tính, cho phép truy cập và cập nhật dữ liệu một cách hiệu quả. Nó không chỉ đơn thuần là nơi chứa dữ liệu mà còn xác định các mối quan hệ giữa các phần tử dữ liệu và các thao tác có thể thực hiện trên chúng. Việc lựa chọn cấu trúc dữ liệu phù hợp có thể ảnh hưởng đáng kể đến hiệu suất của một chương trình hoặc hệ thống.1
Trong môi trường lập trình Python, có hai loại cấu trúc dữ liệu chính. Loại thứ nhất là các cấu trúc dữ liệu tích hợp sẵn, bao gồm List, Dictionary, Tuple và Set, được cung cấp sẵn bởi ngôn ngữ. Loại thứ hai là các cấu trúc dữ liệu do người dùng định nghĩa, như Stack, Queue, Tree, Graph và Linked List, được xây dựng để giải quyết các vấn đề cụ thể hoặc tối ưu hóa các loại thao tác dữ liệu nhất định.1 Báo cáo này sẽ tập trung vào ba trong số các cấu trúc dữ liệu do người dùng định nghĩa này: Stack, Queue và Tree, là những nền tảng quan trọng trong khoa học máy tính.

## Tại sao cần các cấu trúc dữ liệu phi tuyến tính?

Các cấu trúc dữ liệu tuyến tính, chẳng hạn như mảng (arrays) và danh sách liên kết (linked lists), lưu trữ dữ liệu theo một trình tự tuần tự. Điều này có nghĩa là để tìm kiếm một phần tử cụ thể, hệ thống thường phải duyệt qua từng phần tử một từ đầu đến cuối danh sách. Cách tiếp cận tuần tự này dẫn đến hiệu suất tìm kiếm kém hiệu quả, đặc biệt khi làm việc với các tập dữ liệu lớn, với độ phức tạp thời gian thường là O(N) (N là số lượng phần tử).1
Nhu cầu về khả năng tìm kiếm và tổ chức dữ liệu hiệu quả hơn là động lực chính cho sự phát triển của các cấu trúc dữ liệu phi tuyến tính như Tree. Bằng cách tổ chức dữ liệu theo một hệ thống phân cấp thay vì tuần tự, Tree cho phép các thuật toán tìm kiếm loại bỏ nhanh chóng các phần lớn của không gian tìm kiếm ở mỗi bước. Điều này giúp đạt được hiệu suất vượt trội, thường là O(log N) trong trường hợp lý tưởng, so với các cấu trúc tuyến tính.1 Sự thay đổi cơ bản từ truy cập tuần tự sang truy cập phân cấp là một nguyên tắc cốt lõi trong thiết kế thuật toán hiệu quả. Nó minh họa rằng việc lựa chọn cấu trúc dữ liệu không phải là ngẫu nhiên mà được thúc đẩy trực tiếp bởi các yêu cầu về hiệu suất của các thao tác phổ biến, như tìm kiếm.



### Tại sao cần các cấu trúc dữ liệu phi tuyến tính?

Các cấu trúc dữ liệu tuyến tính như mảng và danh sách liên kết lưu trữ dữ liệu theo trình tự tuần tự, dẫn đến hiệu suất tìm kiếm kém với độ phức tạp O(N). Các cấu trúc phi tuyến tính như Tree cho phép tìm kiếm hiệu quả hơn với độ phức tạp O(log N) trong trường hợp lý tưởng.

---

## 1. Stack (Ngăn xếp) - Nguyên tắc LIFO

### Định nghĩa

**Stack** là cấu trúc dữ liệu tuyến tính tuân theo nguyên tắc **LIFO (Last-In, First-Out)** - "Vào sau, ra trước". Hình dung như một chồng đĩa: đĩa được đặt lên cuối cùng sẽ là đĩa đầu tiên được lấy ra.

### Các thao tác cơ bản

- **PUSH**: Thêm phần tử vào đỉnh Stack
- **POP**: Xóa và trả về phần tử ở đỉnh Stack
- **PEEK**: Xem giá trị phần tử ở đỉnh mà không xóa
- **is_empty**: Kiểm tra Stack có rỗng không
- **is_full**: Kiểm tra Stack có đầy không (với Stack có giới hạn)

### Triển khai Stack bằng Python List

```python
# Triển khai Stack sử dụng List trong Python
print("--- Triển khai Stack sử dụng List ---")
my_stack = []

# Thao tác PUSH: Thêm phần tử vào đỉnh Stack
my_stack.append('A')
my_stack.append('B')
my_stack.append('C')
print("Stack sau khi PUSH 'A', 'B', 'C':", my_stack)  # ['A', 'B', 'C']

# Thao tác PEEK: Xem phần tử ở đỉnh
if my_stack:
    top_element = my_stack[-1]
    print("Phần tử ở đỉnh (PEEK):", top_element)  # C

# Thao tác POP: Xóa và trả về phần tử ở đỉnh Stack
if my_stack:
    popped_element = my_stack.pop()
    print("Phần tử được POP:", popped_element)  # C
print("Stack sau khi POP:", my_stack)  # ['A', 'B']

# Kiểm tra Stack rỗng
print("Stack có rỗng không?", not bool(my_stack))  # False

# POP hết các phần tử
my_stack.pop()  # B
my_stack.pop()  # A
print("Stack sau khi POP hết:", my_stack)  # []
print("Stack có rỗng không?", not bool(my_stack))  # True
```

### Ứng dụng thực tế của Stack

1. **Duyệt cây theo chiều sâu (DFS)**: Quản lý việc quay lui trong quá trình duyệt
2. **Quản lý hàm gọi (Call Stack)**: Theo dõi thứ tự các hàm được gọi
3. **Hoàn tác/Làm lại (Undo/Redo)**: Lưu trữ lịch sử hành động
4. **Kiểm tra cân bằng dấu ngoặc**: Xác định các cặp ngoặc khớp nhau

---

## 2. Queue (Hàng đợi) - Nguyên tắc FIFO

### Định nghĩa

**Queue** là cấu trúc dữ liệu tuyến tính tuân theo nguyên tắc **FIFO (First-In, First-Out)** - "Vào trước, ra trước". Giống như hàng người chờ đợi: người đến trước sẽ được phục vụ trước.

### Các thao tác cơ bản

- **enqueue**: Thêm phần tử vào cuối hàng đợi (rear)
- **dequeue**: Loại bỏ phần tử từ đầu hàng đợi (front)
- **peek**: Xem phần tử ở đầu hàng đợi mà không loại bỏ
- **is_empty**: Kiểm tra hàng đợi có trống không
- **is_full**: Kiểm tra hàng đợi có đầy không

### Triển khai Queue bằng Python List (lưu ý hiệu suất)

```python
# Triển khai Queue sử dụng List (Lưu ý hiệu suất)
print("--- Triển khai Queue sử dụng List ---")
my_queue_list = []

# Thao tác enqueue: Thêm phần tử vào cuối hàng đợi
my_queue_list.append(10)
my_queue_list.append(20)
my_queue_list.append(30)
print("Queue sau khi enqueue:", my_queue_list)  # [10, 20, 30]

# Thao tác PEEK: Xem phần tử ở đầu hàng đợi
if my_queue_list:
    front_element = my_queue_list[0]
    print("Phần tử ở đầu (PEEK):", front_element)  # 10

# Thao tác dequeue: Loại bỏ phần tử từ đầu hàng đợi
if my_queue_list:
    dequeued_element = my_queue_list.pop(0)  # O(N) operation!
    print("Phần tử được Dequeue:", dequeued_element)  # 10
print("Queue sau khi dequeue:", my_queue_list)  # [20, 30]
```

> **⚠️ Lưu ý**: Sử dụng `list.pop(0)` có độ phức tạp O(N) vì cần dịch chuyển tất cả phần tử còn lại!

### Triển khai Queue bằng collections.deque (Khuyến nghị)

```python
from collections import deque

# Triển khai Queue sử dụng collections.deque
print("--- Triển khai Queue sử dụng collections.deque ---")
my_queue_deque = deque()

# Thao tác enqueue
my_queue_deque.append(100)
my_queue_deque.append(200)
my_queue_deque.append(300)
print("Queue sau khi enqueue:", my_queue_deque)  # deque([100, 200, 300])

# Thao tác PEEK
if my_queue_deque:
    print("Phần tử ở đầu (PEEK):", my_queue_deque[0])  # 100

# Thao tác dequeue
if my_queue_deque:
    dequeued_element = my_queue_deque.popleft()  # O(1) operation!
    print("Phần tử được Dequeue:", dequeued_element)  # 100
print("Queue sau khi dequeue:", my_queue_deque)  # deque([200, 300])
```

### So sánh hiệu suất

| Đặc điểm | collections.deque | list |
|----------|-------------------|------|
| Thêm vào cuối (append) | O(1) | O(1) |
| Xóa từ đầu (popleft/pop(0)) | O(1) | O(N) |
| Import module | Cần import | Built-in |

### Ứng dụng thực tế của Queue

1. **Duyệt cây theo chiều rộng (BFS)**: Thăm các nút theo từng cấp độ
2. **Quản lý tác vụ hệ điều hành**: Xếp hàng các tiến trình chờ xử lý
3. **Mô phỏng sự kiện**: Xử lý sự kiện theo thứ tự thời gian
4. **Xử lý dữ liệu luồng**: Xử lý dữ liệu đến liên tục

---

## 3. Tree (Cây) - Cấu trúc phi tuyến tính

### Định nghĩa

**Tree** là cấu trúc dữ liệu phi tuyến tính trong đó các nút được tổ chức theo hệ thống phân cấp, biểu diễn mối quan hệ "cha-con" giữa các phần tử dữ liệu. Tree cho phép tìm kiếm, chèn và xóa hiệu quả hơn nhiều so với cấu trúc tuyến tính.

### Các thuật ngữ cơ bản

- **Root (Nút gốc)**: Nút trên cùng của cây, không có nút cha
- **Edge (Cạnh)**: Liên kết giữa hai nút, biểu thị mối quan hệ cha-con
- **Parent Node (Nút cha)**: Nút có một hoặc nhiều nút con
- **Child Node (Nút con)**: Nút nằm trực tiếp bên dưới một nút cha
- **Leaf Node (Nút lá)**: Nút không có nút con nào
- **Depth (Độ sâu)**: Số cạnh từ nút gốc đến nút đó
- **Height (Chiều cao)**: Độ dài đường đi dài nhất từ nút đến nút lá
- **Subtree (Cây con)**: Bất kỳ nút nào cùng với các nút con cháu
- **Siblings (Anh chị em)**: Các nút có cùng nút cha

### Triển khai Tree cơ bản trong Python

```python
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.children = []  # Danh sách các nút con
        self.parent = None  # Tham chiếu đến nút cha

    def add_child(self, child_node):
        """Thêm một nút con vào nút hiện tại."""
        child_node.parent = self
        self.children.append(child_node)

    def get_level(self):
        """Trả về độ sâu của nút trong cây."""
        level = 0
        p = self.parent
        while p:
            level += 1
            p = p.parent
        return level

    def print_tree(self):
        """In cấu trúc cây trực quan."""
        spaces = '  ' * self.get_level()
        prefix = spaces + "|__" if self.parent else ""
        print(prefix + str(self.data))
        
        if self.children:
            for child in self.children:
                child.print_tree()

# Xây dựng cây ví dụ
root = TreeNode("Global")

vietnam = TreeNode("Vietnam")
usa = TreeNode("USA")
root.add_child(vietnam)
root.add_child(usa)

hanoi = TreeNode("Hanoi")
hcm = TreeNode("Ho Chi Minh")
vietnam.add_child(hanoi)
vietnam.add_child(hcm)

new_york = TreeNode("New York")
california = TreeNode("California")
usa.add_child(new_york)
usa.add_child(california)

print("Cấu trúc cây ví dụ:")
root.print_tree()
```

### Ứng dụng thực tế của Tree

1. **File Explorer**: Cấu trúc thư mục và tệp hệ điều hành
2. **Database**: B-trees, B+ trees để tổ chức dữ liệu và chỉ mục
3. **HTML DOM**: Biểu diễn cấu trúc tài liệu HTML
4. **Machine Learning**: Decision Tree, K-D Tree cho các thuật toán AI

---

## 4. Binary Tree (Cây nhị phân)

### Định nghĩa

**Binary Tree** là trường hợp đặc biệt của Tree, trong đó mỗi nút có tối đa hai nút con: **con trái (left child)** và **con phải (right child)**.

### Các loại Binary Tree

1. **Skew Tree (Cây xiên)**: Tất cả nút chỉ có con trái hoặc con phải
2. **Full Binary Tree**: Mỗi nút có 0 hoặc 2 con
3. **Balanced Binary Tree**: Chênh lệch chiều cao giữa cây con trái và phải ≤ 1

> **💡 Quan trọng**: Hiệu suất lý tưởng O(log N) chỉ đạt được khi cây cân bằng!

### Chèn node vào Binary Tree

```python
from collections import deque

class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

def insert_node_binary_tree(root, key):
    """Chèn node mới bằng Level-Order Traversal (BFS)"""
    new_node = Node(key)
    if root is None:
        return new_node
    
    queue = deque([root])
    while queue:
        temp = queue.popleft()
        
        # Kiểm tra con trái
        if temp.left is None:
            temp.left = new_node
            return root
        else:
            queue.append(temp.left)
        
        # Kiểm tra con phải
        if temp.right is None:
            temp.right = new_node
            return root
        else:
            queue.append(temp.right)
    
    return root

def inorder_traversal(node):
    """Duyệt cây theo thứ tự Inorder"""
    if node:
        inorder_traversal(node.left)
        print(node.data, end=" ")
        inorder_traversal(node.right)

# Ví dụ sử dụng
root_bt = Node(1)
root_bt.left = Node(2)
root_bt.right = Node(3)
root_bt.left.left = Node(4)
root_bt.left.right = Node(5)

print("Cây ban đầu (Inorder):", end=" ")
inorder_traversal(root_bt)  # 4 2 5 1 3
print()

# Chèn node mới
root_bt = insert_node_binary_tree(root_bt, 6)
print("Sau khi chèn 6:", end=" ")
inorder_traversal(root_bt)  # 4 2 5 1 3 6
print()
```

---

## 5. Binary Search Tree (BST) - Cây tìm kiếm nhị phân

### Định nghĩa và thuộc tính

**BST** là Binary Tree đặc biệt tuân theo quy tắc sắp xếp:
- Tất cả nút con trái < nút gốc
- Tất cả nút con phải ≥ nút gốc

### Thuật toán tìm kiếm trong BST

```python
class NodeBST:
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None

def insert_bst(root, key):
    """Chèn node vào BST duy trì thuộc tính sắp xếp"""
    if root is None:
        return NodeBST(key)
    
    if key < root.key:
        root.left = insert_bst(root.left, key)
    elif key >= root.key:
        root.right = insert_bst(root.right, key)
    
    return root

def search_bst(root, key):
    """Tìm kiếm node trong BST"""
    # Trường hợp cơ sở
    if root is None or root.key == key:
        return root
    
    # Key lớn hơn -> tìm bên phải
    if key > root.key:
        return search_bst(root.right, key)
    
    # Key nhỏ hơn -> tìm bên trái
    return search_bst(root.left, key)

def inorder_traversal_bst(node):
    """Duyệt BST theo Inorder (cho kết quả đã sắp xếp)"""
    if node:
        inorder_traversal_bst(node.left)
        print(node.key, end=" ")
        inorder_traversal_bst(node.right)

# Xây dựng BST ví dụ
root_bst = None
keys = [50, 30, 70, 20, 40, 60, 80]

for key in keys:
    root_bst = insert_bst(root_bst, key)

print("BST (Inorder - đã sắp xếp):", end=" ")
inorder_traversal_bst(root_bst)  # 20 30 40 50 60 70 80
print()

# Tìm kiếm
search_key = 40
result = search_bst(root_bst, search_key)
if result:
    print(f"Tìm thấy khóa {search_key} trong BST")
else:
    print(f"Không tìm thấy khóa {search_key} trong BST")
```

### Độ phức tạp thời gian BST

- **Trường hợp tốt nhất (cây cân bằng)**: O(log N)
- **Trường hợp xấu nhất (cây thoái hóa)**: O(N)

---

# Cây Trong Khoa Học Máy Tính: Thuật Toán Duyệt và Cây Nhị Phân

## Giới Thiệu

Cây là một trong những cấu trúc dữ liệu quan trọng nhất trong khoa học máy tính. Chúng được sử dụng rộng rãi trong nhiều ứng dụng từ cơ sở dữ liệu đến thuật toán tìm kiếm. Bài viết này sẽ khám phá các khái niệm cơ bản về cây, các thuật toán duyệt cây, và đặc biệt tập trung vào cây nhị phân tìm kiếm (Binary Search Tree - BST).

## I. Thuật Toán Duyệt Cây

### 1. Depth-First Search (DFS) - Duyệt Ưu Tiên Chiều Sâu

DFS bắt đầu từ gốc và đi sâu nhất có thể theo mỗi nhánh trước khi quay lui (backtracking). Vì lý thuyết, nó sử dụng cấu trúc **Stack (Last In, First Out)** để theo dõi các nút cần thăm.

```python
visited = set()

def dfs(node, graph, visited_nodes):
    print(node, end=' ')
    visited_nodes.add(node)
    
    for u in graph[node]:
        if u not in visited_nodes:
            dfs(u, graph, visited_nodes)
```

**Đặc điểm của DFS:**
- Sử dụng bộ nhớ ít hơn so với BFS trong nhiều trường hợp
- Phù hợp để tìm đường đi trong mê cung
- Có thể bị mắc kẹt trong các chu trình vô hạn nếu không xử lý đúng

### 2. Breadth-First Search (BFS) - Duyệt Ưu Tiên Chiều Rộng

Ngược lại với DFS, BFS duyệt tất cả các nút ở cùng một "tầng" (level) trước khi chuyển xuống tầng tiếp theo. Vì lý thuyết, nó sử dụng cấu trúc **Queue (First In, First Out)**.

**Đặc điểm của BFS:**
- Đảm bảo tìm được đường đi ngắn nhất trong đồ thị không có trọng số
- Sử dụng nhiều bộ nhớ hơn DFS
- Phù hợp để tìm kiếm theo từng lớp

## II. Cây Nhị Phân (Binary Tree)

Cây nhị phân là một loại cây đặc biệt mà mỗi nút có tối đa 2 con: **left child** và **right child**.

### Khái Niệm Cân Bằng (Balance)

Một khái niệm quan trọng là tính **balance (cân bằng)**. Một cây nhị phân được gọi là cân bằng nếu chiều cao giữa cây con trái và cây con phải của bất kỳ nút nào không quá 1.

**Tại sao tính balance quan trọng?**
- Cây bị "lệch" (skewed) sẽ mất tính năng tìm kiếm nhanh
- Trong trường hợp xấu nhất, cây có thể trở thành một danh sách liên kết, làm cho việc tìm kiếm mất O(n) thời gian thay vì O(log n)

### Các Thao Tác Trên Cây Nhị Phân

#### Kiểm Tra Cân Bằng
```python
def is_balanced(root):
    def check_height(node):
        if not node:
            return 0
        
        left_height = check_height(node.left)
        if left_height == -1:
            return -1
            
        right_height = check_height(node.right)
        if right_height == -1:
            return -1
            
        if abs(left_height - right_height) > 1:
            return -1
            
        return max(left_height, right_height) + 1
    
    return check_height(root) != -1
```

#### Các Thao Tác Cơ Bản:

**Chèn một nút (Insertion):** Có thể chèn một nút mới vào vị trí thích hợp để duyệt DFS.

**Xóa một nút (Deletion):**
1. **Tìm nút cần xóa**
2. **Tìm nút đại ở ngoài cùng bên phải của cây**
3. **Thay thế giá trị nút cần xóa bằng giá trị nút đại nhất**
4. **Xóa nút đại nhất đó**

### Hạn Chế

Cây nhị phân thông thường không đảm bảo tìm kiếm nhanh. Khi đồng ở một nút, chúng ta không biết nên đi sang phải hay trái để tìm giá trị cần thiết, vì không có quy tắc sắp xếp nào.

## III. Cây Nhị Phân Tìm Kiếm (Binary Search Tree - BST)

BST là một cây nhị phân có thêm các quy tắc rằng:
- **Tất cả các nút trong cây con bên trái** đều nhỏ hơn giá trị của nút N
- **Tất cả các nút trong cây con bên phải** đều lớn hơn hoặc bằng giá trị của nút N

### Cài Đặt BST

```python
class BST:
    def __init__(self):
        # Constructor
        pass
    
    def insert(self, key):
        if self.root is None:
            self.root = TreeNode(key)
        else:
            self._insert(self.root, key)
    
    def _insert(self, node, key):
        if key < node.val:
            if node.left is None:
                node.left = TreeNode(key)
            else:
                self._insert(node.left, key)
        else:
            if node.right is None:
                node.right = TreeNode(key)
            else:
                self._insert(node.right, key)
    
    def search(self, key):
        return self._search(self.root, key)
    
    def _search(self, node, key):
        if node is None or node.val == key:
            return node
        if key < node.val:
            return self._search(node.left, key)
        else:
            return self._search(node.right, key)
```

### Ưu Điểm của BST

1. **Tìm kiếm hiệu quả:** O(log n) trong trường hợp tốt nhất
2. **Thêm và xóa nhanh:** O(log n) cho các thao tác cơ bản
3. **Duyệt có thứ tự:** In-order traversal cho ra dãy số đã sắp xếp
4. **Linh hoạt:** Dễ dàng thực hiện các thao tác như tìm min/max

### Nhược Điểm của BST

1. **Có thể mất cân bằng:** Trong trường hợp xấu nhất, BST có thể trở thành danh sách liên kết
2. **Hiệu suất phụ thuộc vào thứ tự chèn:** Nếu dữ liệu được chèn theo thứ tự, cây sẽ bị lệch
3. **Không tự cân bằng:** Cần các biến thể như AVL Tree hoặc Red-Black Tree để đảm bảo cân bằng

# SQL Nâng Cao cho Phân Tích Dữ Liệu: Từ Join đến Data Mining

SQL là nền tảng của phân tích dữ liệu, và việc thành thạo các kỹ thuật nâng cao có thể thay đổi hoàn toàn cách bạn làm việc với cơ sở dữ liệu. Bài viết này sẽ giới thiệu những khái niệm SQL nâng cao mà mọi nhà phân tích dữ liệu cần biết.

## SQL Join: Kết Nối Dữ Liệu

### Inner Join
Loại join phổ biến nhất, kết nối các bảng dựa trên giá trị khớp:

```sql
SELECT order_id, first_name, last_name
FROM orders o
INNER JOIN customers c ON o.customer_id = c.customer_id;
```

### Self Join
Khi cần tham chiếu cùng một bảng hai lần, ví dụ tìm nhân viên và quản lý của họ:

```sql
SELECT 
    e.first_name AS nhan_vien,
    m.first_name AS quan_ly
FROM employees e
JOIN employees m ON e.reports_to = m.employee_id;
```

### Outer Join
- **LEFT JOIN**: Trả về tất cả bản ghi từ bảng bên trái
- **RIGHT JOIN**: Trả về tất cả bản ghi từ bảng bên phải

Hoàn hảo để tìm khách hàng chưa đặt hàng hoặc các tình huống tương tự.

## Kỹ Thuật Query Nâng Cao

### Common Table Expressions (CTEs)
CTE giúp các query phức tạp dễ đọc hơn bằng cách chia thành các bước logic:

```sql
WITH thong_ke_khach_hang AS (
    SELECT customer_id, COUNT(*) as so_don_hang
    FROM orders
    GROUP BY customer_id
)
SELECT * FROM thong_ke_khach_hang WHERE so_don_hang > 5;
```

### Subqueries (Truy vấn con)
Query trong query - hữu ích để lọc dựa trên dữ liệu tổng hợp:

```sql
SELECT * FROM products 
WHERE price > (SELECT AVG(price) FROM products);
```

### Temporary Tables (Bảng tạm)
Lưu trữ kết quả trung gian cho phân tích nhiều bước phức tạp:

```sql
CREATE TEMPORARY TABLE temp_ban_hang AS
SELECT product_id, SUM(quantity) as tong_ban
FROM order_items
GROUP BY product_id;
```

## Lập Trình Cơ Sở Dữ Liệu

### Stored Procedures (Thủ tục lưu trữ)
Khối mã có thể tái sử dụng, nhận tham số và thực hiện các thao tác phức tạp:

```sql
DELIMITER //
CREATE PROCEDURE LayTopKhachHang(IN n INT)
BEGIN
    SELECT customer_id, first_name, COUNT(*) as so_don
    FROM customers c
    JOIN orders o ON c.customer_id = o.customer_id
    GROUP BY customer_id
    ORDER BY so_don DESC
    LIMIT n;
END //
```

### Triggers (Kích hoạt)
Hành động tự động khi dữ liệu thay đổi:

```sql
CREATE TRIGGER kiem_tra_thay_doi_nhan_vien
AFTER UPDATE ON employees
FOR EACH ROW
INSERT INTO nhat_ky_nhan_vien (employee_id, ngay_thay_doi, luong_cu, luong_moi)
VALUES (NEW.employee_id, NOW(), OLD.salary, NEW.salary);
```

## Ứng Dụng Thực Tế

### Phân Khúc Khách Hàng với UNION
Phân loại khách hàng theo mức hiệu suất:

```sql
SELECT customer_id, first_name, points, 'Đồng' AS hang
FROM customers WHERE points < 2000
UNION
SELECT customer_id, first_name, points, 'Bạc' AS hang  
FROM customers WHERE points BETWEEN 2000 AND 3000
UNION
SELECT customer_id, first_name, points, 'Vàng' AS hang
FROM customers WHERE points > 3000;
```

### USING Clause cho Join Gọn Gàng
Khi các cột join có tên giống nhau:

```sql
SELECT c.customer_id, c.first_name, o.order_id
FROM customers c
JOIN orders o USING (customer_id);
```

## Tích Hợp Data Mining

Phân tích dữ liệu hiện đại thường kết hợp SQL với các công cụ chuyên dụng như RapidMiner để:

### Phân Loại (Classification)
Sử dụng cây quyết định để dự đoán hành vi khách hàng:
- Xác định khách hàng VIP dựa trên tần suất thuê
- Dự đoán khả năng khách hàng tiếp tục sử dụng dịch vụ

### Phân Cụm (Clustering)
Nhóm khách hàng theo đặc điểm tương tự để:
- Tối ưu hóa chiến lược marketing
- Cá nhân hóa dịch vụ

## Case Study: Hệ Thống Cho Thuê Phim Sakila

Cơ sở dữ liệu Sakila minh họa ứng dụng thực tế của SQL nâng cao:

### Phân Tích Hành Vi Khách Hàng
```sql
-- Top 10 khách hàng thuê nhiều nhất
SELECT c.customer_id, c.first_name, c.last_name, COUNT(*) as so_lan_thue
FROM customer c
JOIN rental r ON c.customer_id = r.customer_id
GROUP BY c.customer_id
ORDER BY so_lan_thue DESC
LIMIT 10;
```

### Phân Tích Doanh Thu
```sql
-- Doanh thu hàng tháng theo cửa hàng
SELECT s.store_id, DATE_FORMAT(p.payment_date, '%Y-%m') as thang,
       SUM(p.amount) as doanh_thu
FROM payment p
JOIN staff st ON p.staff_id = st.staff_id
JOIN store s ON st.store_id = s.store_id
GROUP BY s.store_id, thang
ORDER BY thang, doanh_thu DESC;
```



