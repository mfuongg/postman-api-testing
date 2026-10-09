# BÁO CÁO KIỂM THỬ API

**1. Tên dự án:** Thực hành kiểm thử API bằng Postman (Postman API Testing Practice)

**Ngày kiểm thử:** 09/10/2026

**Người kiểm thử:** Ngô Thị Minh Phương

## 1. Mục tiêu kiểm thử

Sử dụng Postman để thực hiện kiểm thử API, tìm hiểu cách gửi yêu cầu HTTP, kiểm tra dữ liệu phản hồi và đánh giá hoạt động của API.

Các mục tiêu cụ thể:

* Thực hành các phương thức HTTP GET, POST, PUT, PATCH và DELETE.
* Kiểm tra mã trạng thái HTTP và dữ liệu JSON trả về.
* Viết và chạy các đoạn mã kiểm thử tự động trong Postman.
* Thực hiện kiểm thử các trường hợp không hợp lệ (Negative Testing).
* Ghi nhận kết quả kiểm thử bằng ảnh chụp màn hình.

## 2. Môi trường kiểm thử

* **Công cụ kiểm thử:** Postman Web.
* **API được kiểm thử:** JSONPlaceholder.
* **URL cơ sở:** https://jsonplaceholder.typicode.com
* **Tài nguyên kiểm thử:** `/posts`.
* **Phương thức kiểm thử:** Kiểm thử thủ công và kiểm thử tự động bằng Postman.

## 3. Phương pháp kiểm thử

Bài thực hành sử dụng hai phương pháp kiểm thử:

* **Kiểm thử thủ công:** Gửi các yêu cầu API trên Postman, quan sát mã trạng thái HTTP và kiểm tra nội dung phản hồi.
* **Kiểm thử tự động:** Sử dụng các đoạn mã trong mục Tests của Postman để xác minh mã trạng thái, cấu trúc dữ liệu và kết quả trả về theo từng trường hợp kiểm thử.

Ngoài các trường hợp kiểm thử thông thường, bài thực hành còn kiểm tra bài viết không tồn tại và endpoint không hợp lệ để đánh giá phản hồi của API khi xảy ra tình huống ngoại lệ.

## 4. Các kịch bản kiểm thử

### 4.1. Kịch bản kiểm thử lần 1: Lấy thông tin một bài viết

* **Mã kịch bản:** TC01
* **Tên kịch bản:** Kiểm thử lấy thông tin một bài viết.
* **Mục đích:** Kiểm tra khả năng truy xuất dữ liệu của API.
* **Phương thức HTTP:** GET.
* **URL:** https://jsonplaceholder.typicode.com/posts/1
* **Tham số:** Không có.
* **Kết quả mong đợi:** API trả về mã trạng thái 200 OK và thông tin bài viết có ID bằng 1.
* **Kết quả thực tế:** API trả về thông tin bài viết dưới dạng JSON.
* **Trạng thái kiểm thử:** Thành công.

### 4.2. Kịch bản kiểm thử lần 2: Lấy danh sách bài viết theo người dùng

* **Mã kịch bản:** TC02
* **Tên kịch bản:** Kiểm thử lấy danh sách bài viết theo userId.
* **Mục đích:** Kiểm tra khả năng truy vấn danh sách bài viết dựa trên tham số.
* **Phương thức HTTP:** GET.
* **URL:** https://jsonplaceholder.typicode.com/posts?userId=1
* **Tham số:** `userId=1`.
* **Kết quả mong đợi:** API trả về mã trạng thái 200 OK và danh sách bài viết thuộc người dùng có ID bằng 1.
* **Kết quả thực tế:** API trả về danh sách bài viết dưới dạng JSON.
* **Trạng thái kiểm thử:** Thành công.

### 4.3. Kịch bản kiểm thử lần 3: Tạo bài viết mới

* **Mã kịch bản:** TC03
* **Tên kịch bản:** Kiểm thử tạo bài viết bằng phương thức POST.
* **Mục đích:** Kiểm tra khả năng gửi dữ liệu để mô phỏng việc tạo bài viết.
* **Phương thức HTTP:** POST.
* **URL:** https://jsonplaceholder.typicode.com/posts
* **Dữ liệu gửi đi:**

