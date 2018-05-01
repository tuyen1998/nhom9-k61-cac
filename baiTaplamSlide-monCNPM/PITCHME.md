### THIẾT KẾ MỨC CAO
### (HIGH LEVEL DESIGN) (Tiếp)
---

#### REST Development
#### COUPLING
#### COHESION
#### Design Principles: SOLID
---

### REST Development
- Khoảng những năm 1970 xuất hiện 1 giải pháp truyền tin hướng có tên là RPC.
- RPC viết tắt của cụm từ Remote Procedure Calls (tạm dịch là các cuộc gọi thủ tục từ xa).
---

### REST Development
- Nó tồn tại rất nhiều vấn đề như:

 1) Không linh hoạt thay đổi kể từ khi nó giả định một mối quan hệ tĩnh giữa máy khách và máy chủ tại thời gian chạy, điều này gây ra các mã số máy khách và máy chủ được kết chặt chẽ với nhau,
 
 2) RPC được dựa trên mô hình lập trình thủ tục/ cấu trúc, nó đã lỗi thời với các mô hình hướng đối tượng,
 
 3) RPC thiếu minh bạch vị trí.
 
---

### REST Development
**Mô hình RPC(Remote Procedure Calls)**
![alt](http://pubs.opengroup.org/onlinepubs/9629399/c7060601.gif)

---

### REST Development
- Trong thiết kế mức cao, local machine gửi yêu cầu tới remote service
- Khi yêu cầu được tính toán, nó sẽ được gửi đi và gửi phản hồi trở lại local service.
---

### REST Development
- REST (Representational State Transfer) là một kiến trúc phần mềm cho các ứng dụng hypermedia phân tán
- REST được Roy Fielding phát minh vào những năm 1990
---

### REST Development
- Thiết kế cốt lõi quyết định REST là:

 1) Được lựa chọn để giải quyết nhiều thách thức cơ bản mà hệ thống phần mềm dựa trên web gặp phải,

 2) Cung cấp một giao diện thống nhất để truy cập các hệ thống độc lập đơn giản, đáng tin cậy, có khả năng mở rộng,

 3) Tất cả những thuộc tính này vẫn giữ đúng đối với các hệ thống mà chúng ta hiện đang thiết kế.
---

### REST Development
- Hệ thống REST hoạt động theo mô hình client- server, trong đó server là tập hợp các service nhỏ lắng nghe các request từ client
- Với từng request khác nhau thì có thể một hoặc nhiều service xử lý
- Các hệ thống dựa trên REST có nhiều mức độ về hạn chế kiến trúc
---

### REST Development
- URI cung cấp một cơ chế đơn giản và minh bạch để đặt tên các dịch vụ REST từ xa
- Các dịch vụ dựa trên REST đều sử dụng phương pháp truy cập chuẩn để tham số hóa các yêu cầu được thực hiện từ client đến REST server
---

### REST Development

![alt](https://cdn-images-1.medium.com/max/599/1*uHzooF1EtgcKn9_XiSST4w.png)

---

### REST Development
- Khi client yêu cầu URI từ xa sử dụng phương thức truy cập, server sẽ trả về mô tả của điều người dùng yêu cầu
- Nhưng nếu họ đưa ra yêu cầu đến cùng một URI với phương pháp truy cập xóa, server sẽ chạy và xóa tài nguyên đó
---

### REST Development
- Vì vậy bản chất của phương pháp truy cập mà người dùng chỉ định cùng với yêu cầu của họ là vô cùng có ý nghĩa
- Khó khăn kiến trúc tiếp theo là các server dựa trên REST giao tiếp sử dụng các đại diện trung gian
- Các NOUN trong một hệ thống REST tương ứng với các nguồn mà hệ thống cho phép truy cập và thao tác, VD: Người sử dụng
---

### REST Development
- **Phương thức:**

 1) Phương thức GET: sử dụng GET theo cách này rất rõ ràng vì GET chỉ dành cho truy cập dữ liệu. GET không thay đổi giá trị của resource
 
 2) Phương thức DELETE dùng để xóa resource: xóa resource bởi URI
 
