# Giới thiệu:
Đây là một repository được fork lại từ [https://github.com/bclswl0827/v2ray-heroku](https://github.com/bclswl0827/v2ray-heroku) với chức năng là tạo ra một server V2Ray trên heroku một cách đơn giản nhất.

Heroku sẽ không khuyến khích việc này nên các bạn cần phải fork lại dự án này để không bị heroku chặn.

Với nhu cầu không quá cao thì heroku chính là giải pháp hoàn hảo cho anh em muốn dùng V2Ray để dùng 4G miễn phí:
* 2TB mỗi tháng
* 550 giờ mỗi tháng (~23 ngày, dĩ nhiên bạn cần ngủ 8 tiếng 1 ngày nên 550 giờ là quá đủ)

Anh em xem hướng dẫn ở đây nhé:

[![4G Free](https://img.youtube.com/vi/79jkqGWi0zU/0.jpg)](https://www.youtube.com/watch?v=79jkqGWi0zU)

=============================================================

# V2Ray Heroku

**Nếu bạn cần triển khai V2Ray VLESS，thì qua bài viết này [vless](https://github.com/bclswl0827/v2ray-heroku/tree/vless)**

## Tổng quan

Dự án V2Ray WebSocket trên Heroku phải được sử dụng một cách hợp lý nếu không sẽ bị chặn

Sau khi triển khai, mỗi khi khởi động sẽ tải bản V2Ray mới nhất

## Triển khai

### Bắt đầu

 1. Fork dự án này qua tài khoản GitHub của bạn（trên PC có thể thấy nút Fork trên cùng bên tay phải, ví dụ tài khoản của bạn tên là `example`）
 2. Sửa lại tên dự án thành tên bất kỳ không nên chứa hai từ khóa `v2ray` và `heroku`（Ví dụ đổi thành `demo`）
 3. Sửa lại file `README.md`，đường dẫn `kim7tin/v2heroku` bằng đường dẫn của bạn（ví dụ `example/demo`）

> [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/kim7tin/v2heroku)

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
