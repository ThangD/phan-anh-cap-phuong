# Business Analysis Document
## Hệ Thống Phản Ánh Kiến Nghị Cấp Phường

**Ngày tạo:** 29/12/2025  
**Phiên bản:** 2.0  
**Dự án:** Hệ thống phản ánh kiến nghị cấp phường

---

## 1. Executive Summary

### 1.1 Tổng quan dự án
Xây dựng hệ thống trang web đơn giản cho phép người dân gửi phản ánh, kiến nghị về các vấn đề liên quan đến đời sống tại phường **mà không cần đăng ký hay đăng nhập**. Đồng thời, cung cấp công cụ quản lý và thống kê cho cán bộ phường thông qua trang quản trị với phân quyền rõ ràng.

**Đặc điểm chính:**
- Người dân gửi phản ánh đơn giản, không cần đăng nhập
- Tra cứu tiến độ xử lý qua mã số
- KHÔNG có diễn đàn công khai
- Cán bộ phường quản lý qua trang quản trị riêng

### 1.2 Mục tiêu
- Tạo kênh phản ánh dễ tiếp cận, đơn giản cho người dân
- Quản lý và xử lý phản ánh có hệ thống, minh bạch
- Cung cấp công cụ thống kê để cải thiện chất lượng phục vụ
- Tiết kiệm thời gian cho cả người dân và cán bộ

### 1.3 Phạm vi
- Áp dụng cho cấp phường
- Tất cả các lĩnh vực: hạ tầng, môi trường, an ninh, dịch vụ công...
- Trang web đơn giản, không phức tạp

---

## 2. Business Context

### 2.1 Bối cảnh kinh doanh
Trong bối cảnh chuyển đổi số đang diễn ra mạnh mẽ tại Việt Nam, các cấp chính quyền địa phương cần có công cụ để:
- Thu thập ý kiến người dân về các dịch vụ công số
- Giải đáp thắc mắc và hướng dẫn sử dụng
- Tiếp nhận phản ánh về chất lượng dịch vụ
- Cải thiện liên tục các dịch vụ số

### 2.2 Vấn đề hiện tại
- Thiếu kênh phản hồi trực tiếp về chuyển đổi số ở cấp phường
- Người dân gặp khó khăn trong việc gửi ý kiến, kiến nghị
- Quá trình xử lý phản ánh chưa được theo dõi chặt chẽ
- Thiếu tính minh bạch trong việc giải quyết các vấn đề

### 2.3 Giải pháp đề xuất
Xây dựng trang web cho phép:
- **Người dân**: Gửi phản ánh dễ dàng (không cần đăng ký), tra cứu tiến độ qua mã số
- **Cán bộ phường**: Quản lý, xử lý phản ánh qua trang quản trị
- **Lãnh đạo**: Xem thống kê, báo cáo để đánh giá và cải thiện

**Không bao gồm:**
- Diễn đàn công khai
- Chức năng comment, thảo luận
- Yêu cầu đăng ký/đăng nhập cho người dân

---

## 3. Stakeholder Analysis

### 3.1 Các bên liên quan chính

| Stakeholder | Vai trò | Mục tiêu | Ảnh hưởng |
|-------------|---------|----------|-----------|
| Người dân phường | Người sử dụng chính | Gửi phản ánh, theo dõi tiến độ xử lý | Cao |
| Hội đồng nhân dân phường | Đơn vị xử lý phản hồi | Tiếp nhận, phân loại, xử lý và phản hồi | Cao |
| Ban/Phòng chuyên môn | Đơn vị phối hợp | Giải quyết các vấn đề chuyên môn | Trung bình |
| Lãnh đạo phường | Giám sát | Theo dõi hiệu quả giải quyết | Cao |
| Ban Quản lý dự án CĐS | Chủ đầu tư | Triển khai và vận hành hệ thống | Cao |

### 3.2 Người dùng cuối

**Người dân:**
- Độ tuổi: 18-70+
- Trình độ công nghệ: Từ cơ bản đến nâng cao
- Thiết bị: Smartphone, máy tính
- Nhu cầu: Gửi phản ánh dễ dàng, nhanh chóng, theo dõi tiến độ

**Cán bộ phường:**
- Độ tuổi: 25-60
- Trình độ công nghệ: Trung bình đến tốt
- Thiết bị: Máy tính, tablet
- Nhu cầu: Quản lý phản ánh hiệu quả, báo cáo nhanh

---

## 4. Business Requirements

### 4.1 Functional Requirements

#### 4.1.1 Cho người dân (KHÔNG cần đăng nhập)

