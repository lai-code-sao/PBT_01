Phần A:  
Câu A1 - 5 Loại Positioning (tuan_2_css_core/12_css_positioning.md + mục 2, mục 3)   
Position    |Vẫn chiếm chỗ trong flow?  |Tham chiếu vị trí               |Cuộn theo trang?                 |	Use case                  |
static      |   Có                      |	Mặc định        	         |   Có	                           | Mặc định — không cần viết                  |
relative    |	Có                      |	Dịch so với vị trí gốc	     |   Có	                           | Làm anchor cho absolute con, dịch nhẹ              |
absolute    |	Không                   |	Bám vào cha relative gần nhất|   Có                            | Badge, dropdown, tooltip, overlay               |
fixed       |	Có                      |	Bám vào viewport	         |   Không 	                       | Chat button, cookie banner, header cố định        |
sticky      |	Có                      |	Bình thường	                 |   Có khi chưa đến ngưỡng        | Sticky header, sticky table header,sidebar        |   
- `absolute` tham chiếu body khi không có thẻ tổ tiên relative nào gần nó, tham chiếu parent khi cha nó relative. "Nearest positioned ancestor" là phần tử cha, ông hoặc tổ tiên gần nhất ngược lên trên cây DOM có thuộc tính position khác với giá trị mặc định (static).  