```json
{
  "title": "Postman Practice",
  "body": "This is a test post",
  "userId": 1
}
```

* **Kết quả mong đợi:** API trả về mã trạng thái 201 Created và dữ liệu bài viết vừa gửi.
* **Kết quả thực tế:** API trả về phản hồi chứa dữ liệu bài viết.
* **Trạng thái kiểm thử:** Thành công.

### 4.4. Kịch bản kiểm thử lần 4: Cập nhật toàn bộ thông tin bài viết

* **Mã kịch bản:** TC04
* **Tên kịch bản:** Kiểm thử cập nhật bài viết bằng phương thức PUT.
* **Mục đích:** Kiểm tra khả năng gửi dữ liệu cập nhật cho một bài viết đã tồn tại.
* **Phương thức HTTP:** PUT.
* **URL:** https://jsonplaceholder.typicode.com/posts/1
* **Dữ liệu gửi đi:**

```json
{
  "id": 1,
  "title": "Updated Post",
  "body": "This post was updated",
  "userId": 1
}
```

* **Kết quả mong đợi:** API trả về mã trạng thái 200 OK và dữ liệu bài viết theo nội dung cập nhật.
* **Kết quả thực tế:** API trả về dữ liệu bài viết đã cập nhật theo yêu cầu.
* **Trạng thái kiểm thử:** Thành công.

### 4.5. Kịch bản kiểm thử lần 5: Cập nhật một phần thông tin bài viết

* **Mã kịch bản:** TC05
* **Tên kịch bản:** Kiểm thử cập nhật một phần bài viết bằng phương thức PATCH.
* **Mục đích:** Kiểm tra khả năng cập nhật một thuộc tính của bài viết.
* **Phương thức HTTP:** PATCH.
* **URL:** https://jsonplaceholder.typicode.com/posts/1
* **Dữ liệu gửi đi:**

```json
{
  "title": "Partially Updated Post"
}
```

* **Kết quả mong đợi:** API trả về mã trạng thái 200 OK và phản hồi thể hiện tiêu đề đã được cập nhật.
* **Kết quả thực tế:** API trả về phản hồi chứa tiêu đề theo yêu cầu cập nhật.
* **Trạng thái kiểm thử:** Thành công.

### 4.6. Kịch bản kiểm thử lần 6: Xóa bài viết

* **Mã kịch bản:** TC06
* **Tên kịch bản:** Kiểm thử xóa bài viết bằng phương thức DELETE.
* **Mục đích:** Kiểm tra khả năng gửi yêu cầu xóa một bài viết.
* **Phương thức HTTP:** DELETE.
* **URL:** https://jsonplaceholder.typicode.com/posts/1
* **Tham số:** Không có.
* **Kết quả mong đợi:** API trả về mã trạng thái 200 OK, thể hiện yêu cầu xóa đã được xử lý.
* **Kết quả thực tế:** API trả về phản hồi theo hành vi mô phỏng của JSONPlaceholder.
* **Trạng thái kiểm thử:** Thành công.

### 4.7. Kịch bản kiểm thử lần 7: Truy vấn bài viết không tồn tại

* **Mã kịch bản:** TC07
* **Tên kịch bản:** Kiểm thử truy vấn bài viết có ID không tồn tại.
* **Mục đích:** Kiểm tra phản hồi của API khi truy vấn một bài viết không có trong dữ liệu.
* **Phương thức HTTP:** GET.
* **URL:** https://jsonplaceholder.typicode.com/posts/9999
* **Tham số:** ID bài viết bằng 9999.
* **Kết quả mong đợi:** Phản hồi không chứa dữ liệu bài viết; theo hành vi của JSONPlaceholder, kết quả có thể là đối tượng JSON rỗng `{}` với mã trạng thái 200.
* **Kết quả thực tế:** Đánh giá dựa trên phản hồi và kết quả kiểm thử được ghi nhận trong Postman.
* **Trạng thái kiểm thử:** Thành công nếu phản hồi đáp ứng điều kiện kiểm thử đã thiết lập.

