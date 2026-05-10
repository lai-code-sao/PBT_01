Phần A:  
Câu A1 - 3 Cách nhúng CSS (tuan_2_css_core
/08_introduction_css.md + mục 3 và tuan_2_css_core
/10_inheritance_cascading.md + mục 3)  
1. Inline CSS — trong attribute style:
- VD: 
```html
<h1 style="color: #32c463; font-size: 30px; font-family: 'Courier New', Courier, monospace;">Tiêu đề</h1>
```
- Ưu điểm:  
    + Kích hoạt nhanh chóng cho một phần tử duy nhất.
    + Có độ ưu tiên cao nhất (ghi đè tất cả các cách khác).
    + Hữu ích khi test nhanh.
- Nhược điểm: Code cực kỳ rối và lặp lại -> khó bảo trì.
- Chỉ dùng khẩn cấp / override tạm thời.  
2. Internal CSS — trong thẻ `<style>`:
- VD: 
```html
<head>
    <style>
        h2{
            font-weight: bold;
            color: #a4b93a; 
            font-size: 32px; 
        }
    </style>
</head>
```
- Ưu điểm: Không cần tạo file riêng, tiện cho các trang web chỉ có duy nhất một trang.  
- Nhược điểm:  
    + Khó bảo trì: Nếu dự án có nhiều trang, bạn phải copy đoạn code này sang từng file. Khi cần sửa màu, bạn phải đi lục từng file một.
    + Làm tăng dung lượng file HTML.  
- Dùng cho prototype hoặc trang đơn.    
3. External CSS — file riêng:
- VD: 
```html
<!--index.html-->
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```
```css
/* styles.css */
h1 { color: #2563eb; font-size: 32px; }
```  
- Ưu điểm:  
    + Caching: Browser cache file CSS → trang thứ 2, thứ 3 load ngay, không tải CSS lại.  
    + Tái sử dụng: Dùng cùng 1 file CSS cho nhiều trang — sửa 1 chỗ = đổi toàn bộ site.  
    + Maintainability: Tách HTML (structure) và CSS (presentation) → team làm song song được.  
    + Performance: Minified CSS (xóa space, comment) → file nhỏ hơn → load nhanh hơn.  
- Nhược điểm: Tạo thêm một yêu cầu tải file, nếu file quá nặng hoặc mạng chậm có thể khiến trang web hiện ra mà chưa có định dạng trong giây lát.  
- Dùng cho mọi dự án thật.   

Nếu cùng 1 element có cả 3 cách CSS đồng thời áp dụng, cách viết sau cùng "thắng" vì trình duyệt phân tích từ trên xuống dưới.  

Câu A2 -  CSS Selectors — Dự đoán kết quả (tuan_2_css_core
/09_css_selectors.md + mục 2, mục 3)  
1. `h1 `                    → Chọn: Tất cả thẻ `<h1>`
2. `.price`                 → Chọn: Thẻ có class="price"
3. `#app header`            → Chọn: Thẻ header nằm trong thẻ có id="app" 
4. `nav a:first-child`      → Chọn: Thẻ `<a>` là con đầu tiên nằm trong thẻ `<nav>`
5. `.product.featured h2`   → Chọn: Thẻ `<h2>` nằm trong thẻ có class="product featured"
6. `article > p`            → Chọn: Thẻ `<p>` là con trực tiếp của thẻ `article`
7. `a[href="/"]`            → Chọn: Thẻ `<a>` có thuộc tính href="/"
8. `.top-bar.dark h1`       → Chọn: Thẻ `<h1>` nằm trong thẻ có class="top-bar dark"  
<img src="/PBT_03/images/selectors_test.png" alt="Ảnh kiểm chứng đáp án">  

Câu A3 - Box Model — Tính toán kích thước (tuan_2_css_core
/11_box_model.md + mục 3)  
TH1: content-box  
→ Chiều rộng hiển thị = 400+20x2+5x2 = 450px  
→ Không gian chiếm trên trang = 450+10x2 = 470px  
TH2: border-box  
→ Chiều rộng hiển thị = 400px  
→ Kích thước content thực tế = 400-20x2-5x2 = 350px  
→ Không gian chiếm trên trang = 400+10x2 = 420px  
TH3: Margin collapse  
→ Khoảng cách giữa box-a và box-b = 40px  
→ KHÔNG PHẢI 65px vì margin collapse nên margin dọc giữa 2 block element GỘPLẠI = lấy cái LỚN HƠN  

Nếu .box-a có margin-bottom: -10px và .box-b có margin-top: 40px, khoảng cách = 40px  

Câu A4 - Specificity (tuan_2_css_core
/09_css_selectors.md + mục 3)  
1. Tính specificity score cho mỗi rule:
Rule A: `p` = 0-0-1 = 1  
Rule B: `.price` = 0-1-0 = 10
Rule C: `#main-price` = 1-0-0 = 100
Rule D: `p.price` = 0-1-1 = 11
2. Element sẽ có màu đỏ vì specificity 100 cao nhất.  
3. Nếu thêm ```html<p class="price" id="main-price" style="color: orange;">```, element có màu cam.  
4. Nếu Rule A thêm `!important`, element có màu đen vì `!important` có  specificity vô hạn.  