# Vấn đề
*Dựa trên biểu đồ kiểm soát chất lượng X-Bar, hiển thị thêm các đoạn lỗi.*
*Vì số lượng điểm đo lớn và nhiều trường hợp lỗi, cần tối ưu về hiệu năng và tốc độ*

# Mong muốn
*Các đoạn lỗi được hiển thị màu đỏ nối tiếp để có thể nhận biết*

# Giải pháp
*Tìm kiếm các đoạn lỗi trong tập hợp điểm và hiển thị lên biểu đồ*
*Hạn chế lặp nhiều tầng, sử dụng Regular Expression, đa luồng*

**B1: Phân tích các loại lỗi**
*Gồm có 2 loại lỗi chính*
- Điểm đo nằm trong hoặc ngoài vùng xác định (dùng Regular Expression)
- Điểm đo tăng, giảm liên tiếp (dùng lặp)

**B2.1: Tìm điểm đo thuộc loại lỗi 1**
- Chuyển đối số đo của điểm sang vùng tương ứng
- Tạo biểu thức Regex của lỗi
- Tạo thêm các bộ lọc điều kiện của lỗi, như độ dài tối thiếu, thêm các biểu thức Regex khác

**B2.2: Tìm điểm đo thuộc loại lỗi 2**
- Tạo một class quản lý lỗi cần xử lý
- Với từng điểm đo, áp dụng class lỗi đọc và xử lý điểm đo đó
- Thêm các bộ lọc như độ dài

**B3: Thực hiện tìm lỗi**
- Với mỗi class lỗi, cho chạy đa luồng và lưu danh sách trong chính class đó.
- Sau khi các class lỗi chạy xong, tập hợp kết quả trả về
