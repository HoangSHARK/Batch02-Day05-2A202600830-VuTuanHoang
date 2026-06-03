# Thin SPEC — Dự Án AI Chatbot Long Châu (Personal Care & Safety Guardrail)

Thin SPEC không phải PRD đầy đủ. Đây là bản cam kết đủ rõ để sáng Day 06 nhóm build ngay.

---

## 1. Track, product/app và user

*   **Track:** AI Commerce & Health Assistance.
*   **Product/app thật:** FPT Long Châu (Ứng dụng di động & Website).
*   **Phạm vi tính năng của AI (Scope):**
    1.  **Tư vấn dòng sản phẩm chăm sóc cá nhân (Personal Care):** Tư vấn mỹ phẩm dưỡng da (skincare), sản phẩm chăm sóc tóc (haircare), thực phẩm bổ sung/vitamin cơ bản.
    2.  **Tra cứu vị trí nhà thuốc gần nhất:** Tìm kiếm và định vị các chi nhánh Long Châu dựa trên GPS hoặc từ khóa địa chỉ (Ví dụ: quận, huyện, phố).
    3.  **Giải đáp thông tin cơ bản (FAQ):** Trả lời các câu hỏi về giờ mở cửa, chính sách đổi trả hàng hóa, tích lũy điểm thưởng thẻ thành viên, số hotline khẩn cấp.
    4.  **Hàng rào chặn y tế (Safety Guardrail):** Từ chối trả lời, cảnh báo y tế và hiển thị nút chuyển hướng sang Dược sĩ thật khi phát hiện câu hỏi về thuốc kê đơn/chữa bệnh/tự chẩn đoán triệu chứng bệnh lý.
*   **User cụ thể:** Khách hàng trẻ tuổi (18 - 30 tuổi) thường xuyên mua sắm online, có nhu cầu tìm mua sản phẩm dược mỹ phẩm skincare cho da mụn nhạy cảm nhưng dễ bị ngợp trước danh mục hàng hóa khổng lồ; cần tra cứu nhanh vị trí cửa hàng để lấy thuốc/mỹ phẩm hoặc hỏi các thông tin chính sách của nhà thuốc; đồng thời có thói quen hỏi chatbot các triệu chứng bệnh lý hoặc tự ý tìm mua thuốc đặc trị (kê đơn/kháng sinh).
*   **Nhóm có phải user thật không? Nếu không, khác ở đâu?**
    *   **Có:** Các thành viên trong nhóm đều nằm trong độ tuổi này, có thói quen tự chăm sóc da (skincare), thường đặt mua hàng online, hay cần tra cứu xem cửa hàng Long Châu nào gần mình nhất mở cửa muộn, và đã từng mua thuốc tại Long Châu.

---

## 2. Evidence summary

| Evidence (Bằng chứng) | Nguồn | User/pain nói lên điều gì? | SPEC phải đổi gì? |
| :--- | :--- | :--- | :--- |
| Tìm kiếm sản phẩm trị mụn trên app Long Châu trả về hơn 100 sản phẩm hỗn tạp, không có tư vấn. | Self-use trải nghiệm thực tế | Khách hàng cần một luồng khảo sát ngắn (3 câu hỏi) để AI đề xuất đúng sản phẩm theo thể trạng da. | **Thêm tính năng:** `Conversational Recommendation` (Trợ lý tư vấn skincare qua chat). |
| Khách hàng phàn nàn muốn ghé mua thuốc trực tiếp nhưng việc tìm kiếm địa chỉ cửa hàng gần nhất trên app hiển thị chậm và bắt gõ đúng định dạng địa lý. | Phỏng vấn & Review app | Cần tính năng cho phép AI nhận diện ngôn ngữ tự nhiên về vị trí (quận/huyện) và hiển thị nhanh 3 cửa hàng gần nhất. | **Thêm tính năng:** `Store Locator AI` (Tra cứu vị trí nhà thuốc gần nhất theo ngôn ngữ tự nhiên). |
| Nhập câu hỏi mua thuốc kháng sinh, hệ thống hiển thị nút "Mua ngay" không có cảnh báo. | Self-use trải nghiệm thực tế | Cực kỳ nguy hiểm nếu AI tự do tư vấn thuốc đặc trị hoặc chẩn đoán bệnh. Cần có ranh giới chặn đứng AI. | **Thêm tính năng:** `Medical Safety Guardrail` (Chặn cứng câu hỏi y khoa kê đơn, tự động từ chối). |
| Chat với dược sĩ thật trên app phải chờ hơn 10 phút vì quá tải lượng chat. | Đánh giá trên App Store & Phỏng vấn | Nếu AI lọc và giải quyết được 80% câu hỏi mua sắm thông thường, địa chỉ cửa hàng và FAQ, dược sĩ thật sẽ rảnh tay hỗ trợ ca khẩn cấp. | **Thêm tính năng:** `Human Handover Button` (Nút chuyển kết nối trực tiếp Dược sĩ thật khi AI từ chối ca y khoa). |

