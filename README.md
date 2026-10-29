# PHẦN 1. PHÂN TÍCH VÀ ĐỀ XUẤT

## 1. Phân tích bài toán (I/O)

- **Đầu vào:**
  - Nhóm CampusPay gồm 4 ban: Kỹ thuật, Thiết kế, Kinh doanh và trưởng nhóm.
  - Nhu cầu: trao đổi công việc, chia sẻ file, quản lý deadline và tìm lại tin nhắn cũ.

- **Đầu ra:**
  - Chọn công cụ giao tiếp phù hợp.
  - Hạn chế trôi tin nhắn, mất file và quên nhiệm vụ.

## 2. Ưu điểm và nhược điểm

**Giải pháp A – Zalo**

- Ưu điểm: Miễn phí, quen thuộc, dễ sử dụng, thuận tiện liên lạc với đối tác.
- Nhược điểm: Tin nhắn dễ bị trôi, khó quản lý nhiệm vụ và tìm lại thông tin cũ.

**Giải pháp B – Lark Suite**

- Ưu điểm: Có Channel, Thread, quản lý Task, tìm kiếm tài liệu và tích hợp Calendar.
- Nhược điểm: Cần thời gian làm quen, một số tính năng phụ thuộc gói dịch vụ.

# PHẦN 2. SO SÁNH VÀ LỰA CHỌN

## 3. Bảng so sánh 5 tiêu chí

| Tiêu chí | Zalo | Lark Suite |
|---|---|---|
| Ngăn chặn tin nhắn trôi | ⚠️ | ✅ |
| Quản lý công việc | ❌ | ✅ |
| Miễn phí, dễ cài đặt | ✅ | ⚠️ |
| Tìm kiếm lịch sử | ⚠️ | ✅ |
| Giao tiếp bất đồng bộ | ⚠️ | ✅ |

## 4. Lựa chọn giải pháp

**Chọn kết hợp Lark Suite và Zalo.**

- **Lark:** Dùng để trao đổi nội bộ, quản lý nhiệm vụ, deadline và tài liệu.
- **Zalo:** Dùng để liên lạc với đối tác bên ngoài.

**Giải quyết 3 bẫy dữ liệu:**

1. **Chỉ có điện thoại:** Lark có ứng dụng di động nên vẫn sử dụng được.
2. **Mất 1-2 ngày học:** Chỉ hướng dẫn các tính năng cơ bản và chuyển đổi dần để không ảnh hưởng deadline.
3. **Đối tác chỉ dùng Zalo:** Tiếp tục liên lạc qua Zalo, sau đó cập nhật công việc quan trọng lên Lark.

# PHẦN 3. THIẾT KẾ VÀ TRIỂN KHAI

## 5. Cấu trúc Channel cho CampusPay

| Channel | Mục đích | Quyền đăng bài |
|---|---|---|
| `#thong-bao` | Thông báo quan trọng, deadline | Trưởng nhóm và người được phân công |
| `#dev` | Trao đổi kỹ thuật, API, mã nguồn | Ban Kỹ thuật và người liên quan |
| `#design` | Chia sẻ thiết kế UI, hình ảnh | Ban Thiết kế và người liên quan |
| `#kinh-doanh` | Business Plan, khách hàng, đối tác | Ban Kinh doanh và người liên quan |
| `#task-deadline` | Giao việc, cập nhật tiến độ | Tất cả thành viên |
| `#general` | Trao đổi chung | Tất cả thành viên |

### Quy tắc cờ đỏ chống spam `@all`

- **Cờ xanh:** Trao đổi bình thường, không dùng `@all`.
- **Cờ vàng:** Sắp đến deadline, chỉ nhắc người liên quan.
- **Cờ đỏ:** Chỉ dùng `@all` khi có sự cố nghiêm trọng ảnh hưởng đến toàn nhóm.

Ngoài ra, cần đăng đúng kênh và dùng Thread để tránh làm loãng nội dung chính.
