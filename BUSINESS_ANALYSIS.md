# Business Analysis Document
## Hệ Thống Phản Ánh Kiến Nghị Cấp Phường

**Ngày tạo:** 29/12/2025  
**Phiên bản:** 2.0  
**Dự án:** Hệ thống phản ánh kiến nghị liên quan đến chuyển đổi số cấp phường

---

## 1. Executive Summary

### 1.1 Tổng quan dự án
Xây dựng hệ thống trang web đơn giản cho phép tiếp nhận phản ánh, kiến nghị từ người dân về các vấn đề liên quan đến đời sống, hạ tầng, môi trường tại phường. Người dân có thể gửi phản ánh **mà không cần đăng nhập**, trong khi cán bộ phường sử dụng trang quản trị với phân quyền để quản lý và xử lý các phản ánh.

**Lưu ý quan trọng:** Đây không phải là diễn đàn công khai, mà chỉ là công cụ tiếp nhận và quản lý phản ánh.

### 1.2 Mục tiêu
- Tạo kênh phản ánh đơn giản, dễ tiếp cận cho người dân (không cần đăng nhập)
- Quản lý và xử lý phản ánh một cách có hệ thống
- Nâng cao tính minh bạch thông qua khả năng tra cứu tiến độ
- Cung cấp công cụ thống kê và báo cáo cho chính quyền phường
- Đơn vị phản hồi: Hội đồng nhân dân phường và các ban/phòng chuyên môn

### 1.3 Phạm vi
- Áp dụng cho cấp phường
- Không giới hạn lĩnh vực phản ánh (hạ tầng, môi trường, an ninh, dịch vụ công, chuyển đổi số...)
- Hệ thống web đơn giản, không có tính năng diễn đàn

---

## 2. Business Context

### 2.1 Bối cảnh kinh doanh
Trong bối cảnh chuyển đổi số đang diễn ra mạnh mẽ tại Việt Nam, các cấp chính quyền địa phương cần có công cụ để:
- Thu thập ý kiến người dân về các dịch vụ công số
- Giải đáp thắc mắc và hướng dẫn sử dụng
- Tiếp nhận phản ánh về chất lượng dịch vụ
- Cải thiện liên tục các dịch vụ số

### 2.2 Vấn đề hiện tại
- Thiếu kênh phản hồi trực tiếp, dễ tiếp cận ở cấp phường
- Người dân phải đến trực tiếp hoặc gọi điện, không tiện lợi
- Quá trình xử lý phản ánh chưa được theo dõi chặt chẽ
- Thiếu tính minh bạch trong việc giải quyết các vấn đề
- Khó khăn trong việc thống kê và báo cáo

### 2.3 Giải pháp đề xuất
Xây dựng trang web đơn giản cho phép:
- **Người dân**: Gửi phản ánh dễ dàng mà không cần đăng ký/đăng nhập, tra cứu tiến độ qua mã số
- **Cán bộ phường**: Quản lý phản ánh qua trang quản trị với phân quyền rõ ràng
- **Lãnh đạo**: Xem thống kê và báo cáo tổng quan
- Không có diễn đàn công khai, chỉ tập trung vào quản lý phản ánh

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

**Người dân (không cần đăng nhập):**
- Độ tuổi: 18-70+
- Trình độ công nghệ: Từ cơ bản đến nâng cao
- Thiết bị: Smartphone, máy tính
- Nhu cầu: Gửi phản ánh nhanh chóng không cần đăng ký, tra cứu tiến độ đơn giản

**Cán bộ phường (có đăng nhập):**
- Độ tuổi: 25-60
- Trình độ công nghệ: Trung bình đến tốt
- Thiết bị: Máy tính, tablet
- Nhu cầu: Quản lý phản ánh hiệu quả, thống kê báo cáo nhanh

---

## 4. Business Requirements

### 4.1 Functional Requirements

#### 4.1.1 Quản lý người dùng (Chỉ cho cán bộ phường)
- **FR-001:** Hệ thống xác thực cán bộ phường
  - Đăng nhập bằng username/password
  - Xác thực 2 yếu tố (2FA) cho bảo mật cao
  