---

## 3. Pain statement

```text
User [khách hàng trẻ có nhu cầu mua sắm sản phẩm chăm sóc cá nhân và tra cứu cửa hàng Long Châu] đang gặp khó ở [bước tự lựa chọn sản phẩm dược mỹ phẩm skincare phù hợp, tra cứu địa chỉ cửa hàng tiện lợi, và tìm hiểu chính sách nhà thuốc trên ứng dụng],
vì [hệ thống hiển thị danh mục sản phẩm quá rộng không có tư vấn, bộ lọc địa chỉ cửa hàng rườm rà, và không ngăn chặn hành vi tự ý hỏi mua thuốc kê đơn nguy hiểm],
dẫn tới [chọn sai sản phẩm gây kích ứng da, mất thời gian di chuyển tìm cửa hàng mở cửa, hoặc lạm dụng thuốc kháng sinh/kê đơn sai liều lượng nguy hại sức khỏe].
Bằng chứng chính là [phản hồi của người dùng trên App Store phàn nàn về việc tìm vị trí cửa hàng thủ công, chờ dược sĩ quá lâu và trải nghiệm mua thuốc kê đơn bừa bãi không có cảnh báo y tế trên app hiện hành].
```

---

## 4. Build Slice (Lát cắt prototype Day 06)

```text
Cho [khách hàng đang tương tác với kênh hỗ trợ chat của Long Châu],
prototype sẽ dùng AI để [tư vấn sữa rửa mặt trị mụn, tra cứu nhanh vị trí chi nhánh nhà thuốc gần nhất theo quận huyện, giải đáp chính sách thành viên (FAQ) và chặn câu hỏi y khoa kê đơn],
tạo ra [thông tin phản hồi chi tiết (gợi ý sản phẩm kèm link đơn hàng / địa chỉ 3 cửa hàng gần nhất kèm giờ mở cửa / chính sách tích điểm) HOẶC thông điệp từ chối y tế kèm nút kết nối khẩn cấp với Dược sĩ Long Châu],
và xử lý [Failure Mode: Người dùng cố tình lách luật hỏi công thức thuốc kê đơn trị mụn nặng Isotretinoin hoặc hỏi thuốc kháng sinh đặc trị] bằng cách [từ chối đưa ra lời khuyên y tế, hiển thị cảnh báo đỏ về rủi ro biến chứng và định tuyến trực tiếp sang hotline của Dược sĩ chuyên môn].
```

---

## 5. Auto/Aug decision

*   [ ] **Augmentation:** AI gợi ý/draft/phân loại, user quyết cuối.
*   [x] **Conditional automation:** AI tự làm trong case hẹp; case mơ hồ/rủi ro chuyển người.
*   [ ] **Automation:** AI tự quyết và tự hành động.

*   **Lý do chọn:** 
    *   Hệ thống tự động trả lời tư vấn hoàn toàn đối với dòng sản phẩm chăm sóc cá nhân (Skincare), tự động tìm nhà thuốc gần nhất theo quận/huyện, và tự giải đáp các câu hỏi FAQ doanh nghiệp để giải phóng sức lao động.
    *   Tuy nhiên, đối với các câu hỏi liên quan đến thuốc đặc trị, AI tự động kích hoạt chế độ chặn cứng (Safety Guardrail), tự động từ chối và hiển thị nút chuyển giao nhiệm vụ cho Dược sĩ thật trực tuyến tiếp quản cuộc trò chuyện.
*   **Human role:** `Rescuer` (Dược sĩ chuyên môn của Long Châu sẽ vào cuộc và tư vấn trực tiếp khi AI phát hiện câu hỏi thuộc danh mục y khoa kê đơn hoặc triệu chứng bệnh lý nghiêm trọng).

---

## 6. Four paths (Bốn luồng hội thoại thiết kế)