**Gửi phản ánh:**
- Truy cập trang web
- Điền form với thông tin:
  - Họ tên
  - Số điện thoại (bắt buộc)
  - Email (tùy chọn)
  - Địa chỉ
  - Loại vấn đề (hạ tầng, môi trường, an ninh...)
  - Mô tả chi tiết
  - Đính kèm ảnh/video
  - Chọn vị trí trên bản đồ (nếu có)
- Nhận mã số phản ánh ngay sau khi gửi
- Nhận SMS/Email xác nhận

**Tra cứu tiến độ:**
- Nhập mã số phản ánh
- Xem trạng thái và lịch sử xử lý
- Đọc phản hồi từ cán bộ
- Không cần đăng nhập

**Đánh giá:**
- Nhận link đánh giá qua SMS/Email
- Đánh giá sao và viết nhận xét
- Không cần đăng nhập

#### 4.1.2 Cho cán bộ phường (CÓ đăng nhập)

**Cán bộ tiếp nhận:**
- Xem danh sách phản ánh mới
- Phân loại và gắn nhãn
- Đánh giá mức độ ưu tiên

**Lãnh đạo:**
- Phân công xử lý cho cán bộ/phòng ban
- Xem báo cáo tổng quan
- Xuất báo cáo

**Cán bộ xử lý:**
- Xem phản ánh được giao
- Cập nhật tiến độ xử lý
- Trả lời người dân
- Đính kèm hình ảnh/tài liệu kết quả

**Admin:**
- Quản lý tài khoản cán bộ
- Cấu hình hệ thống
- Xem audit log

### 4.2 Non-Functional Requirements

#### 4.2.1 Đơn giản và dễ sử dụng
- Giao diện thân thiện, rõ ràng
- Hoạt động tốt trên điện thoại
- Tốc độ tải trang nhanh (< 3 giây)

#### 4.2.2 Bảo mật
- Mã hóa dữ liệu (HTTPS)
- Phân quyền rõ ràng cho cán bộ
- Bảo vệ thông tin cá nhân người dân

#### 4.2.3 Độ tin cậy
- Hoạt động ổn định (uptime ≥ 99%)
- Backup dữ liệu tự động
- Khôi phục nhanh khi có sự cố

---

## 5. User Stories

### 5.1 Người dân

**US-001:** Tôi muốn gửi phản ánh nhanh chóng mà không cần đăng ký
- Truy cập web
- Điền form đơn giản
- Nhận mã số ngay

**US-002:** Tôi muốn biết phản ánh của mình đang được xử lý như thế nào
- Nhập mã số
- Xem trạng thái và phản hồi
- Không cần đăng nhập

**US-003:** Tôi muốn đánh giá kết quả sau khi vấn đề được giải quyết
- Nhận link qua SMS/Email
- Đánh giá và viết nhận xét

### 5.2 Cán bộ phường

**US-004:** Tôi muốn xem và phân loại phản ánh mới
- Đăng nhập hệ thống
- Xem danh sách phản ánh
- Phân loại nhanh chóng

**US-005:** Tôi muốn cập nhật tiến độ xử lý
- Ghi nhận các bước đã làm
- Người dân nhận được thông báo

**US-006:** Tôi muốn xem báo cáo để biết tình hình chung
- Dashboard trực quan
- Xuất báo cáo dễ dàng

---

## 6. Process Flow

### 6.1 Quy trình cơ bản

```
NGƯỜI DÂN (không đăng nhập)
          ↓
    Gửi phản ánh qua web
          ↓
    AI TỰ ĐỘNG PHÂN LOẠI
    (phân tích nội dung, hình ảnh)
          ↓
    Nhận mã số ngay lập tức
          ↓
    Nhận SMS/Email xác nhận
          
          ↓
          
CÁN BỘ PHƯỜNG (có đăng nhập)
          ↓
    Nhận thông báo với kết quả phân loại AI
          ↓
    Xác nhận/điều chỉnh phân loại AI
          ↓
    Phân công xử lý cho cán bộ
          ↓
    Cán bộ xử lý cập nhật tiến độ
          ↓
    Gửi thông báo cho người dân
          ↓
    Hoàn thành và gửi phản hồi
          
          ↓
          
NGƯỜI DÂN (không đăng nhập)
          ↓
    Tra cứu tiến độ qua mã số
          ↓
    Nhận link đánh giá
          ↓
    Đánh giá kết quả
          ↓
    AI học từ feedback
```

### 6.2 Thời gian xử lý đề xuất