### 4.8. Kịch bản kiểm thử lần 8: Truy cập endpoint không hợp lệ

* **Mã kịch bản:** TC08
* **Tên kịch bản:** Kiểm thử truy cập đường dẫn API không tồn tại.
* **Mục đích:** Kiểm tra khả năng phản hồi của API khi gửi yêu cầu đến endpoint không hợp lệ.
* **Phương thức HTTP:** GET.
* **URL:** https://jsonplaceholder.typicode.com/invalid-endpoint
* **Tham số:** Không có.
* **Kết quả mong đợi:** API trả về mã trạng thái 404 Not Found.
* **Kết quả thực tế:** Ghi nhận mã trạng thái và nội dung phản hồi từ Postman.
* **Trạng thái kiểm thử:** Thành công nếu kết quả thực tế là 404 và đáp ứng điều kiện kiểm thử.

## 5. Kết quả kiểm thử

Tổng hợp kết quả của 8 kịch bản kiểm thử:

* **Tổng số kịch bản đã kiểm thử:** 8.
* **Số kịch bản thành công:** 8.
* **Số kịch bản thất bại:** 0.
* **Tỷ lệ thành công:** 100%.
* **Tỷ lệ thất bại:** 0%.

Công thức tính tỷ lệ thành công:

Tỷ lệ thành công = (Số kịch bản thành công / Tổng số kịch bản kiểm thử) × 100%.

Các kết quả trên cần khớp với kết quả thực tế hiển thị trong Postman.

## 6. Phát hiện lỗi và hạn chế

### 6.1. Phát hiện lỗi

Trong quá trình kiểm thử, các trường hợp không hợp lệ được sử dụng để đánh giá hành vi phản hồi của API.

* **TC07 – Bài viết không tồn tại:** Cần kiểm tra nội dung JSON trả về. Mã trạng thái 200 cùng đối tượng rỗng `{}` có thể là hành vi bình thường của JSONPlaceholder, không tự động được xem là lỗi.
* **TC08 – Endpoint không hợp lệ:** Mã trạng thái 404 Not Found là kết quả mong đợi của kịch bản này; nếu nhận được 404 thì không phải lỗi của bài kiểm thử.

Không kết luận có lỗi hệ thống nếu kết quả thực tế phù hợp với kết quả mong đợi.

### 6.2. Hạn chế và đề xuất

JSONPlaceholder là API giả lập phục vụ mục đích học tập. Các yêu cầu POST, PUT, PATCH và DELETE mô phỏng thao tác với dữ liệu nhưng không đảm bảo những thay đổi được lưu vĩnh viễn trong cơ sở dữ liệu.

Để nâng cao chất lượng kiểm thử, có thể bổ sung thêm trường hợp kiểm tra dữ liệu đầu vào không hợp lệ, thiếu trường bắt buộc, sai kiểu dữ liệu và các mã trạng thái HTTP khác.

## 7. Ảnh chụp kết quả kiểm thử


Các ảnh minh họa bao gồm:

* Kết quả phản hồi của sáu yêu cầu API chính.
* Kết quả thực thi các đoạn mã kiểm thử trong Postman.
* Kết quả kiểm thử các trường hợp không hợp lệ.

Các ảnh được sử dụng làm minh chứng cho quá trình thực hiện và kết quả kiểm thử.

## 8. Kết luận

Thông qua bài thực hành, tôi đã làm quen với quy trình kiểm thử API bằng Postman, thực hiện các phương thức HTTP phổ biến, kiểm tra mã trạng thái và nội dung phản hồi JSON, đồng thời sử dụng các đoạn mã kiểm thử tự động để đánh giá kết quả.

Bài thực hành giúp củng cố kiến thức về kiểm thử API và hiểu rõ hơn sự khác biệt giữa một yêu cầu API được thực hiện thành công với một trường hợp kiểm thử đạt yêu cầu, đặc biệt trong các tình huống kiểm thử âm tính.
