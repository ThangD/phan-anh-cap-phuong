# Hệ Thống Phản Ánh Cấp Phường - Business Analysis

## 📋 Danh sách tài liệu

### 1. Tài liệu chính thức ⭐ **CHÍNH**
- **BUSINESS_ANALYSIS.md** / **.docx**
  - Phiên bản 2.0 - Đầy đủ nhất (823 dòng)
  - Tích hợp AI Auto-Classification (FR-006)
  - Đầy đủ: FR, NFR, User Stories, Data Schema, Technical Stack
  - Quy trình không yêu cầu người dân đăng nhập
  - **Dùng cho**: Tất cả stakeholders, team development, BA team

### 2. Tài liệu cho Phường
- **BUSINESS_ANALYSIS_FOR_WARD.md** / **.docx**
  - Không có phần technical chi tiết
  - Tập trung vào nghiệp vụ, quy trình
  - Đã cập nhật với AI Auto-Classification
  - **Dùng cho**: Lãnh đạo và cán bộ Phường

### 3. Đề xuất ngắn gọn
- **DE_XUAT_CHO_PHUONG.md** / **.docx**
  - Tài liệu ngắn gọn, dễ hiểu
  - Không có AI (phiên bản đơn giản)
  - **Dùng cho**: Trình bày ban đầu

---

## 🚀 Tính năng chính

### Điểm đặc biệt:
- 🔓 **Không cần đăng nhập**: Người dân gửi phản ánh trực tiếp, nhận mã số tra cứu
- 🤖 **AI Auto-Classification**: Tự động phân loại phản ánh trong 0-2 giờ
- 📱 **SMS/Email Notification**: Thông báo tự động cho người dân
- 📊 **Dashboard cho cán bộ**: Quản lý và thống kê hiệu quả

### AI Auto-Classification (FR-006):
- ⚡ Phân tích nội dung tự động: Tiêu đề, mô tả, hình ảnh, vị trí
- 🎯 Gợi ý: Phân loại, mức độ ưu tiên, phòng ban phụ trách
- 📈 Confidence Score: Hiển thị độ tin cậy (0-100%)
- 🔄 Machine Learning: AI học từ feedback của cán bộ
- ⏱️ Tiết kiệm 70% thời gian phân loại

### Quy trình:

```
Người dân gửi (không đăng nhập)
    ↓
AI tự động phân loại (0-2h)
    ↓
Cán bộ xác nhận (2-24h)
    ↓
Lãnh đạo phân công
    ↓
Xử lý và phản hồi
    ↓
Người dân đánh giá
```

---

## 📊 Timeline

- **Phase 1**: MVP với AI (Tháng 1-3)
- **Phase 2**: Enhancement (Tháng 4-5)
- **Phase 3**: Pilot (Tháng 6)
- **Phase 4**: Production (Tháng 7)

**Total**: 7 tháng

---

## 💰 Budget Estimate

Chi phí sẽ được cập nhật sau khi xác định:
- Quy mô team phát triển
- Yêu cầu về hạ tầng
- Chi phí dịch vụ (SMS, Email, Hosting)
- Chi phí AI/ML development

---

## 📝 Ghi chú

- File `.docx` và `.pdf` được tạo tự động từ `.md` bằng Pandoc
- File `.docx` và `.pdf` được ignore trong Git (xem `.gitignore`)
- **Tạo file Word**: `pandoc filename.md -o filename.docx`
- **Tạo file PDF**: `pandoc filename.md -o filename.pdf`
- **Tạo tất cả**: `./generate-docs.sh` (script tự động)

---

## 📧 Liên hệ

Nếu có thắc mắc về tài liệu, vui lòng liên hệ:
- Business Analyst: [email]
- Project Manager: [email]

---

**Last Updated**: 30/12/2025
**Version**: 2.0