- **AI phân loại tự động:** 0-2 giờ
- **Xác nhận phân loại:** 2-24 giờ
- **Phân công xử lý:** 24-48 giờ
- **Xử lý vấn đề:** 7-15 ngày (tùy mức độ)
- **Phản hồi chính thức:** 1-2 ngày sau khi xử lý xong

---

## 7. Success Metrics & KPIs

### 7.1 Chỉ số thành công

**Về sử dụng:**
- Số lượng phản ánh được gửi
- Tỷ lệ phản ánh có đủ thông tin
- Số lượt tra cứu tiến độ

**Về hiệu quả xử lý:**
- Thời gian phản hồi trung bình
- Tỷ lệ giải quyết đúng hạn (≥ 80%)
- Mức độ hài lòng người dân (≥ 4.0/5.0)

**Mục tiêu năm đầu:**
- 500 phản ánh
- 80% được trả lời trong 7 ngày
- 90% được giải quyết trong 30 ngày

---

## 8. Risks & Mitigation

### 8.1 Rủi ro

| Rủi ro | Giải pháp |
|--------|-----------|
| Người dân không biết hệ thống | Truyền thông rộng rãi, tờ rơi, hướng dẫn tại trụ sở |
| Phản ánh spam | CAPTCHA, giới hạn số lần gửi, kiểm duyệt |
| Người dân quên mã số | Gửi SMS/Email nhắc nhở, hỗ trợ tra cứu |
| Cán bộ chưa quen | Đào tạo kỹ lưỡng, hướng dẫn chi tiết |

---

## 9. Implementation Plan

### 9.1 Kế hoạch triển khai

**Tháng 1-3: Phát triển**
- Xây dựng trang web cơ bản
- Trang gửi phản ánh
- Trang tra cứu
- Trang quản trị

**Tháng 4-5: Hoàn thiện**
- Thêm báo cáo thống kê
- Cải thiện giao diện
- Tích hợp SMS/Email

**Tháng 6: Thử nghiệm**
- Test với nhóm người dùng thực
- Sửa lỗi
- Điều chỉnh

**Tháng 7: Ra mắt**
- Đào tạo cán bộ
- Truyền thông cho dân
- Vận hành chính thức

### 9.2 Nguồn lực cần thiết

**Sẽ được cập nhật sau khi:**
- Xác định rõ phạm vi và yêu cầu chi tiết
- Đánh giá khả năng nguồn lực hiện có của Phường
- Tham khảo ý kiến từ các bên liên quan

**Dự kiến bao gồm:**
- Đội ngũ phát triển (số lượng và vai trò)
- Thời gian triển khai
- Chi phí ước tính (phát triển, hạ tầng, vận hành)
- Nhân lực hỗ trợ và vận hành

---

## 10. Assumptions & Constraints

### 10.1 Giả định
- Phường có internet ổn định
- Người dân có smartphone hoặc máy tính
- Cán bộ biết sử dụng máy tính cơ bản

### 10.2 Ràng buộc
- Không yêu cầu người dân đăng ký
- Không có diễn đàn công khai
- Phải đơn giản, dễ dùng
- Ngân sách 

---

## 11. Next Steps

### 11.1 Hành động tiếp theo

1. **Xin phê duyệt từ lãnh đạo phường**
2. **Xác nhận ngân sách**
3. **Chọn đơn vị phát triển**
4. **Kick-off dự án**

### 11.2 Câu hỏi cần làm rõ

1. Phường có tên miền (domain) riêng chưa?
2. Ngân sách SMS là bao nhiêu tin/tháng? (Ước tính 500 tin/tháng)
3. Hosting tại Việt Nam hay quốc tế?
4. Thời hạn xử lý mỗi loại phản ánh?
5. Ai phê duyệt phản hồi trước khi gửi cho dân?
6. Chỉ cung cấp mã nguồn và ứng dụng, phần cứng (license nếu có) bên Phường sẽ lo?
7. Chi phí maintenance khoảng 10-12%/năm của chi phí phát triển ban đầu?

---

## 12. Liên hệ

Nếu có thắc mắc hoặc cần thêm thông tin, vui lòng liên hệ:

**Team Dự án:**
- Email: [email dự án]
- Phone: [số điện thoại]

---

## 13. Approval

**Chuẩn bị bởi:**
Tên: ________________
Chức vụ: Business Analyst
Ngày: 29/12/2025

**Phê duyệt bởi (Phường):**
Tên: ________________
Chức vụ: ________________
Ngày: ________________

---

**Tài liệu này được chuẩn bị cho Phường để xem xét và phê duyệt.**
**Chi tiết kỹ thuật sẽ được cung cấp sau khi được phê duyệt.**