- **FR-002:** Phân quyền người dùng (cán bộ)
  - **Cán bộ tiếp nhận**: Xem, phân loại phản ánh mới
  - **Cán bộ xử lý**: Cập nhật tiến độ, trả lời phản ánh được giao
  - **Lãnh đạo**: Phân công công việc, xem toàn bộ thống kê và báo cáo
  - **Admin**: Quản trị hệ thống, quản lý user

**Lưu ý:** Người dân KHÔNG cần đăng ký/đăng nhập

#### 4.1.2 Quản lý phản ánh (Người dân - Không đăng nhập)

- **FR-003:** Gửi phản ánh (không cần đăng nhập)
  - Form đơn giản với các trường:
    - Họ tên người gửi
    - Số điện thoại (bắt buộc - để liên hệ)
    - Email (tùy chọn)
    - Địa chỉ (bắt buộc)
    - Tiêu đề phản ánh
    - Nội dung chi tiết
    - Phân loại (hạ tầng, môi trường, an ninh trật tự, dịch vụ công, chuyển đổi số, khác)
    - Đính kèm hình ảnh/video (tối đa 5 file, mỗi file < 10MB)
    - Vị trí địa lý (tùy chọn - chọn trên bản đồ)
  - Sau khi gửi:
    - Nhận mã số phản ánh duy nhất
    - Có thể lưu hoặc chụp màn hình mã số
    - Nhận SMS/Email xác nhận (nếu có cung cấp)
  
- **FR-004:** Tra cứu tiến độ (không cần đăng nhập)
  - Nhập mã số phản ánh để tra cứu
  - Xem được:
    - Thông tin phản ánh đã gửi
    - Trạng thái hiện tại (Mới, Đang xử lý, Đã giải quyết, Đóng)
    - Lịch sử xử lý (timeline)
    - Phản hồi từ cán bộ
  - Nhận thông báo qua SMS/Email khi có cập nhật (nếu đã cung cấp)
  
- **FR-005:** Đánh giá kết quả (qua link trong SMS/Email)
  - Đánh giá sao (1-5)
  - Viết nhận xét ngắn
  - Yêu cầu xử lý thêm nếu chưa hài lòng

**Loại bỏ:** 
- ~~Đăng ký tài khoản~~
- ~~Đăng nhập~~
- ~~Xem danh sách phản ánh của mình~~
- ~~Diễn đàn công khai~~
- ~~Comment, thảo luận~~
- ~~Upvote/downvote~~

#### 4.1.3 Xử lý phản ánh (Cán bộ - Có đăng nhập)

- **FR-006:** Tiếp nhận và phân loại
  - Dashboard hiển thị phản ánh mới theo thời gian thực
  - Xem chi tiết phản ánh
  - Xác nhận hoặc điều chỉnh phân loại
  - Đánh giá mức độ ưu tiên (Thấp, Trung bình, Cao, Khẩn cấp)
  - Gắn nhãn, tag
  
- **FR-007:** Phân công xử lý (Lãnh đạo)
  - Chọn ban/phòng phụ trách
  - Chỉ định cán bộ xử lý cụ thể
  - Thiết lập thời hạn xử lý
  - Thêm ghi chú nội bộ
  
- **FR-008:** Xử lý và cập nhật tiến độ (Cán bộ xử lý)
  - Cập nhật trạng thái xử lý
  - Ghi nhận các bước xử lý
  - Yêu cầu bổ sung thông tin từ người dân (gọi điện hoặc gửi SMS)
  - Chuyển phản ánh cho đơn vị khác nếu cần
  - Đính kèm tài liệu, hình ảnh minh chứng kết quả
  - Soạn thảo phản hồi chính thức
  
- **FR-009:** Quản lý workflow
  - Lịch sử xử lý đầy đủ (audit trail)
  - Cảnh báo phản ánh quá hạn
  - Thông báo tự động cho người được phân công
  - Khả năng mở lại phản ánh đã đóng

#### 4.1.4 Báo cáo và thống kê (Cán bộ có quyền)

- **FR-010:** Dashboard tổng quan (Lãnh đạo)
  - Tổng số phản ánh theo trạng thái
  - Biểu đồ xu hướng theo thời gian
  - Thời gian xử lý trung bình
  - Tỷ lệ giải quyết đúng hạn
  - Mức độ hài lòng trung bình
  - Top các vấn đề phổ biến
  - Hiệu suất xử lý theo phòng ban/cán bộ
  
