# G-forwards-tool
Công cụ chuyển đổi proxy server thành proxy local loại bỏ auth user:pass.
Hỗ trợ định dạng đầu vào như HTTP/SOCKS4/SOCKS5 với các dạng Auth ip, User Pass
API hỗ trợ cho việc sử dụng từ xa và công cụ sử dụng.
![G-forwards-tool](https://github.com/2movn/G-forwards-tool/blob/main/tong-quan.png)
# Mục đích sử dụng, Công dụng chính
1. Chuyển đổi định dạng proxy auth về non-auth để sử dụng với nhiều mục đích khác nhau.
2. Giúp thay đổi proxy trên các thiết bị cứng mà không cần can thiệp. Thêm proxy và giả lập, mobile, các tool game cần thay đổi proxy liên tục mà không cần can thiệp vào.

# Link Tải
 - Tải Về: [G-forwards-tool](https://github.com/2movn/G-forwards-tool/releases/download/4.0.0/G-forwards-tool-v4.zip)
# Cách sử dụng
Để sử dụng công cụ bạn cần chuẩn bị trước proxy có thể kết nối internet và có định dạng socks5, socks4, http, Hoặc các Key, Api của 1 server như: Tinsoft Proxy, TM Proxy, Tin Proxy, ShopLike
## Sử dụng với proxy thường
1. Mở công cụ.
2. Điền toàn bộ list proxy vào bảng LIST PROXY, mỗi proxy là 1 dòng.
3. Nhấn thêm proxy. Lúc này proxy sẽ tự động thêm proxy lên bảng giao diện.
4. Tùy chỉnh port tại cột PORT LOCAL.
5. Lựa chọn chạy từng proxy tại cột START, hoặc nhận Chạy tất cả ở menu bên cạnh.
![G-forwards-tool](https://github.com/2movn/G-forwards-tool/blob/main/proxy-list.png?raw=true)
## Sử dụng với API
1. Mở công cụ.
2. Điền toàn bộ list proxy vào bảng API/TOKEN, mỗi API là 1 dòng.
3. Lựa chọn Server api chính xác cho từng API.
4. Nhấn thêm proxy. Lúc này proxy sẽ tự động thêm API lên bảng giao diện.
5. Tùy chỉnh NETWORK để chọn nhà mạng phú hợp theo từng server.
6. Tùy chỉnh Local để chọn địa điểm proxy theo từng server.
7. Tùy chỉnh port tại cột PORT LOCAL.
8. Lựa chọn chạy từng proxy tại cột START, hoặc nhận Chạy tất cả ở menu bên cạnh.
![G-forwards-tool](https://github.com/2movn/G-forwards-tool/blob/main/api.png?raw=true)
## Các Tính năng sử dụng chỉnh sửa trên giao diện
1. Mở toàn bộ: Hỗ trợ mở nhanh toàn bộ các proxy, api đã thêm.
2. Reset tất cả: Tắt toàn bộ và gửi thông điệp tới server để đổi proxy mới. [Không áp dụng với proxy list].
3. Dừng tất cả: Sẽ dừng toàn bộ các tirns trình đang chạy và ngừng chế dộ forward proxy.
4. Chỉnh sửa API. PROXY: Bấm vào cột API/KEY | PROXY tương ứng trên bảng hiển thị và chỉnh sửa ngay trên giao diện.
5. Chỉnh sửa Port local: Bấm chỉnh sửa ngay trên bảng giao diện tương ứng với proxy.
6. Check proxy: Kiểm tra ip public với ip tương ứng.
7. Start: Bắt đầu forward proxy tương ứng.
8. Reset: Bắt đầu reset Proxy tương ứng.
9. Stop: Bắt đầu sừng proxy tương ứng
10. Del: Xóa proxy tương ứng.
11. Time: Hiển thị thời gian cho phép đổi ip của server tương ứng

## Tính năng khác
1. Ruler Block: Giúp chặn và không truy cập tới website cần thiết, giảm tối đa dung lượng cho proxy.
2. License: Kích hoạt công cụ để sử dụng toàn bộ tính năng
3. API: Sử dụng api để điều khiển công cụ từ xa.
![G-forwards-tool](https://github.com/2movn/G-forwards-tool/blob/main/block.png?raw=true)
# Ruler Block
## Cài đặt hiển thị/Tắt log
- File cài đặt: [...\G-forwards-tool\setting\log.ini]
- Mặc định: 1 (Hiển thị Log) | Các số khác: Tắt log
## Cài đặt Chặn website
- File cài đặt chặn: [...\G-forwards-tool\setting\rules.txt]
- Mặc định:
```
(?:.+\.)?google.*\.com
(?:.+\.)?gstatic\.com
(?:.+\.)?gmail\.com
(?:.+\.)?ntp\.org
(?:.+\.)?glpals\.com
(?:.+\.)?akamai.*\.net
(?:.+\.)?ggpht\.com
(?:.+\.)?android\.com
(?:.+\.)?gvt1\.com
(?:.+\.)?youtube.*\.com
(?:.+\.)?ytimg\.com
(?:.+\.)?goo\.gl
(?:.+\.)?youtu\.be
(?:.+\.)?google\..+
(?:.+\.)?iphey\.com
```

# API của công cụ:
Chỉnh sửa port server tại : [...\G-forwards-tool\setting\port.ini] Mặc định: 3333.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:3333
 * Running on http://192.168.1.2:3333

> Lưu Ý: Request được khóa 5 giây/lần

![G-forwards-tool](https://github.com/2movn/G-forwards-tool/blob/main/getlist.png?raw=true)
## Thêm Proxy:
- Định dạng request: POST
- Đinh dạng data: json
- url: /add
```
url = 'http://localhost:3333/add'
headers = {'Content-Type': 'application/json'}

data=[
    {
        "api": "ip:port:user:pass",
        "port_local": "12009",
        "proxy_server": "proxylist",
    },
    {
        "api": "api here",
        "port_local": "12009",
        "proxy_server": "tinsoft",
    }
]
```
## Xem List và tính trạng:
- Định dạng request: GET
- url: /list
```
url = 'http://localhost:3333/list'
```
## Xóa API, PROXY:
- Định dạng request: GET
- url: /delete
- parameter: id
```
//Xóa đơn proxy
url = 'http://localhost:3333/delete?id=[uuid]'
//Xóa toàn bộ proxy
url = 'http://localhost:3333/delete?id=all'
```
## Dừng Forward:
- Định dạng request: GET
- url: /stop
- parameter: id
```
//Dừng đơn proxy
url = 'http://localhost:3333/stop?id=[uuid]'
//Dừng toàn bộ proxy
url = 'http://localhost:3333/stop?id=all'
```
## Chạy Forward:
- Định dạng request: GET
- url: /start
- parameter: id
```
//Chạy đơn proxy
url = 'http://localhost:3333/start?id=[uuid]'
//Chạy toàn bộ proxy
url = 'http://localhost:3333/start?id=all'
```
## Reset Forward:
- Định dạng request: GET
- url: /reset
- parameter: id
```
//Reset đơn proxy
url = 'http://localhost:3333/reset?id=[uuid]'
//Reset toàn bộ proxy
url = 'http://localhost:3333/reset?id=all'
```
