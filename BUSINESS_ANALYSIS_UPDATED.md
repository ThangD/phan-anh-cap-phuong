# Business Analysis - Hệ Thống Phản Ánh Cấp Phường
## Phiên bản 2.1 - Có tích hợp AI Auto-Classification

**Ngày cập nhật:** 30/12/2025  
**Dự án:** Hệ thống phản ánh kiến nghị cấp phường với AI

---

## 1. Tổng quan

### 1.1 Mục tiêu chính
Xây dựng hệ thống web đơn giản cho phép:
- **Người dân**: Gửi phản ánh KHÔNG CẦN ĐĂNG NHẬP, tra cứu tiến độ qua mã số
- **Cán bộ phường**: Quản lý phản ánh với hỗ trợ AI tự động phân loại
- **AI tự động**: Phân tích và phân loại phản ánh ngay khi được gửi

### 1.2 Điểm mới quan trọng: AI Auto-Classification
Thay vì cán bộ phải đọc và phân loại thủ công từng phản ánh, hệ thống sẽ:
- ✅ AI tự động phân tích nội dung ngay khi người dân gửi
- ✅ Gợi ý phân loại, mức độ ưu tiên, phòng ban phụ trách
- ✅ Cán bộ chỉ cần XÁC NHẬN hoặc ĐIỀU CHỈNH (nếu AI sai)
- ✅ AI học từ các điều chỉnh để ngày càng chính xác hơn

---

## 2. Quy trình mới với AI

### Quy trình cũ (Thủ công):
```
Người dân gửi → Cán bộ đọc → Cán bộ phân loại → Phân công xử lý
              (tốn thời gian)  (có thể sai sót)
```

### Quy trình mới (Có AI):
```
Người dân gửi → AI TỰ ĐỘNG PHÂN LOẠI → Cán bộ xác nhận → Phân công xử lý
                (< 2 giờ, 24/7)        (nhanh chóng)
                      ↓
            - Phân loại: Hạ tầng/Môi trường/An ninh...
            - Mức độ: Thấp/Trung bình/Cao/Khẩn cấp
            - Gợi ý phòng ban xử lý
            - Confidence: 85% (độ tin cậy)
```

---

## 3. Chi tiết tính năng AI

### 3.1 AI phân tích gì?
1. **Nội dung văn bản**:
   - Tiêu đề phản ánh
   - Mô tả chi tiết
   - Từ khóa quan trọng (ví dụ: "đường hư hỏng" → Hạ tầng)

2. **Hình ảnh đính kèm** (optional):
   - Phát hiện loại vấn đề qua ảnh
   - Ví dụ: Ảnh rác thải → Môi trường

3. **Vị trí địa lý**:
   - Xác định khu vực
   - Gợi ý phòng ban quản lý khu vực đó

4. **Ngữ cảnh**:
   - Phát hiện mức độ khẩn cấp từ từ ngữ (ví dụ: "nguy hiểm", "khẩn cấp")
   - Phát hiện cảm xúc người gửi

### 3.2 Kết quả AI cung cấp

Ví dụ kết quả AI cho một phản ánh:

```
📋 PHẢN ÁNH MỚI: #PA-2025-001
Tiêu đề: "Đường Lê Lợi bị hư hỏng nhiều ổ gà"

🤖 KẾT QUẢ AI:
✓ Phân loại: HẠ TẦNG - Giao thông đường bộ
✓ Mức độ: TRUNG BÌNH (có thể nâng lên CAO nếu trời mưa)
✓ Gợi ý phòng ban: Phòng Quản lý đô thị
✓ Độ tin cậy: 92%
✓ Thời hạn đề xuất: 15 ngày

👤 CÁN BỘ CẦN:
☐ Xác nhận (nếu đúng)
☐ Điều chỉnh (nếu AI sai)
```

### 3.3 Lợi ích của AI