- **FR-011:** Báo cáo chi tiết
  - Báo cáo theo lĩnh vực
  - Báo cáo theo khu vực địa lý
  - Báo cáo theo thời gian (ngày/tuần/tháng/quý/năm)
  - Báo cáo theo cán bộ xử lý
  - Xuất báo cáo (PDF, Excel)
  - Lọc và tìm kiếm nâng cao

- **FR-012:** Thông báo tự động
  - Thông báo cho cán bộ khi có phản ánh mới
  - Cảnh báo phản ánh quá hạn
  - Thông báo khi được phân công
  - Gửi SMS/Email cho người dân khi có cập nhật

### 4.2 Non-Functional Requirements

#### 4.2.1 Performance
- **NFR-001:** Thời gian tải trang < 3 giây
- **NFR-002:** Hỗ trợ 1000 người dùng đồng thời
- **NFR-003:** Uptime 99.5%
- **NFR-004:** Thời gian xử lý upload file < 5 giây (file < 10MB)

#### 4.2.2 Security
- **NFR-005:** Mã hóa dữ liệu truyền tải (HTTPS/TLS)
- **NFR-006:** Mã hóa dữ liệu nhạy cảm trong database
- **NFR-007:** Xác thực 2 yếu tố (2FA) cho cán bộ
- **NFR-008:** Phân quyền chi tiết theo role
- **NFR-009:** Audit log đầy đủ
- **NFR-010:** Tuân thủ GDPR/Nghị định 13 về bảo vệ dữ liệu cá nhân

#### 4.2.3 Usability
- **NFR-011:** Giao diện đơn giản, dễ sử dụng
- **NFR-012:** Responsive design (mobile-first)
- **NFR-013:** Hỗ trợ đa ngôn ngữ (Tiếng Việt ưu tiên)
- **NFR-014:** Hỗ trợ accessibility (WCAG 2.1 Level A)
- **NFR-015:** Tích hợp voice input cho người dùng

#### 4.2.4 Compatibility
- **NFR-016:** Hỗ trợ các trình duyệt: Chrome, Firefox, Safari, Edge (2 phiên bản mới nhất)
- **NFR-017:** Hỗ trợ iOS 14+ và Android 8+
- **NFR-018:** Tích hợp với hệ thống 1022 của thành phố
- **NFR-019:** API mở cho tích hợp với các hệ thống khác

#### 4.2.5 Scalability & Maintenance
- **NFR-020:** Kiến trúc microservices
- **NFR-021:** Database có thể scale horizontal
- **NFR-022:** Hỗ trợ backup tự động hàng ngày
- **NFR-023:** Khả năng rollback khi có sự cố
- **NFR-024:** Monitoring và alerting

---

## 5. User Stories

### 5.1 Người dân (không đăng nhập)

**Epic 1: Gửi và theo dõi phản ánh**

- **US-001:** Là người dân, tôi muốn gửi phản ánh mà không cần đăng ký tài khoản
  - **Acceptance Criteria:**
    - Truy cập trang web, nhấn "Gửi phản ánh"
    - Điền form đơn giản (họ tên, SĐT, địa chỉ, nội dung)
    - Đính kèm ảnh/video nếu cần
    - Nhận mã số phản ánh ngay sau khi gửi
    - Nhận SMS/Email xác nhận

- **US-002:** Là người dân, tôi muốn tra cứu tiến độ xử lý phản ánh của mình
  - **Acceptance Criteria:**
    - Nhập mã số phản ánh vào ô tra cứu
    - Xem được trạng thái và lịch sử xử lý
    - Đọc được phản hồi từ cán bộ
    - Không cần đăng nhập

- **US-003:** Là người dân, tôi muốn đánh giá kết quả xử lý
  - **Acceptance Criteria:**
    - Nhận link đánh giá qua SMS/Email
    - Click vào link, đánh giá sao và viết nhận xét
    - Không cần đăng nhập

### 5.2 Cán bộ tiếp nhận

**Epic 2: Quản lý phản ánh mới**

- **US-004:** Là cán bộ tiếp nhận, tôi muốn xem danh sách phản ánh mới
  - **Acceptance Criteria:**
    - Đăng nhập vào hệ thống
    - Dashboard hiển thị phản ánh mới theo thời gian
    - Sắp xếp, lọc theo nhiều tiêu chí
    - Xem chi tiết từng phản ánh

