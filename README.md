# duaninfotainment
Mô phỏng hệ thống infotainment trên hệ thống Ô tô

# Kế hoạch chi tiết
1.  Yêu cầu các tính năng chính:
- Hệ thống thông tin định vị (AVN): Kết hợp hệ thống âm thanh, video và điều hướng. AVN là trung tâm điều khiển chính cho hầu hết các chức năng giải trí và thông tin, bao gồm radio, phát nhạc, xem phim, dẫn đường bằng GPS, kết nối điện thoại, và truy cập internet.
- Cảnh báo tình trạng xe (Cluster): Hiển thị thông tin quan trọng về xe như tốc độ, vòng tua máy, mức nhiên liệu, nhiệt độ động cơ, cảnh báo an toàn và các thông báo khác. Cluster truyền thống sử dụng đồng hồ analog, nhưng ngày nay nhiều xe sử dụng màn hình kỹ thuật số để hiển thị thông tin một cách linh hoạt và trực quan hơn.
- Mạng trong xe: Kết nối các bộ phận điện tử khác nhau trong xe, cho phép chúng giao tiếp và trao đổi dữ liệu. Mạng trong xe sử dụng các giao thức truyền thông như CAN, LIN, Ethernet để đảm bảo hoạt động đồng bộ và hiệu quả của các hệ thống.

2. Thiết bị sử dụng 
# ESP32: Giả lập các thông số cần cảnh báo trên Cluster ESP32
Xác định các thông số và ngưỡng cảnh báo:
Dưới đây là một số thông số thường được theo dõi và cảnh báo trên Cluster:
| Thông số | Ngưỡng cảnh báo |
|---|---|
| Tốc độ (km/h) | Vượt quá giới hạn tốc độ cho phép |
| Vòng tua máy (RPM) | Vượt quá giới hạn vòng tua an toàn |
| Mức nhiên liệu (%) | Dưới mức nhiên liệu dự trữ |
| Nhiệt độ động cơ (°C) | Vượt quá nhiệt độ hoạt động tối đa |
| Áp suất lốp (PSI) | Thấp hơn áp suất khuyến nghị |
| Cảnh báo an toàn | Đèn báo lỗi động cơ, ABS, túi khí... |

# Laptop mô phỏng hệ thống thông tin định vị (AVN)
# 1. Giao diện người dùng (GUI):
Sử dụng framework/thư viện đã chọn để thiết kế giao diện người dùng cho AVN, bao gồm:
- Màn hình chính với các nút điều khiển cho các chức năng chính (Radio, Media, Navigation, Phone, Settings).
- Màn hình Radio: Hiển thị tên kênh, tần số, nút điều chỉnh âm lượng, nút chuyển kênh.
- Màn hình Media: Hiển thị danh sách bài hát, video, nút Play/Pause, tua đi/lùi, điều chỉnh âm lượng.
- Màn hình Navigation: Hiển thị bản đồ, vị trí hiện tại, điểm đến, chỉ đường.
- Màn hình Phone: Hiển thị danh bạ, nhật ký cuộc gọi, nút thực hiện cuộc gọi, nhận cuộc gọi.
- Màn hình Settings: Các tùy chỉnh cho hệ thống.

# 2. Chức năng:
Radio:
- Sử dụng thư viện âm thanh để phát các kênh radio (có thể sử dụng dữ liệu âm thanh giả lập hoặc stream từ internet).
- Cho phép người dùng điều chỉnh âm lượng, chuyển kênh.

Media:
- Sử dụng thư viện âm thanh/video để phát nhạc và video từ các file lưu trữ trên laptop.
- Cho phép người dùng duyệt danh sách bài hát/video, Play/Pause, tua đi/lùi, điều chỉnh âm lượng.

Navigation:
- Sử dụng thư viện bản đồ (ví dụ: OpenStreetMap) để hiển thị bản đồ và vị trí hiện tại (có thể sử dụng dữ liệu vị trí giả lập).
- Cho phép người dùng nhập điểm đến và tính toán đường đi.
- Hiển thị chỉ đường bằng văn bản hoặc giọng nói.

Phone:
- Sử dụng thư viện Bluetooth để kết nối với điện thoại (nếu có).
- Hiển thị danh bạ, nhật ký cuộc gọi.
- Cho phép người dùng thực hiện và nhận cuộc gọi (có thể sử dụng dữ liệu giả lập).
Settings:
- Cho phép người dùng tùy chỉnh các cài đặt cho hệ thống, ví dụ: ngôn ngữ, độ sáng màn hình, âm lượng mặc định.
