# Vấn đề
*File PCL có rất nhiều test case, vì thế việc copy bằng tay sẽ tốn nhiều thời gian*

# Giải pháp
> Tạo file script để tự động liệt kê các test case thay vì copy

# Thực hiện

**B1: Thêm dấu trừ (-) để xác định tiêu đề ở trường hợp cuối cùng**
|                           |Check 1    |Check 2    |Check 3    |
|---------------------------|:---------:|:---------:|:---------:|
|Tiêu đề 1:                 |           |           |-          |
|   Input 1                 |x          |           |           |
|   Input 2                 |           |x          |x          |
|Tiêu đề 2:                 |           |           |-          |
|   Input 3                 |           |x          |           |
|   Input 4                 |x          |           |x          |

**B2: Lưu tất cả thông tin tiêu đề và input vào một đối tượng kiểu tree**
```
|
|- Tiêu đề 1
|   |- Input 1     [x, , ]
|   |- Input 2     [ ,x,x]
|
|- Tiêu đề 2
    |- Input 3     [ ,x, ]
    |- Input 4     [x, ,x]

```
**B3: Duyệt cây, nếu input nào mà có được đánh dấu x thì in ra kèm theo các tiêu đề phía trước đó**