- **US-005:** Là cán bộ tiếp nhận, tôi muốn phân loại phản ánh
  - **Acceptance Criteria:**
    - Xác nhận hoặc thay đổi phân loại
    - Đánh giá mức độ ưu tiên
    - Gắn nhãn, tag
    - Thêm ghi chú nội bộ

### 5.3 Lãnh đạo

**Epic 3: Phân công và giám sát**

- **US-006:** Là lãnh đạo, tôi muốn phân công xử lý phản ánh
  - **Acceptance Criteria:**
    - Xem danh sách phản ánh đã phân loại
    - Chọn cán bộ/phòng ban xử lý
    - Thiết lập thời hạn
    - Gửi thông báo phân công tự động

- **US-007:** Là lãnh đạo, tôi muốn xem báo cáo tổng quan
  - **Acceptance Criteria:**
    - Dashboard với KPIs rõ ràng
    - Biểu đồ trực quan
    - Xuất báo cáo
    - So sánh theo thời kỳ

### 5.4 Cán bộ xử lý

**Epic 4: Xử lý phản ánh**

- **US-008:** Là cán bộ xử lý, tôi muốn xử lý các phản ánh được giao
  - **Acceptance Criteria:**
    - Xem danh sách công việc được giao
    - Cập nhật tiến độ xử lý
    - Đính kèm hình ảnh/tài liệu kết quả
    - Soạn phản hồi cho người dân

- **US-009:** Là cán bộ xử lý, tôi muốn được nhắc nhở về deadline
  - **Acceptance Criteria:**
    - Nhận cảnh báo khi gần đến hạn
    - Xem danh sách công việc quá hạn
    - Yêu cầu gia hạn nếu cần

---

## 6. Process Flow

### 6.1 Quy trình xử lý phản ánh (đã cập nhật)

```
[Người dân truy cập web và gửi phản ánh - KHÔNG CẦN ĐĂNG NHẬP]
          ↓
[Hệ thống tiếp nhận & tạo mã phản ánh duy nhất]
          ↓
[Gửi SMS/Email xác nhận cho người dân với mã số]
          ↓
[Thông báo cho cán bộ tiếp nhận]
          ↓
[Cán bộ tiếp nhận phân loại và đánh giá ưu tiên]
          ↓
[Lãnh đạo phân công cho cán bộ/phòng ban xử lý]
          ↓
[Cán bộ xử lý cập nhật tiến độ định kỳ]
          ↓
[Gửi thông báo cập nhật cho người dân (SMS/Email)]
          ↓
[Hoàn thành xử lý và gửi phản hồi chính thức]
          ↓
[Gửi link đánh giá cho người dân]
          ↓
[Người dân đánh giá (không cần đăng nhập)]
          ↓
[Đóng phản ánh hoặc mở lại nếu cần]
```

### 6.2 Quy trình chi tiết với timeline

**Giai đoạn 1: Tiếp nhận (0-24h)**
1. Người dân gửi phản ánh qua web
2. Hệ thống tự động:
   - Tạo mã phản ánh
   - Gửi xác nhận cho người dân
   - Phân loại sơ bộ bằng AI
   - Thông báo cho cán bộ tiếp nhận

**Giai đoạn 2: Phân loại và định tuyến (24-48h)**
3. Cán bộ tiếp nhận:
   - Xác nhận phân loại
   - Đánh giá mức độ ưu tiên
   - Chuyển cho ban/phòng phù hợp
   - Thiết lập thời hạn xử lý

**Giai đoạn 3: Xử lý (2-7 ngày)**
4. Cán bộ chuyên môn:
   - Nghiên cứu vấn đề
   - Thu thập thêm thông tin nếu cần
   - Phối hợp giải quyết
   - Cập nhật tiến độ định kỳ

**Giai đoạn 4: Phản hồi (1-2 ngày)**
5. Hội đồng nhân dân phường:
   - Xem xét kết quả xử lý
   - Phê duyệt phản hồi
   - Gửi phản hồi chính thức cho người dân

**Giai đoạn 5: Đánh giá (3 ngày)**
6. Người dân:
   - Nhận phản hồi
   - Đánh giá mức độ hài lòng
   - Yêu cầu xử lý thêm hoặc chấp nhận