---

### REST Development
- **Phương thức:**

 3) Phương thức PUT: Sử dụng để cập nhật dữ liệu của resource. Dữ liệu được cập nhật bằng cách xác định resource bằng URI. Nếu không tồn tại resource sẽ tạo ra một resource mới
 
 4) Phương thức POST: tạo ra một resource mới.
---

### REST Development
- Trong các header yêu cầu, có thể đặt thêm metadata như chỉ định loại định dạng phản hồi bạn muốn lấy lại hoặc chỉ định thông tin về người dùng thực hiện yêu cầu hoặc một số loại token ủy quyền
- Hầu hết các yêu cầu REST nên là idempotent
---

### REST Development
- Điều này có nghĩa là nếu người dùng thực hiện cùng một yêu cầu nhiều lần, cùng một hành động sẽ diễn ra. Ngoại lệ cho điều này sẽ được post
- Khi một phản hồi được trả về từ một dịch vụ **REST** lại cho khách hàng, nó chứa hai thành phần chính, phần header và phần thân.
---

### REST Development
- Header chứa tất cả các loại siêu dữ liệu khác nhau, nhưng một phần quan trọng là mã trạng thái
- Một danh sách các mã trạng thái chuẩn được sử dụng phổ biến. VD: 200 cho yêu cầu thành công, 404 cho việc không thấy dữ liệu
---

### REST Development
- Phần dữ liệu phản hồi cũng có thể được trả về dưới nhiều dạng khác nhau phổ biến nhất là JSON, XML và HTML
- HTML thường được sử dụng trong những tình huống mà ta muốn phản hồi được hiển thị trong một trình duyệt web trực quan
---

### REST Development
- XML là một định dạng giao hoán cũ hơn, cho phép các đối tượng phức tạp được mô tả trong một trường hợp cực phức tạp
- JSON được sử dụng trong trường hợp bạn muốn đối tượng phản hồi được phân tích cú pháp trực tiếp trong một trình duyệt web hoặc trong nút, bởi vì mọi đối tượng JSON cũng là một đối tượng JavaScript
---

### REST Development
**Giao tiếp phi trạng thái (stateless communication)**
- REST ám chỉ rằng hoặc là chuyển về trạng thái nguồn (resource state), hoặc lưu giữ trên client server và client không lưu trạng thái của nhau
-> Mỗi yêu cầu (request) lên server thì client phải đóng gói thông tin đầy đủ để server hiểu được
---

### REST Development
- Lý do: số lượng client tương tác sẽ ảnh hưởng nghiêm trọng tới server nếu nó phải giữ trạng thái (state) cho client (về khả năng mở rộng)
-> Stateless giúp hệ thống dễ phát triển,bảo trì, mở rộng
---

### REST Development
- Khuyết điểm: gia tăng lượng thông tin cần truyền tải giữa client và server.
- Khía cạnh quan trọng khác: Hạn chế stateless cô lập các client đối với những thay đổi trên server vì nó không phụ thuộc vào cuộc gọi với cùng một server trong hai yêu cầu liên tiếp.
---

### REST Development
- Một client có thể nhận được một tài liệu có chứa các liên kết từ các máy chủ, trong khi nó thực hiện một số tiến trình, máy chủ có thể tắt, đĩa cứng của nó có thể được tách ra và được thay thế, phần mềm có thể được cập nhật và khởi động lại
- Nếu client theo dõi một trong các liên kết đã nhận được từ máy chủ, nó sẽ không nhận thấy thông báo.
---

### REST Development
**Chuẩn hóa các interface**
- Đây là một trong những đặc tính quan trọng của hệ thống REST 
- Bằng cách tạo ra các quy ước chuẩn để giao tiếp giữa các thành phần trong hệ thống, bạn đã đơn giản hóa việc client có thể tương tác với server.
---

