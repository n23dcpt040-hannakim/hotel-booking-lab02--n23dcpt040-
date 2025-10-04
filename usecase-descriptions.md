# Use Case Descriptions

---

## UC-01: Book Room (Online)
- **Mã:** UC-01
- **Tên:** Đặt phòng online
- **Tác nhân:** Guest (Khách hàng)
- **Mô tả ngắn:** Khách hàng tìm phòng, chọn ngày, điền thông tin, thực hiện thanh toán và nhận xác nhận.
- **Tiền điều kiện (Preconditions):**
  - Khách đã truy cập trang web/app.
  - RoomType và Room có sẵn trong hệ thống.
- **Luồng chính (Main Flow):**
  1. Guest tìm phòng theo ngày/loại/giá.
  2. Hệ thống hiển thị danh sách phòng còn trống.
  3. Guest chọn phòng và nhấn "Đặt".
  4. Hệ thống tạm giữ phòng (hold) trong khoảng thời gian X phút.
  5. Guest nhập thông tin cá nhân (name, phone, email) và thông tin thanh toán.
  6. Hệ thống gọi Payment Gateway (UC-03).
  7. Payment Gateway trả kết quả thành công → Hệ thống tạo Reservation (status = CONFIRMED).
  8. Hệ thống gửi email/SMS xác nhận cho Guest.
- **Luồng thay thế (Alternate flows):**
  - 6a. Nếu thanh toán thất bại: hệ thống huỷ hold, thông báo cho Guest; Guest có thể thử lại.
  - 4a. Nếu thời gian hold hết hạn: hiển thị lỗi "phòng không còn".
- **Hậu điều kiện (Postconditions):**
  - Nếu thành công: Reservation được lưu (status CONFIRMED); email xác nhận đã gửi.
  - Nếu thất bại: không có Reservation; Guest được thông báo.
- **Mức ưu tiên:** Cao
- **Tần suất:** Cao

---

## UC-02: Check-in / Check-out (Receptionist)
- **Mã:** UC-02
- **Tên:** Check-in / Check-out
- **Tác nhân:** Receptionist (Lễ tân)
- **Mô tả ngắn:** Lễ tân xác nhận mã đặt phòng, gán phòng khi khách tới, và xử lý thanh toán khi khách trả phòng.
- **Tiền điều kiện:**
  - Đã có Reservation (status = CONFIRMED).
- **Luồng chính (Check-in):**
  1. Receptionist nhập mã đặt phòng (ResvID) hoặc tìm theo tên.
  2. Hệ thống hiển thị chi tiết Reservation.
  3. Receptionist gán RoomID cụ thể (nếu chưa gán).
  4. Hệ thống cập nhật Reservation status -> CHECKED_IN; cập nhật Room status -> OCCUPIED.
  5. (Tùy chọn) In phiếu arrival.
- **Luồng chính (Check-out):**
  1. Receptionist chọn Reservation cần check-out.
  2. Hệ thống tổng hợp chi phí (room rate, dịch vụ phát sinh).
  3. Receptionist xử lý thanh toán (cash hoặc gọi Payment Gateway nếu cần).
  4. Hệ thống cập nhật Reservation status -> COMPLETED; Room status -> AVAILABLE.
  5. Ghi log công việc housekeeping (gửi request cho Housekeeping).
- **Luồng thay thế:**
  - Nếu guest muốn gia hạn: tạo booking extension và cập nhật ngày CheckOut.
- **Hậu điều kiện:**
  - Sau checkout: phòng sẵn sàng cho housekeeping, thanh toán hoàn tất.
- **Mức ưu tiên:** Cao
- **Tần suất:** Trung bình-cao