**Giai đoạn 6: Đóng (1 ngày)**
7. Hệ thống:
   - Đóng phản ánh
   - Lưu trữ dữ liệu
   - Cập nhật thống kê
   - Công khai (nếu được đồng ý)

---

## 7. Data Requirements

### 7.1 Entities chính (đã cập nhật)

#### Feedback (Phản ánh - không cần user_id)
- feedback_id (PK)
- tracking_code (mã tra cứu duy nhất)
- citizen_name (họ tên người gửi)
- citizen_phone (SĐT - bắt buộc)
- citizen_email (email - tùy chọn)
- citizen_address (địa chỉ)
- title
- description
- category (infrastructure, environment, security, public_service, digital_transformation, other)
- priority (low, medium, high, urgent)
- status (new, assigned, in_progress, resolved, closed, reopened)
- location (lat, long)
- attachments (JSON)
- created_at
- updated_at
- resolved_at
- assigned_to (FK - Staff User)
- assigned_department

#### Staff User (Cán bộ phường - chỉ cán bộ mới có account)
- user_id (PK)
- username
- email
- phone
- full_name
- department
- role (receiver, handler, leader, admin)
- status
- created_at
- updated_at

#### Response (Phản hồi)
- response_id (PK)
- feedback_id (FK)
- user_id (FK - người trả lời)
- content
- attachments (JSON)
- is_official (boolean - phản hồi chính thức từ HĐND)
- created_at
- updated_at

#### Rating (Đánh giá - không cần user_id)
- rating_id (PK)
- feedback_id (FK)
- tracking_code (để verify)
- score (1-5)
- comment
- created_at

#### Department (Ban/Phòng)
- department_id (PK)
- name
- description
- contact_info
- status

#### Workflow (Quy trình)
- workflow_id (PK)
- feedback_id (FK)
- from_user_id (FK)
- to_user_id (FK)
- action (assigned, transferred, updated, resolved)
- note
- created_at

#### Notification (Thông báo)
- notification_id (PK)
- feedback_id (FK)
- recipient_type (staff, citizen)
- recipient_phone (nếu gửi cho citizen)
- recipient_email (nếu gửi cho citizen)
- user_id (FK - nếu gửi cho staff)
- type (sms, email, in_app)
- content
- is_sent
- sent_at
- created_at

**Loại bỏ:**
- ~~User entity cho người dân~~
- ~~Comment entity~~
- ~~Public forum related tables~~

### 7.2 Data Volume Estimates

**Giả định:**
- Phường có khoảng 20,000 dân
- 5% dân sử dụng hệ thống = 1,000 người
- Mỗi người gửi 2 phản ánh/năm = 2,000 phản ánh/năm
- Mỗi phản ánh có 2-3 phản hồi
- Mỗi phản ánh có 3-5 attachment (ảnh/file) trung bình 2MB

**Dung lượng:**
- Users: 1,000 records × 1KB = 1MB
- Feedbacks: 2,000 records × 5KB = 10MB
- Responses: 5,000 records × 2KB = 10MB
- Comments: 3,000 records × 1KB = 3MB
- Attachments: 10,000 files × 2MB = 20GB
- **Tổng: ~20GB/năm**

---

## 8. Technical Requirements

### 8.1 System Architecture (Đơn giản hóa)

**Kiến trúc đề xuất: Monolithic hoặc Simple Microservices**

```
[Web Browser] ──→ [Web Application]
                       │
                       ├──→ [Public Pages] (không cần auth)
                       │    - Trang gửi phản ánh
                       │    - Trang tra cứu
                       │    - Trang đánh giá
                       │
                       └──→ [Admin Portal] (cần auth)
                            - Dashboard
                            - Quản lý phản ánh
                            - Báo cáo thống kê
                       
                       ↓
              [Backend API]
                       ↓
              [Database + File Storage]
                       ↓
              [Notification Service]
              (SMS/Email Gateway)
```

### 8.2 Technology Stack (Đề xuất đơn giản)

**Frontend:**
- Web: React.js + Next.js (hoặc Vue.js)
- UI Framework: Bootstrap / Tailwind CSS (đơn giản, responsive)
- State Management: React Context API / Zustand

**Backend:**
- Framework: Node.js (Express/NestJS) hoặc PHP (Laravel)
- Language: TypeScript hoặc PHP
- API: RESTful API