| Trước khi có AI | Sau khi có AI |
|-----------------|---------------|
| Cán bộ đọc mỗi phản ánh: 5-10 phút | AI phân tích: < 5 giây |
| Phân loại có thể không nhất quán | AI phân loại đồng nhất |
| Chỉ làm việc giờ hành chính | AI hoạt động 24/7 |
| Có thể bỏ sót phản ánh khẩn cấp | AI phát hiện và ưu tiên tự động |
| Khó thống kê xu hướng | AI phân tích xu hướng tự động |

---

## 4. Giao diện cho Cán bộ

### 4.1 Dashboard với AI

```
┌─────────────────────────────────────────────────────────┐
│  🤖 PHẢN ÁNH MỚI CẦN XÁC NHẬN                           │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  📋 #PA-2025-001 - "Đường Lê Lợi hư hỏng"              │
│  🤖 AI: Hạ tầng - Giao thông (92% tin cậy)             │
│  📍 Khu vực: Phường 1, Khu phố 3                        │
│  ⚠️  Mức độ: TRUNG BÌNH                                 │
│  🏢 Gợi ý: Phòng Quản lý đô thị                         │
│                                                          │
│  [✓ Xác nhận]  [✏️ Điều chỉnh]  [👁️ Xem chi tiết]      │
│                                                          │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  📋 #PA-2025-002 - "Rác thải tràn ra đường"            │
│  🤖 AI: Môi trường - Vệ sinh (95% tin cậy)             │
│  📍 Khu vực: Phường 1, Khu phố 5                        │
│  ⚠️  Mức độ: CAO                                        │
│  🏢 Gợi ý: Phòng Tài nguyên & Môi trường               │
│                                                          │
│  [✓ Xác nhận]  [✏️ Điều chỉnh]  [👁️ Xem chi tiết]      │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

### 4.2 Khi điều chỉnh AI

Nếu cán bộ thấy AI phân loại sai, có thể điều chỉnh:

```
┌─────────────────────────────────────────────────────────┐
│  ĐIỀU CHỈNH PHÂN LOẠI AI                                │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  📋 Phản ánh: #PA-2025-001                              │
│                                                          │
│  🤖 AI gợi ý:         Hạ tầng - Giao thông              │
│  ❌ Không đúng vì:    [Chọn lý do]                      │
│                                                          │
│  ✏️ Phân loại đúng:   [Dropdown: Chọn phân loại]        │
│                       ▼ Hạ tầng - Chiếu sáng công cộng  │
│                                                          │
│  📝 Ghi chú:          Phản ánh về đèn đường bị hỏng,    │
│                       không phải về đường bộ            │
│                                                          │
│  [💾 Lưu và học AI]  [❌ Hủy]                          │
│                                                          │
│  💡 Tip: AI sẽ học từ điều chỉnh này để cải thiện!     │
└─────────────────────────────────────────────────────────┘
```

---

## 5. Công nghệ AI sử dụng

### 5.1 NLP (Natural Language Processing)
- **Mô hình**: PhoBERT hoặc viBERT (Vietnamese BERT)
- **Chức năng**: 
  - Hiểu ngữ nghĩa tiếng Việt
  - Phân loại văn bản
  - Trích xuất từ khóa quan trọng
  - Phát hiện cảm xúc

### 5.2 Machine Learning
- **Framework**: scikit-learn hoặc TensorFlow Lite
- **Chức năng**:
  - Phân loại nhiều nhãn (multi-label classification)
  - Dự đoán mức độ ưu tiên
  - Gợi ý phòng ban

### 5.3 Computer Vision (Tùy chọn)
- **Framework**: OpenCV hoặc TensorFlow
- **Chức năng**:
  - Nhận diện đối tượng trong ảnh
  - Phát hiện loại vấn đề từ hình ảnh

### 5.4 Feedback Loop (Học từ điều chỉnh)
```
Phản ánh mới → AI dự đoán → Cán bộ điều chỉnh → AI học
                                    ↓
                          Lưu vào training data
                                    ↓
                          Re-train model định kỳ
                                    ↓
                          AI ngày càng chính xác
