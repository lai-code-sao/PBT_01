Phần A:  
Câu A1 - 3 Cách nhúng CSS (tuan_2_css_core
/08_introduction_css.md + mục 3 và tuan_2_css_core
/10_inheritance_cascading.md)  
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
