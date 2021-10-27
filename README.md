# Giới thiệu:
Đây là một repository được fork lại từ [https://github.com/bclswl0827/v2ray-heroku](https://github.com/bclswl0827/v2ray-heroku) với chức năng là tạo ra một server V2Ray trên heroku một cách đơn giản nhất.

Heroku sẽ không khuyến khích việc này nên các bạn cần phải fork lại dự án này để không bị heroku chặn.

Với nhu cầu không quá cao thì heroku chính là giải pháp hoàn hảo cho anh em muốn dùng V2Ray để dùng 4G miễn phí:
* 2TB mỗi tháng
* 550 giờ mỗi tháng (~23 ngày, dĩ nhiên bạn cần ngủ 8 tiếng 1 ngày nên 550 giờ là quá đủ)

=============================================================
### Một Số Hình Ảnh Hướng Dẩn 

![chuyen heroku](https://user-images.githubusercontent.com/92734523/139077306-b4decf1b-6d3c-4de8-b1d0-6372377d32ab.png)

![chuyen trang](https://user-images.githubusercontent.com/92734523/139077487-43cc277e-d1f6-4481-97dd-203658dea23e.png)

![sua ten](https://user-images.githubusercontent.com/92734523/139077589-c37c1dd3-d440-4b58-8579-0fb08c33bd5a.png)

![deploy](https://user-images.githubusercontent.com/92734523/139077581-efd0fe1b-5394-4689-9cef-b487c556d38e.png)

![url](https://user-images.githubusercontent.com/92734523/139077592-d8f61ce4-2225-482b-9b05-229dc82b4052.png)

**Nhớ các thông tin đó như url id alterid => vô ứng dụng V2ray hay ứng dụng nào có tự tạo vmess làm theo hình**

![2ff82b7ec51c0d42540d1](https://user-images.githubusercontent.com/92734523/139078062-7091ea86-ee93-443c-aa62-08679fed2dcb.jpg)

![892ffab114d3dc8d85c23](https://user-images.githubusercontent.com/92734523/139078111-4b3f1805-acc2-43e9-9731-31aa7d9ab431.jpg)

![0a5e6ac384a14cff15b02](https://user-images.githubusercontent.com/92734523/139078129-51e67203-307b-4535-a80c-634ec81b0da9.jpg)

#### Đây là speedtest server heroku lúc 20h37 tại quận 4 HCM

![e27c4be5a5876dd934964](https://user-images.githubusercontent.com/92734523/139078147-8e621d87-0380-4b60-92ac-104635f6a771.jpg)


********************************************************************************************************

## Tổng quan

Dự án V2Ray WebSocket trên Heroku phải được sử dụng một cách hợp lý nếu không sẽ bị chặn

Sau khi triển khai, mỗi khi khởi động sẽ tải bản V2Ray mới nhất

## Triển khai

### Bắt đầu

 1. Fork dự án này qua tài khoản GitHub của bạn（trên PC có thể thấy nút Fork trên cùng bên tay phải, ví dụ tài khoản của bạn tên là `example`）
 2. Sửa lại tên dự án thành tên bất kỳ không nên chứa hai từ khóa `v2ray` và `heroku`（Ví dụ đổi thành `demo`）
 3. Sửa lại file `README.md`，đường dẫn `TranCuongQ4/4gheroku` bằng đường dẫn của bạn（ví dụ `example/demo`）

> [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/TranCuongQ4/4gheroku)

 4. Quay lại trang chủ của dự án，bấm vào liên kết để triển khai V2Ray

### Đối số

Các đối số sẽ dùng trong quá trình cài đặt。

| Đối số | Mặc định | Diễn giải |
| :--- | :--- | :--- |
| `ID` | `ad806487-2d26-4636-98b6-ab85cc8521f7` | VMess user ID |
| `AID` | `64` | AlterID，Số từ 0 đến 65535 |
| `WSPATH` | `/` | |

## Truy cập CloudFlare

Hai phương pháp sau có thể kết nối ứng dụng với CloudFlare, từ đó tăng tốc độ ở một mức độ nhất định:

1. Liên kết tên miền với ứng dụng và kết nối tên miền với CloudFlare
2. Reverse proxy thông qua CloudFlare worker 

## Lưu ý

 1. ** Xin đừng lạm dụng dự án này, có rất ít dịch vụ miễn phí như Heroku, hãy sử dụng và trân trọng **
 2. Nếu bạn sử dụng tên miền để kết nối với CloudFlare, vui lòng xem xét bật TLS 1.3 
 3. Hầu hết các địa chỉ AWS IPv4 đã bị Twitter chặn 