```

---

## 6. Yêu cầu kỹ thuật mới

### 6.1 Backend bổ sung
- **AI Service**: Microservice riêng cho AI classification
- **ML Pipeline**: Để train và update model
- **Training Data Storage**: Lưu dữ liệu để train lại model

### 6.2 Database bổ sung
```sql
-- Bảng lưu kết quả AI
CREATE TABLE ai_classification (
    id INT PRIMARY KEY,
    feedback_id INT,
    category_prediction VARCHAR(100),
    priority_prediction VARCHAR(50),
    department_suggestion VARCHAR(100),
    confidence_score DECIMAL(5,2),
    created_at TIMESTAMP
);

-- Bảng lưu feedback từ cán bộ
CREATE TABLE ai_feedback (
    id INT PRIMARY KEY,
    feedback_id INT,
    ai_classification_id INT,
    is_correct BOOLEAN,
    corrected_category VARCHAR(100),
    corrected_priority VARCHAR(50),
    corrected_department VARCHAR(100),
    staff_note TEXT,
    created_at TIMESTAMP
);
```

### 6.3 API Endpoints mới

```
POST /api/ai/classify
- Input: feedback content, images, location
- Output: classification results with confidence

POST /api/ai/feedback
- Input: correction from staff
- Output: saved and queued for retraining

