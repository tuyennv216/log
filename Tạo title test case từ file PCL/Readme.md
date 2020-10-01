# Hiện tại
*Tạo file PCL để chụp evident cho hoạt động test*
*Vì có rất nhiều test case, lên việc copy bằng tay sẽ tốn nhiều thời gian*

# Mong muốn
*Tạo file script để tự động liệt kê các test case thay vì copy*

# Giải pháp

**B1: Thêm dấu trừ (-, i, o) để xác định dòng tiêu đề, dòng input, dòng output ở một cột mới**
|               |           |Check 1    |Check 2    |Check 3    |       |
|---------------|-----------|:---------:|:---------:|:---------:|:-----:|
|Tiêu đề 1:     |           |           |           |           |i      |
|               |Input 1    |x          |           |           |       |
|               |Input 2    |           |x          |x          |       |
|Tiêu đề 2:     |           |           |           |           |o      |
|               |Input 3    |           |x          |           |       |
|               |Input 4    |x          |           |x          |       |

**B2: Lưu tất cả thông tin vào một đối tượng kiểu tree**
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

# Một số bài toán
- Xác định dòng tiêu đề, dòng input lựa chọn
- Xác định thứ bậc của input thuộc tiêu đề nào và thuộc check thứ mấy
- Duyệt cây để lấy kết quả