**Database:**
- Primary: PostgreSQL hoặc MySQL
- Cache: Redis (optional)
- File Storage: Local storage hoặc MinIO

**Infrastructure:**
- Hosting: VPS đơn giản hoặc Cloud (AWS/Azure/GCP)
- Container: Docker (optional)
- Web Server: Nginx

**Communication:**
- SMS: VIETGUYS / VNPT SMS Gateway / Esms.vn
- Email: SMTP / SendGrid / AWS SES

**Loại bỏ:**
- ~~Elasticsearch (không cần search phức tạp)~~
- ~~Message Queue (hệ thống đơn giản)~~
- ~~Kubernetes (không cần orchestration phức tạp)~~
- ~~AI/ML features~~
- ~~Real-time WebSocket~~

### 8.3 Integration Requirements

**Tích hợp cơ bản:**
- SMS Gateway API
- Email Service API
- Google Maps API (cho chọn vị trí)
- ~~Tích hợp với hệ thống 1022 (nếu cần trong tương lai)~~
- ~~VNeID / CCCD integration (không cần vì không yêu cầu đăng nhập)~~

---

## 9. Success Metrics & KPIs

### 9.1 Adoption Metrics
- Số lượng phản ánh được gửi
- Tỷ lệ phản ánh có cung cấp email/SĐT
- Tỷ lệ người dân tra cứu lại tiến độ
- Số lượt truy cập trang web

**Target:**
- 500 phản ánh trong 6 tháng đầu
- 80% phản ánh có SĐT để liên hệ
- 50% người dân tra cứu lại tiến độ ít nhất 1 lần

### 9.2 Performance Metrics
- Thời gian phản hồi trung bình
- Tỷ lệ giải quyết đúng hạn
- Thời gian xử lý trung bình
- Tỷ lệ phản ánh được giải quyết

**Target:**
- 80% phản ánh được trả lời trong 7 ngày
- 90% phản ánh được giải quyết trong 30 ngày
- Thời gian phản hồi đầu tiên < 48h

### 9.3 Quality Metrics
- Mức độ hài lòng của người dân (rating)
- Tỷ lệ phản ánh bị mở lại
- Số lượng complaint về quy trình
- Net Promoter Score (NPS)

**Target:**
- Average rating ≥ 4.0/5.0
- Tỷ lệ reopened < 10%
- NPS ≥ 50

### 9.4 Technical Metrics
- System uptime
- API response time
- Error rate
- Page load time

**Target:**
- Uptime ≥ 99.5%
- API response < 200ms (p95)
- Error rate < 0.1%
- Page load < 3s

---

## 10. Risks & Mitigation

### 10.1 Technical Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Spam phản ánh (không có authentication) | Medium | Medium | CAPTCHA, rate limiting, moderation tools |
| Tích hợp với hệ thống 1022 gặp khó khăn | Medium | High | Sớm làm việc với team 1022, có plan B không phụ thuộc |
| Performance kém với nhiều user | Low | High | Load testing sớm, thiết kế scalable architecture |
| Security breach | Low | Critical | Security audit, penetration testing, tuân thủ best practices |
| Data loss | Low | Critical | Backup strategy, disaster recovery plan |

### 10.2 Business Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Người dân không biết/không nhớ mã số | Medium | Medium | Gửi SMS/Email nhắc nhở, hướng dẫn rõ ràng |
| Phản ánh thiếu thông tin | Medium | Low | Form có validation, gợi ý nhập đầy đủ |
| Người dân không sử dụng | Medium | High | Chiến dịch truyền thông, training, incentive |
| Cán bộ không thích ứng | Medium | Medium | Training, change management, đơn giản hóa quy trình |
| Quá tải phản ánh | Low | Medium | Tăng nhân lực, tự động hóa, FAQ, chatbot |
| Phản ánh spam, lạm dụng | Medium | Medium | Moderation, xác thực người dùng, AI filtering |

### 10.3 Compliance Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Vi phạm quy định bảo vệ dữ liệu | Low | High | Tuân thủ Nghị định 13, GDPR, data privacy audit |
| Thiếu tính minh bạch | Low | Medium | Công khai quy trình, báo cáo định kỳ |
| Conflict of interest | Low | Medium | Quy trình phê duyệt rõ ràng, audit trail |

