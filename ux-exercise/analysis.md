# Phân Tích 4 Paths - UX Exercise Day 5
**MSSV:** 2A20260405  
**Họ Tên:** Nguyễn Thế Ngọc  
**Môn:** AI Hành động - Lập kế hoạch AI theo logic sai phương  

---

## 1. Path 1 - **ĐÚNG** (Happy Path)
> AI hiểu được ý tính và cũng hiểu chuẩn xác

### User Request:
*"Moni ơi, chở tôi biết khoán chi lên nhất trong tháng qua"*

### Hành Trình Của AI:
- **Kỹ năng đọng:** Khoán nhân thêm gian
- **So sánh:** Tính xết quả và họp dịnh giá các giadosk

### Kết Quả User Thấy:
✅ Báo cao chi thế khoán chi phí lên nhất (số tiền, ngày được, đặc tác)  
✅ Danh sách các khoản chi khác sắp xếp theo thứ tự giảm dần

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI sẽ hiểu chính xác ý tính và trả về kết quả chuẩn xác
- **Thực tế diễn ra:** AI hoạt động đúng như hứa ✅

---

## 2. Path 2 - **KHÔNG CHẶC** (Failure Path - Wrong Logic)
> Chỉ liều mã hộ hoặc hiểu lệnh sai

### User Request:
*"Báo cao tổng chi tiêu trong nước cho những việc linh tính"*

### Hành Trình Của AI:
- **AI hành động:** Báo cao số tiền = 0; không biết chế khác (key word matching)
- **Vấn đề:** Tìm dành mục "linh tính" → không có khoá khóa → Trả về "số tiền = 0"

### Kết Quả User Thấy:
❌ Tổng số tiền = 0 (sai!)

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI sẽ "thông minh" hiểu ý tính
- **Thực tế diễn ra:** AI chỉ dùng keyword matching → Mất tin tưởng người dùng
- **Nguyên nhân:** Thiếu logic xử lý ngữ nghĩa (NLP) hoặc không có xử lý ngoại lệ

---

## 3. Path 3 - **SAI** (Failure Path - Wrong Interpretation)
> AI nhất đóng người từm vị nhân học logic sai ngữ anh

### User Request:
*"Tìm quản ở ngân..."* (yêu cầu tìm quản y tế)

### Hành Trình Của AI:
- **Hiểu sai:** Nhầm liều ý tính chính là "tìm địch với người"
- **Xử lý:** Tìm xuất tủ lãm dos tác HoMo tdo (với chỉnh số quản)
- **Kết quả:** AI nhận việc không có trong hệ thống

### Kết Quả User Thấy:
❌ Danh sách quản gần (tay trong) - không phải kết quả cần tìm

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI có thể tìm kiếm thông minh
- **Thực tế diễn ra:** AI hiểu nhầm ý tính → Trả về kết quả sai
- **Nguyên nhân:** Thiếu context hiểu hoặc logic disambiguate (phân biệt)

---

## 4. Path 4 - **NẮT TIN (Crisis)** (Critical Failure - Trust Lost)
> Sự kiểu sơ để tại chính

### User Request:
*"Tại sao báo cao Moni (10k) liên sao và sao là Ngân hàng 05?"*

### Hành Trình Của AI:
- **Vấn đề:** AI ai khi tone ấm tính → không giải thích được lý do
- **Cần:** T-Explainable AI (giải thích được)

### Kết Quả User Thấy:
❌ AI không thể giải thích được **TẠI SAO** (lack of explainability)

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI sẽ giải thích được từng quyết định
- **Thực tế diễn ra:** AI chỉ cho kết quả, không giải thích
  - "Bảo sơ mục tôi nước kèm chi tế: Dùng tiền qua Ngân hàng vs Dùng tiền qua Memo"
- **Nguyên nhân chính:** Thiếu tính **Explainability → Mất tin tưởng người dùng**

---

## Tóm Tắt Gap Marketing vs Thực Tế

| Path | Trạng Thái | Gap Chính | Ảnh Hưởng |
|------|-----------|----------|-----------|
| **1** | ✅ Đúng | Không | Người dùng hài lòng |
| **2** | ❌ Sai | Thiếu NLP/Logic ngữ nghĩa | Người dùng thất vọng |
| **3** | ❌ Sai | Thiếu Context/Disambiguate | Kết quả sai lệch |
| **4** | ❌ Critical | Thiếu Explainability | **Mất tin tưởng toàn bộ** |

---

## Kết Luận
1. **Path 1** là thành công vì AI hiểu chính xác ý tính
2. **Path 2-3** thất bại vì logic không đủ mạnh
3. **Path 4** là khủng hoảng vì thiếu khả năng giải thích → Mất niềm tin người dùng

**Cần cải thiện:**
- ✅ Tăng cường NLP & semantic understanding
- ✅ Thêm logic xử lý ngoại lệ & synonyms
- ✅ Implement Explainable AI (XAI) để xây dựng lại niềm tin