### REST Development
- Các quy ước này áp dụng cho toàn bộ các service giúp cho người sử dụng hệ thống của bạn dễ dùng hơn. VD: hệ thống bạn đặt ra 1 chuẩn API để người dùng dù là mobile, web đều có thể kết nối vào được. 
- Hệ thống REST có yếu điểm ở đây vì khi chuẩn hóa rồi ta không thế tối ưu từng kết nối.
---

### REST Development
**Chú ý**:
- API REST nên nhỏ để không rò rỉ chi tiết thực hiện nội bộ. Ngoài ra, nên xem xét khả năng sử dụng của chúng để khách hàng có thể sử dụng chúng hiệu quả.
- Bằng cách thiết kế một API linh hoạt, API của bạn có thể được sử dụng bởi nhiều client khác nhau bằng nhiều cách khác nhau
-> Tăng tính linh hoạt cho client.
---

### COUPLING
- Kết nối các lớp chương trình khác nhau.
- Khớp nối(coupling) thực sự là vấn đề trong thực tế bởi vì nó có một ảnh hưởng mạnh mẽ đến cách duy trì và tiến hóa hệ thống của chúng ta.
- Bởi vì nếu bạn có một lớp chương trình chặt chẽ cùng với một lớp khác, thực hiện thay đổi đối với lớp đó thường có thể gây ra lỗi trong các lớp khác.
---

### COUPLING
- Ngoài ra, nếu chúng ta đi sửa lỗi hoặc thêm một tính năng mới vào hệ thống của chúng ta, điều này thường có nghĩa là chúng ta cần phải sửa mã ở nhiều nơi khác nhau, cũng có thể gây ra lỗi ở nhiều nơi khác nhau.
- Điều này cũng cho thấy một thách thức về sử dụng lại.
---

### COUPLING
-  Ghép nối là một độ đo của độ phụ thuộc lẫn nhau giữa các module trong chương trình máy tính.
- Các lớp độc lập nhỏ hơn thì tốt hơn nhiều so với các lớp mà tất cả đều kết hợp với nhau chặt chẽ. Vì vậy, nếu bạn đang xem xét một lớp, và bạn nhận ra bạn cũng cần phải nhìn vào nhiều lớp 1 lúc.
- Đột nhiên, bạn có cả một loạt các trình biên tập mã mở mà làm cho nó thực sự khó khăn để quản lý hệ thống của bạn.
---

### COUPLING
- Chúng ta muốn giảm thiểu các giao diện tồn tại giữa các yếu tố chương trình khác nhau, giảm thiểu sự phức tạp của các giao diện, để họ chỉ tiết lộ bề mặt tối thiểu đó là yêu cầu cung cấp các chức năng cần thiết.
- Và giảm thiểu càng nhiều càng tốt các ràng buộc kiểm soát dòng tồn tại giữa các mô-đun.
---

### COHESION
- Sự gắn kết, mà chúng ta đã thấy trước đây, là một các biện pháp chủ yếu để đánh giá mức độ tập liên kết chặt chẽ trách nhiệm của một đơn vị thực hiện (các lớp)
- Vì vậy, các biện pháp gắn kết là làm thế nào tập trung tốt các phương pháp và các trường trong một lớp.
---

### COHESION
- Các lớp có độ gắn kết thấp, chịu trách nhiệm cho một loạt các hành động đa dạng. Điều này có thể làm cho nó thực sự khó khăn cho một nhà phát triển để nhìn vào một lớp và thực sự hiểu những gì đang thực hiện.
- Nó cũng cản trở việc duy trì và phát triển phần mềm.
---

### COHESION
- Các lớp gắn kết thường có một tập nhỏ các trường private, và các methord trong lớp sẽ hoạt động trên những mảng đó.
- Nếu một phương pháp sử dụng nhiều hơn một hoặc thậm chí tất cả các mảng, nó có thể liên kết chặt chẽ với các mục tiêu tổng thể của lớp.
---

