# Cài SSL miển phí Let's Encrypt trên IIS bằng công cụ Certify the web.
## 1. Tải xuống 
- Tải từ link https://certifytheweb.com/ và cài đặt.

## 2. Đăng kí
- Nhập mail và đăng kí

<img src="image/1.PNG">

## 3. Tạo chứng chỉ mới
- Chọn New Cer, chố site chọn 1 site, sau đó nhập domain và add. Tiếp đến Request Cer.

- <img src="image/2.PNG">
## 4. Thêm binding.
- Vào IIS manager, vào bindings.
- Thêm site binding:

    <img src="image/4.PNG">

- Sau đó khởi động lại IIS.

- Kết quả:

<img src="image/3.PNG">