Phần A:  
Câu A1 - 5 Loại Positioning (tuan_2_css_core/12_css_positioning.md + mục 2, mục 3)   
Position|Vẫn chiếm chỗ trong flow?|Tham chiếu vị trí            |Cuộn theo trang?      |Use case                                    |
|---    |---                      |---                          |---                   |---                                         |
static  |Có                       |Mặc định        	            |Có	                   |Mặc định — không cần viết                   |
relative|Có                       |Dịch so với vị trí gốc	    |Có	                   |Làm anchor cho absolute con, dịch nhẹ       |
absolute|Không                    |Bám vào cha relative gần nhất|Có                    |Badge, dropdown, tooltip, overlay           |
fixed   |Không                    |Bám vào viewport	            |Không 	               |Chat button, cookie banner, header cố định  |
sticky  |Có                       |Bình thường	                |Có khi chưa đến ngưỡng|Sticky header, sticky table header, sidebar |   
- `absolute` tham chiếu body khi không có thẻ tổ tiên relative nào gần nó, tham chiếu parent khi cha nó relative. "Nearest positioned ancestor" là phần tử cha, ông hoặc tổ tiên gần nhất ngược lên trên cây DOM có thuộc tính position khác với giá trị mặc định (static).  

Câu A2 - Flexbox vs Grid (tuan_3_css_advanced/13_creating_responsive_layouts.md + mục 3)  
- Trường hợp 1:  
```css
.container { display: flex; }
.item { flex: 1; }
```  
4 items → Bố cục = 4 cột chia đều  
<img src="" alt="Sơ đồ bố cục 4 cột chia đều">

- Trường hợp 2:  
```css
.container { display: flex; flex-wrap: wrap; }
.item { width: 45%; margin: 2.5%; }
```  
6 items → Bố cục = 3 hàng, 2 cột
<img src="" alt="Sơ đồ bố cục 3 hàng, 2 cột">

- Trường hợp 3:  
```css
.container { display: flex; justify-content: space-between; align-items: center; }
```  
3 items → Bố cục = 3 cột, item 1 gắn sát về bên trái, item 2 nằm giữa trục ngang, item 3 gắn sát về bên phải, cả 3 item nằm giữa container theo trục dọc.  
<img src="" alt="Sơ đồ bố cục 3 cột, item 1 gắn sát về bên trái, item 2 nằm giữa trục ngang, item 3 gắn sát về bên phải, cả 3 item nằm giữa container theo trục dọc">

- Trường hợp 4:  
```css
.container { display: grid; grid-template-columns: 200px 1fr 200px; gap: 20px; }
```  
3 items → Bố cục = 3 cột, item 1 và item 3 có độ rộng cố định và bằng nhau, độ rộng còn lại là của item 2 sau khi đã trừ khoảng cách giữa các item.
<img src="" alt="Sơ đồ bố cục 3 cột, item 1 và item 3 có độ rộng cố định và bằng nhau, độ rộng còn lại là của item 2 sau khi đã trừ khoảng cách giữa các item">

- Trường hợp 5:  
```css
.container { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
```  
7 items → Bố cục = 1 hàng item cuối gắn sát về bên phải container.
<img src="" alt="Sơ đồ bố cục 1 hàng item cuối gắn sát về bên phải">

