# Phân Tích 4 Paths - UX Exercise Day 5
**MSSV:** 2A202600405  
**Họ Tên:** Nguyễn Thị Ngọc  
**Môn:** UX  

---

## 1. Path 1 - **ĐÚNG** (Happy Path)
> AI hiểu được ý định (intent) và truy xuất dữ liệu chính xác

### User Request:
*"Moni ơi, cho tôi biết khoản chi lớn nhất trong tháng qua"*

### Hành động Của AI:
- **Kỹ năng đọng:** Xác định đúng khoản thời gian
- **So sánh:** Truy xuất và so sánh giá trị các giao dịch

### Kết Quả User Thấy:
✅ Báo cao cụ thể khoán chi phí lớn nhất (số tiền, ngày , đối tác)  
✅ Danh sách các khoản chi khác sắp xếp theo thứ tự số tiền giảm dần


### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI sẽ hiểu chính xác ý định và trả về kết quả chuẩn xác
- **Thực tế diễn ra:** AI hoạt động đúng như hứa ✅

### Giá trị: 
✅ Xây dựng sự tin tưởng (Reliability) vào khả năng tính toán của hệ thống - nền tảng UX trong fintech.
---

## 2. Path 2 - **KHÔNG CHẮC CHẮN** (Failure Path - sai từ ngữ địa phương hoặc danh mục chưa chuẩn hoá)

### User Request:
*"Báo cao tổng chi tiêu trong năm cho những việc linh tinh"*

### Hành Động Của AI:
- **AI hành động:** AI chỉ tìm từ khoá khớp với từ "linh tinh"  không khớp từ khoá -> trả về số tiền mặc định = 0 

### Kết Quả User Thấy:
❌ Tổng số tiền = 0 (sai!)

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI sẽ "thông minh" hiểu ý định
- **Thực tế diễn ra:** AI chỉ dùng keyword matching → User thấy AI kém thông minh
- **Nguyên nhân:** Thiếu Semantic Search (Tìm kiếm ngữ nghĩa) để hiểu "linh tinh" có thể là các khoản "Khác" hoặc "Không tên"

### Cải thiện: 
- *AI nên thông báo và hỏi lại: "Bạn không có danh mục 'linh tinh'. Bạn có muốn tôi báo cáo các khoản chi tiêu trong danh mục 'Khác' hoặc 'Misc' không?"*

---

## 3. Path 3 - **SAI** (Failure Path - Out of Scope)
>AI hoạt động ngoài phạm vi, nhầm lẫn logic hoặc sai ngữ cảnh

### User Request:
*"Tìm quán ăn ngon gần đây"* 

### Hành Động Của AI (HIỆN TẠI - CÓ VẤN ĐỀ):
- **Hiểu sai:** AI nhận diện yêu cầu hợp lệ thay vì một yêu cầu ngoài phạm vi tài chính
- **Xử lý:** AI truy xuất dữ liệu từ danh mục đối tác quảng cáo thay vì dữ liệu ngân sách cá nhân

### Kết Quả User Thấy:
- Danh sách quán ăn gầy đây

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** Trợ lý tài chính thông minh, tập trung quản lí và tối ưu hoá chi phí
- **Thực tế diễn ra:** AI  nhầm vai trò -> hành xử như Search Engine -> làm loãng giá trị cốt lõi của sản phẩm 
- **Nguyên nhân:** Thiếu guardrails để xử lí cho những yêu cầu ngoài phạm vi

### Cải thiện:
- Đưa AI trở lại đúng vai trò mà Marketing đã hứa bằng kỹ thuật Điều hướng theo ngữ cảnh. Phản hồi : Bạn dự định chi khoảng bao nhiêu cho bữa ăn này để mình cân đối với hạn mức chi tiêu tuần của bạn?

---

## 4. Path 4 - **NẮT TIN (Crisis)** (Critical Failure - Trust Lost)
> Sai lệch số liệu tài chính không rõ nguyên nhân

### User Request:
*"Tại sao báo cáo Moni là 10 triệu, lệch so với sao kê Ngân hàng chỉ có 5 triệu?"*

### Hành Động Của AI:
-  Tone & Mood: AI chọn tone điềm tình để xoa dịu
- Xử lý thiếu minh bạch: Chỉ giải thích nguyên nhân dựa trên các giả định chung chung thay vì truy xuât các giao dịch cụ thể để đối chứng

### Kết Quả User Thấy:
- User cảm nhận sự đồng cảm và Hiểu lí do số tiền bị lệch ở mức chung chung
- Vẫn mơ hồ về con số

### Gap vs Marketing vs Thực Tế:
- **Marketing hứa:** AI minh bạch, giúp kiểm soát tài chính chính xác đến từng đồng
- **Thực tế diễn ra:** AI chỉ cho kết quả, giải thích nguyên nhân chung chung -> tạo ra một chiếc hộp đen về số liệu → Mất tin tưởng người dùng**

- **Nguyên nhân chính:** Thiếu tính Explainability 
### Giải Pháp Cần Thiết:
✅ **Thêm nút "Xem Chi Tiết"** → Hiển thị danh sách tất cả giao dịch  
✅ **Thêm "Giải Thích"** → Show: "Tổng = GD1 + GD2 + GD3... = 10 triệu"  
✅ **Thêm "So Sánh Ngân Hàng"** → Highlight khoản Pending/Chưa cập nhật  
✅ → **Lấy lại TRUST từ người dùng**
---

## Tóm Tắt Gap Marketing vs Thực Tế

| Path | Trạng Thái | Gap Chính | Nguyên Nhân | Ảnh Hưởng |
|------|-----------|----------|------------|-----------|
| **1** | ✅ Đúng | Không | - | Người dùng hài lòng |
| **2** | ❌ Sai | Thiếu xử lý ngữ nghĩa | Keyword matching đơn giản | Người dùng thất vọng |
| **3** | ❌ Sai | Out-of-scope handling | Thiếu guardrails cho yêu cầu ngoài phạm vi | Kết quả sai lệch |
| **4** | ❌ Critical | Thiếu Explainability | Black box AI | **Mất niềm tin** |

---

## Kết Luận
1. **Path 1** là thành công vì AI hiểu chính xác ý định và xử lý đúng scope tài chính
2. **Path 2** thất bại vì thiếu semantic understanding cho từ ngữ địa phương
3. **Path 3** thất bại vì thiếu guardrails xử lý yêu cầu out-of-scope
4. **Path 4** là khủng hoảng vì thiếu explainability → Mất niềm tin người dùng

**Cần cải thiện theo ưu tiên:**
- 🔴 **URGENT (Path 4):** Implement Explainable AI để lấy lại trust
- 🟡 **HIGH (Path 2-3):** Tăng cường NLP & thêm guardrails cho scope management
- 🟢 **MAINTAIN (Path 1):** Giữ vững happy path experience
