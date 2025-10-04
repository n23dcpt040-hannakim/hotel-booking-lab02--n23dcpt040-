
# Lab02 - Hotel Booking System (Mini Project)

## Mục tiêu
Thiết kế Use Case, Sequence Diagram và ERD cho hệ thống quản lý đặt phòng khách sạn.

## Nội dung repo
- usecase-diagram.puml / usecase-diagram.png
- usecase-descriptions.md
- sequence_booking.puml / sequence_booking.png
- sequence_checkin_checkout.puml / sequence_checkin_checkout.png
- erd.puml / schema.sql
- jira-backlog.md
- Readme.md: file này

## Hướng dẫn mở & export PlantUML
- Cài extension PlantUML cho VSCode hoặc dùng web service https://www.plantuml.com/plantuml.
- Mở file `.puml`, export PNG.

## Link Jira project:
- <https://congnghephanmem123.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog>

## Commit mẫu
---

## 🧾 Commit Log – Hotel Booking System (Lab 02)

| STT | User Story | Commit Message | Jira Key | Mô tả ngắn |
|:---:|:------------|:----------------|:-----------|:-------------|
| 1 | **US-01: Search Rooms** | `git commit -m "US-01 Add: Implement search rooms by date & capacity. HOTEL-01"` | HOTEL-01 | Thêm chức năng tìm phòng theo ngày, loại và sức chứa. |
| 2 | **US-02: View Room Details** | `git commit -m "US-02 Add: View detailed room information page. HOTEL-02"` | HOTEL-02 | Tạo giao diện chi tiết phòng, hiển thị giá, mô tả, tiện nghi. |
| 3 | **US-03: Book Room & Pay Online** | `git commit -m "US-03 Add: Booking flow and payment integration. HOTEL-03"` | HOTEL-03 | Hoàn thiện luồng đặt phòng và tích hợp thanh toán online. |
| 4 | **US-04: Check-in / Check-out (Receptionist)** | `git commit -m "US-04 Add: Receptionist check-in/check-out workflow. HOTEL-04"` | HOTEL-04 | Thêm quy trình lễ tân check-in/check-out và cập nhật trạng thái phòng. |
| 5 | **US-05: Manage Rooms & Prices (Manager)** | `git commit -m "US-05 Add: Room and pricing management module. HOTEL-05"` | HOTEL-05 | Module cho quản lý chỉnh sửa thông tin phòng, giá và mô tả. |
| 6 | **US-06: Revenue Reports (Manager)** | `git commit -m "US-06 Add: Generate revenue report by date range. HOTEL-06"` | HOTEL-06 | Báo cáo doanh thu theo thời gian, có xuất file CSV. |
| 7 | **US-07: Housekeeping Tasks** | `git commit -m "US-07 Add: Housekeeping task management and status update. HOTEL-07"` | HOTEL-07 | Quản lý công việc dọn phòng, cập nhật trạng thái hoàn thành. |




## Tag release
- `git tag v1.0`
- `git push origin v1.0`
