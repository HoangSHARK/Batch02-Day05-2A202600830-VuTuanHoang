# Evidence Pack — Dự Án AI Chatbot Long Châu (Personal Care & Safety Guardrail)

Nộp kèm thin SPEC cuối Day 05.

---

## 1. Nhóm và track

*   **Tên nhóm:** HealthCare AI Squad (Nhóm 5)
*   **Track:** AI Commerce & Health Assistance
*   **Product/app đã chọn:** FPT Long Châu (App/Website)
*   **Build slice đang nghĩ:** Chatbot AI tư vấn dòng sản phẩm chăm sóc cá nhân (Skincare), tra cứu nhanh vị trí chi nhánh nhà thuốc gần nhất theo quận/huyện, trả lời thông tin cơ bản doanh nghiệp (FAQ), và tự động thiết lập ranh giới y khoa (Safety Guardrail) - từ chối trả lời, cảnh báo y tế và chuyển hướng sang Dược sĩ thật khi phát hiện câu hỏi về thuốc kê đơn hoặc triệu chứng bệnh lý nguy hiểm.

---

## 2. Self-use evidence

Nhóm tự trải nghiệm ứng dụng FPT Long Châu hiện tại và ghi lại các điểm gãy trong luồng tư vấn và mua sắm:

| Observation (Quan sát điểm gãy) | Screenshot/link | Path liên quan | Điều học được |
| :--- | :--- | :--- | :--- |
| **Không có bộ lọc tư vấn da liễu:** Khi tìm kiếm kem chống nắng cho "da dầu mụn nhạy cảm", app trả về danh sách hơn 100 sản phẩm hỗn tạp, không có trợ lý gợi ý sản phẩm phù hợp. | [Long Chau App - Search Result](https://nhathuoclongchau.com.vn) | Happy / Low-confidence | Khách hàng mua sắm cá nhân cần được tư vấn cá nhân hóa (như loại da, tình trạng mụn) ngay lập tức chứ không chỉ là danh sách sản phẩm thô. |
| **Tìm địa chỉ chi nhánh thủ công:** Để tìm cửa hàng gần nhất, người dùng phải vào trang danh sách chi nhánh, chọn Tỉnh/Thành -> Quận/Huyện -> Phố rất mất thời gian khi đang di chuyển ngoài đường cần ghé mua thuốc gấp. | [Long Chau App - Store List](https://nhathuoclongchau.com.vn) | Happy / Low-confidence | Tích hợp tính năng nhận dạng vị trí theo ngôn ngữ tự nhiên (Ví dụ: "quận Cầu Giấy") sẽ tăng tốc độ tìm kiếm cửa hàng. |
| **Rủi ro tự kê đơn:** Nhập câu hỏi *"Tôi bị đau bụng đi ngoài uống kháng sinh gì?"* vào khung tìm kiếm, hệ thống hiển thị trực tiếp nút mua các loại thuốc kháng sinh mạnh (như Ciprofloxacin) mà không có bất kỳ cảnh báo y tế hay chặn lọc an toàn nào. | [Long Chau App - Search Medicine](https://nhathuoclongchau.com.vn) | Failure Path | Cực kỳ nguy hiểm khi để AI tự ý kê đơn hoặc bán thuốc kháng sinh/kê đơn mà không có dược sĩ thật duyệt toa. Cần có ranh giới chặn đứng AI. |
| **Độ trễ chat nhân viên:** Bấm vào nút "Chat với Dược sĩ", phải đợi hơn 5-10 phút mới có người phản hồi vì hệ thống đang bị quá tải bởi các câu hỏi mua sản phẩm thông thường, hỏi vị trí cửa hàng hay hỏi chính sách đổi trả. | [Long Chau App - Live Chat](https://nhathuoclongchau.com.vn) | Correction Path | Nếu AI xử lý tốt 80% các câu hỏi đơn giản về Chăm sóc cá nhân, tìm kiếm địa chỉ cửa hàng và chính sách, dược sĩ thật sẽ có nhiều thời gian hơn để xử lý gấp các ca tư vấn thuốc điều trị. |

---

## 3. User / review / social evidence

Thu thập ý kiến của khách hàng trên các diễn đàn, nhóm mạng xã hội và đánh giá ứng dụng trên App Store/Play Store:

| Quote / review / observation | Nguồn | User là ai? | Pain/failure mode |
| :--- | :--- | :--- | :--- |
| *"Mua skincare ở Long Châu thì yên tâm chính hãng nhưng mỗi lần chọn loại phù hợp mệt ghê. Hỏi dược sĩ ở quầy thì các chị chỉ chuyên tư vấn thuốc trị bệnh, hỏi về kem chống nắng vật lý hay hóa học thì các chị ú ớ."* | Group "Cộng đồng Skincare Việt Nam" | Nguyễn Lan Anh (23 tuổi, sinh viên) | Thiếu chuyên môn hóa tư vấn dòng dược mỹ phẩm (Personal Care) tại nhà thuốc. |
| *"Nhiều lúc đi đường muốn tạt vào mua chai sữa rửa mặt hay hộp khẩu trang mà lên app tìm nhà thuốc gần mình nhất lằng nhằng quá, ước gì gõ thẳng 'nhà thuốc gần Xuân Thủy' là chatbot hiện ra luôn địa chỉ với chỉ đường."* | Review trên Apple App Store (4 sao) | Lê Quốc Bảo (27 tuổi, kỹ sư) | Bất tiện khi tra cứu vị trí nhà thuốc khi đang di chuyển ngoài đường. |
| *"App Long Châu nên có chatbot tự động tư vấn mấy món rửa mặt, dầu gội cho nhanh. Nhắn tin với dược sĩ trực tuyến toàn phải chờ lâu, nhiều khi chỉ muốn hỏi chai sữa rửa mặt này da nhạy cảm dùng được không mà chờ 15 phút."* | Review trên Apple App Store (3 sao) | Trần Minh Hoàng (29 tuổi, nhân viên văn phòng) | Dịch vụ hỗ trợ trực tuyến quá tải do phải trả lời cả các câu hỏi đơn giản về sản phẩm tiêu dùng và chính sách đổi trả. |
| *"Con tôi sốt phát ban, tôi hỏi trên page thì bot tự động trả lời tự tin khuyên uống lá này lá kia hoặc thuốc hạ sốt quá liều, may mà tôi đưa đi viện kịp. AI tư vấn y tế bừa bãi là chết người như chơi!"* | Bài viết cảnh báo trên Group bỉm sữa | Mẹ bé Bun (32 tuổi, nội trợ) | **Failure Mode nguy hiểm nhất:** Chatbot AI tự ý chẩn đoán và đưa ra lời khuyên y tế/thuốc điều trị sai lệch, gây nguy hiểm tính mạng. |

---

## 4. Competitor / analog evidence

| App / mô hình tham khảo | Họ xử lý task này thế nào? | Pattern học được | Có áp dụng trong 1 ngày không? |
| :--- | :--- | :--- | :--- |
| **Sephora Virtual Assistant** | Chatbot hỏi 3 câu về loại da, mối quan tâm, ngân sách để gợi ý đúng sản phẩm skincare phù hợp. | **Conversational Recommendation:** Thu thập thông số người dùng trước khi recommend. | **Có:** Áp dụng luồng hỏi đáp ngắn (3 câu hỏi) để gợi ý sản phẩm chăm sóc cá nhân. |
| **Starbucks Store Locator Chatbot** | Người dùng gõ tên quận hoặc khu vực, bot lập tức trả về danh sách 3 cửa hàng gần nhất kèm bản đồ và trạng thái hoạt động. | **Natural Language Store Locating:** Tự động trích xuất thực thể địa lý từ tin nhắn tự do để truy vấn danh sách cửa hàng. | **Có:** Áp dụng tìm kiếm danh sách cửa hàng Long Châu trong database theo Quận/Huyện do user gõ. |
| **Ada Health (Symptom Checker)** | Chẩn đoán triệu chứng chuyên sâu nhưng có tuyên bố từ chối trách nhiệm pháp lý rất lớn ở mọi màn hình và cấm tuyệt đối việc kê đơn tự động. | **Medical Safety Guardrail:** Hiển thị cảnh báo đỏ và khuyên đi khám bác sĩ ngay khi có dấu hiệu bệnh lý nghiêm trọng. | **Có:** Tạo lớp chặn (Guardrail Layer) sử dụng Keyword/LLM Classifier để nhận diện câu hỏi y khoa và từ chối trả lời. |

---

## 5. Evidence -> Insight

*   **Evidence nổi bật nhất:** 
    *   Khách hàng vừa có nhu cầu mua mỹ phẩm da liễu cá nhân hóa vừa có nhu cầu tra cứu nhanh vị trí nhà thuốc gần nơi họ đang đứng mà không cần qua nhiều bước chọn biểu mẫu.
    *   Người dùng cực kỳ lo sợ và lên án việc AI tự chẩn đoán bệnh hoặc khuyên dùng các loại thuốc điều trị y khoa không có chuyên môn.
*   **Insight:** 
    *   Khách hàng mua sắm tại Long Châu không chỉ cần danh mục hàng hóa hay thông tin y khoa chung chung (*surface problem*). Thật ra họ cần **một trợ lý hỗ trợ mua sắm & tra cứu tiện ích nhanh gọn (skincare, định vị nhà thuốc, FAQ dịch vụ), đồng thời đòi hỏi sự bảo vệ nghiêm ngặt khỏi các khuyến nghị y tế sai lệch** khi họ vô tình tự kê đơn thuốc điều trị (*deeper need*).
*   **Opportunity:** 
    *   Cơ hội là dùng AI để **tư vấn cá nhân hóa sản phẩm skincare (Augment), định vị nhà thuốc gần nhất theo quận huyện và giải đáp nhanh FAQ chính sách**, giúp người dùng mua sắm và tương tác thuận tiện, đồng thời **chặn lọc cứng (Automate Guardrail) đối với các câu hỏi về thuốc kê đơn/bệnh lý** để đảm bảo an toàn y khoa bằng cách từ chối và chuyển hướng cuộc gọi đến dược sĩ thật.

---

## 6. Evidence đổi SPEC như thế nào?

*   [ ] Đổi user chính.
*   [ ] Đổi pain statement.
*   [x] Đổi build slice.
*   [x] Đổi Auto/Aug decision.
*   [x] Đổi 4 paths.
*   [x] Đổi failure mode.
*   [ ] Đổi owner/test plan.

**Ghi rõ thay đổi quan trọng:**
*   **Trước evidence, nhóm định:** Làm một chatbot AI tư vấn sức khỏe tổng quát cho Long Châu (hỏi gì đáp nấy, kể cả triệu chứng bệnh và gợi ý mua thuốc).
*   **Sau evidence, nhóm đổi thành:** Giới hạn phạm vi (Scope) của AI: **Chỉ tư vấn dòng chăm sóc cá nhân (Skincare), định vị nhà thuốc gần nhất theo địa chỉ ngôn ngữ tự nhiên, trả lời các FAQ đổi trả/thành viên**. Cấm tuyệt đối việc AI tư vấn thuốc điều trị (kê đơn/không kê đơn) hoặc tự chẩn đoán bệnh. AI phải chủ động từ chối và chuyển hướng sang Dược sĩ thật (Human-in-the-loop).
*   **Lý do:** Tránh rủi ro pháp lý nghiêm trọng về y tế, bảo vệ sức khỏe người dùng, đồng thời tối đa hóa tiện ích tra cứu tiện lợi hàng ngày cho khách hàng.