### COHESION
- Ngược lại, nếu có một phương pháp mà không sử dụng bất kỳ lĩnh vực nào cả, nó có lẽ không liên quan với các mục tiêu tổng thể của lớp, và có lẽ nên được di chuyển ở một nơi khác.
- Điều này dẫn chúng ta đến một số lượng lớn các lớp nhỏ hơn, điều này là tốt bởi vì nó có nghĩa là nhà phát triển có thể di chuyển nhanh chóng trong các lớp họ quan tâm, và giúp cô lập các thay đổi, làm cho nó bảo trì và tiến hóa dễ dàng hơn.
---



### Design Principles: SOLID

![alt](https://howtodoinjava.com/wp-content/uploads/solid_class_design_principles.png)
---

### Design Principles: SOLID
**Hướng dẫn thiết kế và các dấu hiệu**
-	Tính linh hoạt của hệ thống là phần mềm là có thể thiết kế theo nhiều cách khác nhau
**Một số yêu cầu về hệ thống phần mềm**
-	Cần dễ hiểu
-	Cần chuẩn đoán và sửa lỗi một cách dễ dàng và nhanh chóng
-	Đáp ứng được các thay đổi và cải tiến trong tương lai

---

### Design Principles: SOLID
**Những thiết kế phần mềm kém**

---
### Design Principles: SOLID
**Thiết kế cứng nhắc(rigid designing)**
-	Là thiết kế chống lại sự thay đổi
-	Là thách thức trong thực tế vì mất nhiều nỗ lực để thay đổi
-	Xác định các rủi ro trong tương lai khó khăn

---
### Design Principles: SOLID
**Thiết kế mong manh(design fragility)**
-	Phát sinh khi có một thiết kế dễ bị phá vỡ
-	Tạo ra nhiều giả định khi chạy chương trình

---
### Design Principles: SOLID
**Thiết kế bất động(immobility design)**
-	Các dòng code không độc đáo
-	Thường được tìm kiếm và sao chép vào trong các hệ thống
-	Tìm ẩn nhiều rủi ro

---
### Design Principles: SOLID
**Thiết kế nhớt(viscous design)**
-	Dễ vi phạm hơn là tuân tủ các quy tắc thiết kế
-	Dẫn các nhà phát triển dẫn các hacks vào hệ thống

---
### Design Principles: SOLID
S : Nguyên tắc đơn nhiệm( Sinple responsibility princible)
O: Nguyên tắc mở/đóng(Open/Cloded princible)
L: Nguyên tắc khả dĩ thay thế(Liskov substitution principle)
I: Nguyên tắc phân chia giao diện(Interface segragation princible)
D: Nguyên tắc tương thích động(Dependency inversion principle)

---
### Design Principles: SOLID
**Nguyên tắc đơn nhiệm (Simple responsibility princible)**

![alt](https://image.slidesharecdn.com/2013aprilmsfagmte-singleresponsibilityprinciple-130427022920-phpapp01/95/the-single-responsibility-principle-3-638.jpg?cb=1367029949)

---

### Design Principles: SOLID
**Nguyên tắc đơn nhiệm (Simple responcibility princibles)**
- S : Nguyên tắc đơn nhiệm( sinple responsibility princible)
Phát biểu: Mỗi 1 modun trong 1 chương trình nên làm một việc và làm tốt việc
-	Rất quan trong trong thực tế
Vì nhiều người thường làm nhiều chức năng vào một mô-Đun hơn là tạo ra 1 mô-đun mới

---


### Design Principles: SOLID
**Nguyên tắc đơn nhiệm (Simple responcibility princibles)**

-	Một số nguyên tắc giúp tuân thủ theo Ngt đơn nhiệm
 +	Mô hình chiến lược(the strategy pattarn)
  =>	Thúc đẩy hướng tới các thuật toán nhỏ, độc lập
+ Mẫu lệnh(command pattarn)
=>Tóm tắt lại các hành động
+	Mẫu trạng thái(
=>	Giúp tóm tắt cách 1 đối tượng cư xử trong những trạng thái khác nhau

---

### Design Principles: SOLID
**Nguyên tắc mở và đóng (Open / Closed principle (OCP) )**

![alt](https://image.slidesharecdn.com/ppt-120429111617-phpapp01/95/principles-of-object-oriented-class-design-15-728.jpg?cb=1348987975)

---

### Design Principles: SOLID
**Nguyên tắc mở và đóng (Open / Closed principle (OCP) )**
- Phát biểu:Mỗi hệ thống nên hạn chế việc chỉnh sửa bên trong một Class hoặc Module có sẵn, thay vào đó hãy xem xét mở rộng chúng.
- Điều này có nghĩa là các tính năng mới có thể dễ dàng thêm vào một hệ thống mà không thay đổi thực hiện hiện có.
---

### Design Principles: SOLID
**Nguyên tắc Đóng và Mở (Open / Closed principle (OCP) )**
- **Hạn chế sửa đổi**: Ta không nên chỉnh sửa source code của một module hoặc class có sẵn, vì sẽ ảnh hưởng tới tính đúng đắn của chương trình.
- **Ưu tiên mở rộng**: Khi cần thêm tính năng mới, ta nên kế thừa và mở rộng các module/class có sẵn thành các module con lớn hơn.
- Các module/class con vừa có các đặc tính của lớp cha (đã được kiểm chứng đúng đắn), vừa được bổ sung tính năng mới phù hợp với yêu cầu.
---

### Design Principles: SOLID
**Nguyên tắc khả dĩ thay thế (Liskov substitution principle (LSP) )**

![alt](https://image.slidesharecdn.com/oodesignprinciplesheuristics-140808094222-phpapp02/95/oo-design-principles-heuristics-21-638.jpg?cb=1407490990)

---

### Design Principles: SOLID
**Nguyên tắc khả dĩ thay thế (Liskov substitution principle (LSP) )**
Phát biểu: các thể hiện(instance) của lớp con có thể thay thế được các thể hiển của lớp cha mà nó vẫn giữ nguyên được tính đúng đắn của chương trình.
-	Khi mở rộng phần mềm bằng bằng các lớp con kế thừa thì cần phải đảm bảo các lớp con có thể chạy được và chạy đúng những chức năng mà các lớp cha đã có.

---
### Design Principles: SOLID
**Nguyên tắc khả dĩ thay thế (Liskov substitution principle (LSP) )**
Ý nghĩa:
-	Việc bảo trì và mở rộng được thực hiện dễ dàng
-	Tránh được một số lỗi ngay khi biên dịch

---


### Design Principles: SOLID
**Nguyên tắc phân chia giao diện(Interface segragation princible)**
![alt](https://image.slidesharecdn.com/oodesignprinciplesslideshare-140515053613-phpapp01/95/objectoriented-design-principles-13-638.jpg?cb=1402624393)

---
### Design Principles: SOLID
**Nguyên tắc phân chia giao diện(Interface segragation princible)**
Phát biểu: 1 chương trình con(client) không nên phụ thuộc vào các phần giao diện và nó không dùng tới.
-	 Thay vì có 1 giao diện lớn ta nên tách ra thành nhiều phần nhỏ với nhiều mục đích khác nhau
-	Nguyên tắc này thường hay bị vi phạm vì người phát triển thường không chú trọng tới việc phân tách giao diện

---
#### Design Principles: SOLID
**Nguyên tắc tương thích động (DIP)**
![alt](http://slideplayer.com/slide/9027270/27/images/7/Dependency+inversion+principle.jpg)

---

### Design Principles: SOLID
**Nguyên tắc tương thích động (DIP)**
- Phát biểu: Mỗi thành phần của một hệ thống chỉ nên phụ thuộc vào lớp trừu tượng(abstractions), không nên phụ thuộc vào các lớp triển khai(implementations )
-	Điểm quan trọng: tách riêng các triển khai bằng việc áp các lớp trừu tượng( thường là các lớp giao diện)
=>	Dễ dàng thay đổi, sửa chữa và sử dụng lại
=>	Dễ dàng cung cấp các triển khai trong hệ thống
---
