# Vấn đề
*Tạo biểu đồ bằng canvas sử dụng ChartJS*
*Kích thước của Canvas là có hạn, ví dụ ChartJS chỉ có thể hiển thị khoảng 1000 điểm biểu đồ đường sử dụng Canvas.*

# Mong muốn
*Hiển thị được nhiều hơn 1000 điểm, ví dụ 2000.*

# Giải pháp
*Tạo một class xử dụng ChartJS ở bên trong, hiển thị danh sách điểm trên nhiều biểu đồ nối tiếp*

**B1: Phân tích các loại biểu đồ nối tiếp**
- Số điểm hiển thị trên một biểu đồ
- Số điểm hiển thị trên hai biểu đồ trở lên
    + Biểu đồ loại 1 (cắt padding đuôi)
    + Biểu đồ loại 2 (cắt padding đầu, cắt padding đuôi)
    + Biểu đồ loại 3 (cắt padding đầu)

**B2: Tạo các biểu đồ theo loại**
Một biểu đồ sẽ gồm các chức năng
- Nhận danh sách đầu vào (dữ liệu, loại biểu đồ)
- Hiển thị dữ liệu
- Biến đổi thành loại tương ứng (cắt padding)

**B3: Tạo lớp container quản lý các biểu đồ con**
Lớp quản lý sẽ gồm các chức năng
- Nhận danh sách đầu vào
- Phân chia dữ liệu cho các biểu đồ con

**B3.1: Chỉ hiện thị những biểu đồ đang xuất hiện trên màn hình (mở rộng)**
- Dựa vào vị trí % scroll left của container, tính được vị trí tương đối của các biểu đồ con đang hiển thị.
- Từ vị trí scroll left của container, kiểm tra biểu đồ có thuộc màn hình đang hiển thị hay không, từ đó sẽ hiển thị.
