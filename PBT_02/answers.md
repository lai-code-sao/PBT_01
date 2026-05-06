Phần A:  
Câu A1 - Input Types  
10 input types khác nhau trong HTML5:  
1. type="text" -> Ô nhập text, giới hạn độ dài, kiểm tra nhập đúng định dạng (pattern) -> Dùng cho form đăng ký, đăng nhập
2. type="email" → Ô nhập text, tự kiểm tra có @ → Dùng cho form đăng ký
3. type="password" -> Các ký tự nhập vào được ẩn đi giới hạn độ dài (minlength), kiểm tra nhập đúng định dạng (pattern) -> Dùng cho ô nhập mật khẩu đăng nhập hoặc xác nhận thanh toán
4. type="number" -> Ô nhập có kèm nút chọn tăng/giảm, giới hạn giá trị (min/max), khoảng cách giá trị (step) -> Dùng để chọn số lượng sản phẩm muốn mua trong giỏ hàng
5. type="tel" -> Bàn phím số trên mobile -> Dùng để nhập sôd điện thoại
6. type="date" -> Bảng chọn lịch, giới hạn giá trị -> Dùng cho khách hàng nhập ngày sinh
7. type="time" -> Bảng chọn giờ/phút, giới hạn giá trị -> Dùng để khách hàng chọn khung giờ giao hàng
8. type="color" -> Bảng chọn màu khi click một ô hiển thị màu -> Dùng trong trang quản trị để tùy chỉnh màu sắc giao diện cửa hàng hoặc nhãn dán sản phẩm
9. type="range" -> Một thanh trượt để chọn giá trị trong một khoảng định sẵn, giới hạn giá trị -> Dùng trong bộ lọc tìm kiếm để chọn khoảng giá sản phẩm
10. type="file" -> Cửa sổ duyệt file trên thiết bị, giới hạn định dạng (accept) và số lượng (multiple) ->  Khách hàng tải ảnh hoặc video thực tế khi viết đánh giá (review) sản phẩm

Câu A4 - Media (tuan_1_html5/06_graphics_multimedia.md + mục 3)
1. Thuộc tính loading="lazy" trên thẻ <img>. 
- Cải thiện tốc độ tải của trang web
- Không nên dùng cho những hình ảnh xuất hiện khi vừa mở trang đã thấy
2. 
- Nên cung cấp nhiều <source> trong thẻ <video> vì browser chọn ra cái phù hợp với thiết bị của người dùng  
- 3 format video web phổ biến:
+ <source src="review.webm" type="video/webm"> 
+ <source src="review.mp4" type="video/mp4">
+ <source src="movie.ogv" type="video/ogg">
3.
- Thuộc tính alt trên <img> dùng để mô tả hình ảnh khi ảnh bị lỗi hoặc giúp trình đọc màn hình hiểu nội dung hình ảnh
- alt tốt cho 3 trường hợp:
+ Ảnh sản phẩm iPhone 16 -> alt="iPhone 16 Pro Max 265GB màu Titan"
+ Ảnh trang trí (decorative) -> alt=""
+ Ảnh biểu đồ doanh thu Q1/2026 -> alt="Biểu đồ đường hiển thị doanh thu quý 1 năm 2026 có xu hướng tăng"
Câu A5 - So sánh <figure> vs <img> (tuan_1_html5/06_graphics_multimedia.md + mục 3)  
- Dùng Cách 1 khi ảnh chỉ mang tính chất trang trí hoặc minh họa nhỏ lẻ không cần chú thích
- Dùng Cách 2 khi ảnh là một phần quan trọng của nội dung bài viết và cần có tiêu đề hoặc chú thích bên dưới  
2 ví dụ thực tế cho mỗi cách:  
Cách 1:  
VD 1: Logo thương hiệu trên thanh điều hướng  
```html
<a href="index.html">
  <img src="images/logo-tlu.png" alt="Logo Đại học Thủy Lợi" width="50">
</a>
```  
VD 2: Icon chức năng trong giỏ hàng  
```html
<button>
  <img src="images/cart-icon.png" alt="" width="20"> 
  Thêm vào giỏ hàng
</button>
```  
Cách 2:  
VD 1: Chi tiết sản phẩm thời trang  
```html
<figure>
    <img src="images/ao-somi.jpg" alt="Áo sơ mi nam màu trắng">
    <figcaption>Hình 1: Chất liệu vải cotton thoáng mát, phù hợp cho mùa hè.</figcaption>
</figure> 
```   
VD 2: Biểu đồ trong báo cáo hệ thống  
```html
<figure style="text-align: center;">
    <img src="images/use-case-diagram.png" alt="Sơ đồ Use Case quản lý thư viện">
    <figcaption>Biểu đồ 2.1: Các tương tác chính của thủ thư và sinh viên với hệ thống.</figcaption>
</figure> 
```   