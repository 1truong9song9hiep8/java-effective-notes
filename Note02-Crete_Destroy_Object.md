# Tạo và Xóa Đối Tượng

**1. *Hãy xem xét các phương thức nhà máy tĩnh thay vì các hàm tạo*
Thông thường chúng ta tạo đối tượng bằng constructor, có một cách khác là sử dụng static factory method. Các Static Factory Method là gì? là những hàm static mà nó trả về một instance của class đó.

khi nào thì chúng ta sử dụng static factory method thay vì constructor, khi bạn muốn trả về một instance mà một số trường có giá trị mặc định sẵn.

lợi thế thứ 1: dễ đọc hơn bởi chúng ta có thể viết tên tùy ý cho hàm.

lợi thế thứ 2: có thể không tạo ra đối tượng mới, nếu muốn tái sư dụng instance.

lợi thế thứ 3: có thể trả về một subtype, còn constructor thì không

trước Java8 một interface không thể có static method, 


## Xem sét builder thay vì các constrcutor params
Các factory method và constructor có chung một nhược điểm là không có khản năng mở rộng khi các param thay đổi.