---

## 11. Implementation Plan

### 11.1 Phases (Đơn giản hóa)

**Phase 1: MVP Development (Tháng 1-3)**
- Trang gửi phản ánh (không cần đăng nhập)
- Trang tra cứu tiến độ
- Admin portal cơ bản (quản lý phản ánh)
- Tích hợp SMS/Email notification

**Phase 2: Enhancement (Tháng 4-5)**
- Dashboard và báo cáo thống kê
- Phân quyền chi tiết
- Tích hợp bản đồ
- Cải thiện UI/UX

**Phase 3: Pilot (Tháng 6)**
- Deploy và test với người dùng thực
- Thu thập feedback
- Bug fixes

**Phase 4: Production (Tháng 7)**
- Deploy chính thức
- Training cán bộ
- Truyền thông cho người dân

### 11.2 Team Structure

**Sẽ được cập nhật sau khi có đánh giá chi tiết về phạm vi dự án**

### 11.3 Budget Estimate

**Sẽ được cập nhật sau khi xác định được:**
- Quy mô team phát triển
- Thời gian triển khai cụ thể
- Yêu cầu về hạ tầng
- Chi phí dịch vụ (SMS, Email, Hosting)

---

## 12. Assumptions & Constraints

### 12.1 Assumptions
- Phường có kết nối internet ổn định
- Người dân có smartphone hoặc máy tính với trình duyệt web
- Cán bộ phường có kỹ năng công nghệ cơ bản
- Ngân sách được phê duyệt (~$130,000)
- Có ngân sách cho SMS (ước tính 500 tin/tháng)

### 12.2 Constraints
- Không yêu cầu người dân đăng ký/đăng nhập
- Không có diễn đàn công khai
- Phải đơn giản, dễ sử dụng
- Budget limit: Tối ưu chi phí
- Timeline: 7 tháng để hoàn thành

### 12.3 Dependencies
- Phê duyệt từ ban lãnh đạo
- Hợp tác từ các phòng ban
- Hỗ trợ từ team hệ thống 1022
- Cung cấp dữ liệu người dân (danh sách, địa chỉ)
- Quy định pháp lý rõ ràng về xử lý dữ liệu cá nhân

---

## 13. Next Steps

### 13.1 Immediate Actions
1. **Phê duyệt Business Analysis này**
2. **Kick-off Project**
3. **Technical Design**
   - Thiết kế database schema
   - Thiết kế UI/UX mockups
   - API specifications
4. **Procurement**
   - VPS hosting
   - SMS gateway account
   - Email service

### 13.2 Decision Points
- [ ] Approval from leadership
- [ ] Budget confirmation
- [ ] SMS gateway provider selection
- [ ] Hosting provider selection

### 13.3 Open Questions
1. Phường có sẵn tên miền (domain) chưa?
2. SMS budget cụ thể là bao nhiêu tin/tháng?
3. Có yêu cầu on-premise hay cloud-based hosting?
4. Thời hạn xử lý mặc định cho mỗi loại phản ánh?
5. Quy trình phê duyệt phản hồi trước khi gửi cho dân?

---

## 14. Appendix

### 14.1 Glossary
- **Phường:** Ward (administrative division)
- **Chuyển đổi số:** Digital transformation
- **Phản ánh:** Feedback/complaint
- **Kiến nghị:** Suggestion/proposal
- **HĐND:** Hội đồng nhân dân (People's Council)
- **Cổng 1022:** City-wide feedback portal (like 311 in US)

### 14.2 References
- Nghị định 13/2023 về Bảo vệ dữ liệu cá nhân
- Luật An toàn thông tin mạng 2018
- Quy định về dịch vụ công trực tuyến
- Best practices từ hệ thống 1022 hiện tại

### 14.3 Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 29/12/2025 | Business Analyst | Initial version |
| 2.0 | 29/12/2025 | Business Analyst | Updated requirements and scope |

---

## 15. Approval

**Prepared by:**
Name: ________________
Title: Business Analyst
Date: 29/12/2025

**Reviewed by:**
Name: ________________
Title: Project Manager
Date: ________________

**Approved by:**
Name: ________________
Title: Project Sponsor
Date: ________________

---

**Document End**

*This Business Analysis document is confidential and intended for internal use only.*
