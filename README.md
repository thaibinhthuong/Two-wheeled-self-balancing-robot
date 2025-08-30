# Robot Tự Cân Bằng 2 Bánh

## Giới thiệu
Dự án này hiện thực một robot 2 bánh tự cân bằng sử dụng cảm biến MPU6050, thuật toán PID và lập trình đa luồng với FreeRTOS.  
Robot có khả năng giữ thăng bằng theo phương thẳng đứng, điều khiển 2 động cơ thông qua mạch cầu H (L298N hoặc TB6612).

---

## Phần cứng sử dụng
- Khung xe 2 bánh và trục động cơ
- 2 động cơ giảm tốc DC
- Driver động cơ: L298N hoặc TB6612
- Cảm biến: MPU6050 (gia tốc và gyroscope)
- Vi điều khiển: ESP8266 , cũng có thể sử dụng ESP32(khuyến nghị, hỗ trợ FreeRTOS tốt)
- Nguồn: pin 3 cell AA hoặc pin Li-ion 7.4V
- Công tắc nguồn, dây điện, hộp pin

---

## Phần mềm và công nghệ
- Ngôn ngữ: C/C++
- IDE: Arduino IDE hoặc PlatformIO
- Hệ điều hành thời gian thực: FreeRTOS
- Thư viện cần thiết:
  - Wire.h (I2C giao tiếp MPU6050)
  - MPU6050.h hoặc Adafruit_MPU6050
  - Arduino_FreeRTOS.h (nếu dùng Arduino) hoặc native FreeRTOS (nếu ESP32)
  - PID_v1.h (thuật toán PID)

---

## Cách chạy dự án
1. Cài đặt Arduino IDE hoặc PlatformIO.
2. Cài thư viện cần thiết (MPU6050, PID, FreeRTOS).
3. Kết nối ESP32 với máy tính qua cổng USB.
4. Cấp nguồn cho robot và đặt trên mặt phẳng.
5. Robot sẽ tự cân bằng nếu PID được tinh chỉnh đúng.

---

## Ghi chú
- Các hằng số PID (Kp, Ki, Kd) cần tinh chỉnh thực nghiệm.
- Pin cần đủ dòng để động cơ hoạt động ổn định.
- Có thể mở rộng thêm chức năng như: điều khiển từ xa bằng Bluetooth/WiFi, hiển thị dữ liệu trên màn hình OLED, hoặc logging dữ liệu ra Serial để phân tích.