GET /api/ai/stats
- Output: AI accuracy statistics
```

---

## 7. Kế hoạch triển khai AI

### Phase 1: Setup & Training (Tháng 1-2)
- Thu thập dữ liệu mẫu (200-500 phản ánh thực tế)
- Gắn nhãn thủ công bởi cán bộ có kinh nghiệm
- Train model ban đầu
- Test độ chính xác (target: >70%)

### Phase 2: Pilot với AI (Tháng 3)
- Deploy AI lên production
- Cán bộ test và cung cấp feedback
- Thu thập thêm dữ liệu thực tế
- Re-train model với dữ liệu mới

### Phase 3: Optimization (Tháng 4-5)
- Cải thiện model dựa trên feedback
- Thêm tính năng phân tích hình ảnh
- Target độ chính xác: >85%

### Phase 4: Full Production (Tháng 6+)
- AI hoạt động chính thức
- Monitoring liên tục
- Re-train định kỳ (mỗi tháng)

---

## 8. Metrics đánh giá AI

### 8.1 Độ chính xác
- **Accuracy**: Tỷ lệ dự đoán đúng tổng thể
- **Target**: >85% sau 3 tháng

### 8.2 Precision & Recall
- **Precision**: Khi AI dự đoán là X, bao nhiêu % thực sự là X
- **Recall**: Trong tất cả trường hợp X, AI phát hiện được bao nhiêu %
- **Target**: >80% cho cả hai

### 8.3 Confidence Distribution
- Bao nhiêu % dự đoán có confidence >80%
- Bao nhiêu % dự đoán cần cán bộ xem xét kỹ
- **Target**: >70% dự đoán có confidence >80%

### 8.4 Time Savings
- Thời gian trung bình cán bộ xử lý mỗi phản ánh
- **Before AI**: 5-10 phút
- **With AI**: 1-2 phút (chỉ cần xác nhận)
- **Target**: Tiết kiệm >70% thời gian

---

## 9. Chi phí bổ sung cho AI

### 9.1 Development
- AI/ML Engineer: $5,000-8,000/tháng × 3 tháng = $15,000-24,000
- Data labeling (gắn nhãn dữ liệu): $2,000-3,000
- **Subtotal**: $17,000-27,000

### 9.2 Infrastructure
- GPU instance cho training: $200-500/tháng
- ML model hosting: $100-200/tháng
- **Annual**: $3,600-8,400

### 9.3 Maintenance
- Model monitoring: $50-100/tháng
- Re-training monthly: $200-300/tháng
- **Annual**: $3,000-4,800

### 9.4 Tổng chi phí AI
- **Initial**: $17,000-27,000
- **Annual**: $6,600-13,200
- **Total Year 1**: $23,600-40,200

---

## 10. Rủi ro và Giải pháp

### 10.1 AI không chính xác ban đầu
- **Risk**: Model mới có thể sai nhiều
- **Mitigation**: 
  - Luôn có cán bộ xác nhận
  - Cho phép dễ dàng điều chỉnh
  - Cải thiện dần qua feedback

### 10.2 Dữ liệu training không đủ
- **Risk**: Cần 200-500 mẫu có gắn nhãn
- **Mitigation**:
  - Thu thập từ hệ thống 1022
  - Thuê service gắn nhãn chuyên nghiệp
  - Cán bộ gắn nhãn trong 1-2 tuần

### 10.3 Bias trong AI
- **Risk**: AI có thể thiên vị một số loại phản ánh
- **Mitigation**:
  - Monitor distribution of predictions
  - Cân bằng training data
  - Regular audits

---

## 11. So sánh với/không có AI

| Tiêu chí | Không có AI | Có AI |
|----------|-------------|-------|
| **Thời gian xử lý phản ánh mới** | 1-2 ngày | 0-2 giờ |
| **Thời gian cán bộ/phản ánh** | 5-10 phút | 1-2 phút |
| **Độ nhất quán** | Tùy cán bộ | Luôn đồng nhất |
| **Khả năng mở rộng** | Cần thêm nhân lực | Tự động scale |
| **Chi phí ban đầu** | Thấp hơn | Cao hơn ~$25K |
| **Chi phí dài hạn** | Cao (nhân lực) | Thấp hơn |
| **Thời gian phát triển** | 3-4 tháng | 5-6 tháng |

---

## 12. Kết luận

### 12.1 Khuyến nghị
**NÊN** triển khai AI Auto-Classification vì:
- ✅ Tiết kiệm 70% thời gian xử lý
- ✅ Cải thiện trải nghiệm người dân (phản hồi nhanh hơn)
- ✅ Giảm áp lực cho cán bộ
- ✅ Dễ dàng mở rộng khi số lượng phản ánh tăng
- ✅ Cung cấp insights tự động về xu hướng vấn đề

### 12.2 Timeline điều chỉnh
- **Với AI**: 5-6 tháng development + 1 tháng pilot = 6-7 tháng
- **Không AI**: 3-4 tháng development

### 12.3 ROI (Return on Investment)
Giả sử:
- Cán bộ lương: $500/tháng
- Tiết kiệm 50% thời gian 2 cán bộ = $500/tháng
- Chi phí AI: ~$1,100/tháng (sau năm đầu)

**Break-even**: ~2 năm
**Benefit lâu dài**: Tăng khi số lượng phản ánh tăng

---

## Phụ lục: Ví dụ Training Data

```json
{
  "feedback_examples": [
    {
      "text": "Đường Lê Lợi đoạn gần chợ bị nhiều ổ gà, xe đi rất nguy hiểm",
      "category": "infrastructure_roads",
      "priority": "high",
      "department": "urban_management",
      "keywords": ["đường", "ổ gà", "nguy hiểm"]
    },
    {
      "text": "Rác thải chưa được thu gom 3 ngày, bốc mùi hôi thối",
      "category": "environment_waste",
      "priority": "high", 
      "department": "environment",
      "keywords": ["rác", "không thu gom", "hôi thối"]
    },
    {
      "text": "Đèn đường trước số nhà 123 bị hỏng đã 2 tuần",
      "category": "infrastructure_lighting",
      "priority": "medium",
      "department": "urban_management",
      "keywords": ["đèn đường", "hỏng"]
    }
  ]
}
```

---

**Document End**

*Business Analysis Document với tích hợp AI Auto-Classification*
*Version 2.1 - Updated 30/12/2025*

