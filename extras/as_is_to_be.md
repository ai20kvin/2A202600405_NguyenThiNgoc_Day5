# As-is workflow

| Bước | Hoạt động (As-is) | Kết quả/Vấn đề |
|------|-------------------|----------------|
| **B1: Nhận câu hỏi** | User hỏi "Tiền linh tinh năm nay". | Hệ thống ghi nhận từ khóa "linh tinh". |
| **B2: Tra cứu** | AI quét trong danh mục (Category) có tên là "linh tinh". | Lỗi: Không tìm thấy danh mục này trong hệ thống. |
| **B3: Xử lý số liệu** | AI thấy không có dữ liệu khớp. | Trả về giá trị mặc định là 0. |
| **B4: Phản hồi** | Chatbot trả lời: "Số tiền = 0". | Hậu quả: User thấy sai, mất tin tưởng. |

---

# To-be Workflow – Thêm, Bớt, Đổi

| Bước | Hành động của Hệ thống | Mục tiêu | Cải tiến so với As-is |
|------|------------------------|----------|----------------------|
| **1. Tiếp nhận & Phân tích ý định** | User hỏi "Tiền linh tinh năm nay". AI nhận diện "linh tinh" là một khái niệm mở (không phải category cứng). | Hiểu ý định thực sự của người dùng thay vì chỉ khớp từ khóa. | Đổi: Từ "Khớp từ khóa" sang "Hiểu ngữ nghĩa". |
| **2. Truy vấn & Đề xuất tiêu chí** | AI phản hồi: "Tôi không có mục riêng là 'linh tinh'. Bạn có muốn tôi gom các khoản dưới 100k và các khoản chưa phân loại vào nhóm này không?" | Thiết lập một 'luật chơi' chung giữa AI và User. | Thêm: Cơ chế xác nhận tiêu chí trước khi tính toán. |
| **3. Truy xuất đa tầng (RAG)** | Quét các khoản < 100k + Mục "Khác" + Giao dịch nội dung mơ hồ. | Tìm kiếm dữ liệu tiềm năng dựa trên tiêu chí đã thống nhất. | Thêm: Khả năng quét sâu vào nội dung giao dịch. |
| **4. Ước tính & Minh bạch hóa** | Tính tổng và hiển thị: "Ước tính khoảng 1,5tr. Con số này dựa trên 25 giao dịch nháp." | Tránh kết quả bằng 0 và giải thích nguồn gốc con số. | Đổi: Từ "Con số chết" sang "Con số giải trình". |
| **5. Đối thoại & Hiệu chỉnh** | Cung cấp nút [Xem danh sách] hoặc [Điều chỉnh mức chi tiêu]. User có thể đổi từ <100k thành <50k. | Cho người dùng kiểm soát tối cao đối với dữ liệu của họ. | Thêm: Vòng lặp phản hồi (Feedback loop) để AI học cho lần sau. |