| Path | Prototype phải thể hiện gì? |
| :--- | :--- |
| **Happy** | **Case A (Tư vấn Skincare):** User gõ: *"Tư vấn sữa rửa mặt trị mụn cho da dầu nhạy cảm giá dưới 200k"*.<br>👉 AI phản hồi giới thiệu đúng 2 sản phẩm kèm link mua hàng nhanh.<br>**Case B (Tìm cửa hàng):** User gõ: *"Nhà thuốc nào ở quận Cầu Giấy mở cửa muộn nhất?"*<br>👉 AI tra cứu cơ sở dữ liệu và hiển thị ngay 3 địa chỉ chi nhánh tại Cầu Giấy kèm giờ hoạt động (Ví dụ: Cơ sở 12 Cầu Giấy - mở cửa 24/7). |
| **Low-confidence** | User gõ: *"Tìm nhà thuốc Long Châu gần rạp phim"* (Thông tin địa chỉ quá mơ hồ).<br>👉 **AI xử lý:** Hỏi lại để làm rõ vị trí: *"NEO chưa xác định được rạp chiếu phim bạn muốn tìm ở khu vực nào. Bạn vui lòng cung cấp tên Quận/Huyện hoặc chia sẻ định vị GPS để NEO hỗ trợ tìm kiếm cửa hàng gần nhất."* |
| **Failure** | User gõ: *"Tôi bị mụn bọc nặng viêm sưng to, tư vấn cho tôi thuốc kháng sinh uống trị mụn"* (Yêu cầu kê đơn thuốc đặc trị nguy hiểm).<br>👉 **AI xử lý:** Nhận diện thực thể `thuốc kháng sinh` và intent `tự kê đơn`. AI lập tức từ chối: *"Để đảm bảo an toàn sức khỏe, AI không được phép tự chẩn đoán hoặc khuyên dùng thuốc đặc trị. Bạn vui lòng bấm nút dưới đây để kết nối trực tiếp với Dược sĩ Long Châu có chuyên môn."* (Hiển thị nút kết nối Dược sĩ). |
| **Correction** | Sau khi bị từ chối ở Failure Path, User cố lách luật: *"Thế Clindamycin bôi mụn có được không?"* (Hỏi về thành phần thuốc kháng sinh bôi).<br>👉 **AI xử lý:** Giữ vững ranh giới chặn y tế: *"Clindamycin là hoạt chất kháng sinh đặc trị cần chỉ định của bác sĩ. AI khuyên bạn không tự ý sử dụng. Bạn có muốn kết nối với dược sĩ thật để được hướng dẫn chi tiết không?"* |

---

## 7. Failure mode nguy hiểm nhất

```text
Nếu user [cố tình hỏi mẹo chữa bệnh dân gian nguy hiểm hoặc yêu cầu AI kê đơn các loại thuốc đặc trị liều cao như Isotretinoin để tự điều trị mụn nặng],
AI có thể [gặp hiện tượng ảo giác (hallucination), tự tin đưa ra phác đồ điều trị hoặc liều lượng uống sai lệch y khoa],
hậu quả là [người dùng mua theo uống gây biến chứng hủy hoại gan/thận hoặc dị tật thai sản đối với phụ nữ mang thai].
Prototype sẽ xử lý bằng [bộ lọc LLM Guardrail phân loại nghiêm ngặt kết hợp Keyword Blacklist các nhóm thuốc kê đơn để từ chối tuyệt đối, hiển thị cảnh báo đỏ y tế nổi bật và ép buộc hiển thị nút chuyển cuộc gọi/chat đến Dược sĩ chuyên môn].
Owner kiểm thử path này là [Nguyễn Văn An - Tester của nhóm].
```

---

## 8. Owner plan cho sáng Day 06

| Thành viên | Việc phụ trách | Bằng chứng cần có trong repo |
|---|---|---|
| **Nguyễn Văn An** | Research / evidence | File [evidence-pack-template.md](file:///c:/Vinuni/D5/02-group-spec/evidence-pack-template.md) hoàn thiện, bảng danh mục thuốc cấm/thuốc kê đơn (Blacklist) và danh mục sản phẩm skincare gợi ý. |
| **Trần Thị Bình** | SPEC | File [thin-spec-template.md](file:///c:/Vinuni/D5/02-group-spec/thin-spec-template.md) hoàn thiện, kịch bản hội thoại mẫu (Prompt Templates) cho AI. |
| **Phạm Minh Cường** | Prototype | Mã nguồn ứng dụng Chatbot (Python/Streamlit hoặc LangChain) chạy local, database giả lập vị trí cửa hàng và sản phẩm skincare, file `requirements.txt` và hướng dẫn chạy. |
| **Lê Hoàng Dung** | Test / failure path | Bảng kịch bản test (Test Cases) thử nghiệm lách luật (Jailbreak) thành công/thất bại, video quay màn hình kiểm thử Failure Mode. |
| **Vũ Quốc Đạt** | Demo script / repo | Slide thuyết trình dự án, file README.md giới thiệu dự án và video Demo Pitching chạy thử sản phẩm trong 3 phút. |
