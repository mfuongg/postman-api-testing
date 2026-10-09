# Thực hành kiểm thử API bằng Postman

## 1. Giới thiệu

Dự án này thực hiện kiểm thử API cơ bản bằng Postman và JSONPlaceholder. JSONPlaceholder là một REST API giả lập miễn phí, được sử dụng để thực hành và tìm hiểu cách hoạt động của các API.

## 2. Mục tiêu

* Tìm hiểu và thực hành các phương thức HTTP: GET, POST, PUT, PATCH và DELETE.
* Gửi yêu cầu API và kiểm tra dữ liệu phản hồi dạng JSON.
* Kiểm tra mã trạng thái HTTP và nội dung phản hồi.
* Viết các đoạn mã kiểm thử tự động trong Postman.
* Thực hiện kiểm thử các trường hợp không hợp lệ (Negative Testing).
* Ghi lại kết quả kiểm thử thông qua ảnh chụp màn hình.

## 3. Môi trường kiểm thử

* **Công cụ:** Postman Web
* **API:** JSONPlaceholder
* **Địa chỉ API cơ sở:** https://jsonplaceholder.typicode.com
* **Tài nguyên kiểm thử:** `/posts`

## 4. Danh sách trường hợp kiểm thử

| Mã kiểm thử | Phương thức | Endpoint            | Kết quả mong đợi                                   |
| ----------- | ----------- | ------------------- | -------------------------------------------------- |
| TC01        | GET         | `/posts/1`          | Lấy thông tin một bài viết                         |
| TC02        | GET         | `/posts?userId=1`   | Lấy danh sách bài viết của người dùng có ID bằng 1 |
| TC03        | POST        | `/posts`            | Mô phỏng tạo một bài viết mới                      |
| TC04        | PUT         | `/posts/1`          | Mô phỏng cập nhật toàn bộ thông tin bài viết       |
| TC05        | PATCH       | `/posts/1`          | Mô phỏng cập nhật một phần thông tin bài viết      |
| TC06        | DELETE      | `/posts/1`          | Mô phỏng xóa một bài viết                          |
| TC07        | GET         | `/posts/9999`       | Kiểm tra phản hồi khi bài viết không tồn tại       |
| TC08        | GET         | `/invalid-endpoint` | Kiểm tra phản hồi khi endpoint không hợp lệ        |

## 5. Kiểm thử tự động

Các đoạn mã kiểm thử trong Postman được sử dụng để xác minh mã trạng thái HTTP và dữ liệu phản hồi của các yêu cầu API.

Nội dung kiểm thử bao gồm:

* Kiểm tra mã trạng thái HTTP.
* Kiểm tra cấu trúc và giá trị dữ liệu JSON.
* Kiểm tra kết quả trả về của các phương thức HTTP.
* Kiểm thử các trường hợp bài viết không tồn tại hoặc endpoint không hợp lệ.

## 6. Kết quả kiểm thử

* **Tổng số trường hợp kiểm thử:** 8
* **Số trường hợp đạt:** 8
* **Số trường hợp không đạt:** 0

Kết quả được ghi nhận dựa trên các phản hồi API và kết quả thực thi các đoạn mã kiểm thử trong Postman.

## 7. Ảnh chụp kết quả kiểm thử

Các ảnh chụp màn hình minh họa quá trình kiểm thử đã được tải trực tiếp lên thư mục gốc của GitHub repository.

Các ảnh bao gồm:

* Kết quả phản hồi của sáu yêu cầu API chính.
* Kết quả thực thi các đoạn mã kiểm thử trong Postman.
* Kết quả kiểm thử các trường hợp không hợp lệ (Negative Testing).


## 8. Hạn chế

JSONPlaceholder là một REST API giả lập dùng cho mục đích thực hành. Vì vậy, các yêu cầu POST, PUT, PATCH và DELETE có thể trả về phản hồi thành công nhưng dữ liệu thay đổi không được lưu trữ lâu dài trong cơ sở dữ liệu thực tế.

## 9. Kết luận

Thông qua bài thực hành, tôi đã tìm hiểu cách gửi yêu cầu API bằng Postman, sử dụng các phương thức HTTP, kiểm tra dữ liệu phản hồi, xây dựng các đoạn mã kiểm thử tự động và thực hiện kiểm thử các trường hợp không hợp lệ.

Bài thực hành giúp củng cố kiến thức cơ bản về kiểm thử API và cách sử dụng Postman trong quá trình kiểm thử phần mềm.
