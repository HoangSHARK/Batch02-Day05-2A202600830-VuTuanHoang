# Toolkit — Từ Evidence Đến Build Slice: Chatbot Long Châu (Personal Care & Safety Guardrail)

Dùng sau khi nhóm đã có evidence. Mục tiêu là chốt một build slice đủ nhỏ cho Day 06.

---

## 1. Gom evidence thành cụm

Gom theo **workflow/pain** của người dùng khi tương tác mua sắm y tế & dược mỹ phẩm trực tuyến:

*   **Cụm 1: "Ngợp và hoang mang khi tự chọn Dược mỹ phẩm (Skincare)"**
    *   *Mô tả:* Khách hàng có nhu cầu làm đẹp/chữa mụn cơ bản bị ngợp trước hàng trăm loại kem chống nắng, sữa rửa mặt trên app. Họ thiếu thông tin tư vấn cá nhân hóa (da dầu, da khô nhạy cảm nên dùng loại nào).
    *   *Bằng chứng:* Phản ánh trên diễn đàn skincare và khảo sát self-use khi tìm từ khóa trên app Long Châu.
*   **Cụm 2: "Khó tra cứu địa điểm và chính sách cửa hàng khi cần gấp"**
    *   *Mô tả:* Khách hàng cần tìm nhà thuốc Long Châu gần nhất đang hoạt động hoặc muốn biết các chính sách bảo hành, đổi trả hàng hóa, tích điểm thẻ nhưng công cụ lọc trên app quá cồng kềnh, khó dùng bằng ngôn ngữ nói.
    *   *Bằng chứng:* Đánh giá và phản hồi của người dùng về tính tiện ích của app khi di chuyển ngoài đường.
*   **Cụm 3: "Rủi ro tự kê đơn thuốc nguy hiểm (Medical Safety Hazard)"**
    *   *Mô tả:* Người dùng có thói quen hỏi chatbot/khung tìm kiếm triệu chứng bệnh để tự tìm mua thuốc đặc trị (ví dụ: thuốc kháng sinh, thuốc kê đơn) mà không có sự kiểm duyệt của người có chuyên môn.
    *   *Bằng chứng:* Nhập thử *"đau bụng uống kháng sinh gì"* hiện ngay nút mua thuốc kháng sinh mạnh trên app mà không cảnh báo.
*   **Cụm 4: "Quá tải kênh chat với dược sĩ thật"**
    *   *Mô tả:* Kênh chat trực tiếp của Long Châu luôn trong tình trạng quá tải do dược sĩ phải trả lời song song cả những câu hỏi cơ bản về mỹ phẩm, tìm địa chỉ, FAQ và các ca bệnh thực tế cần tư vấn thuốc gấp.
    *   *Bằng chứng:* Trải nghiệm chờ chat trực tuyến mất hơn 10 phút.

---

## 2. Viết insight

*   **Form:**
    ```text
    User [segment] không chỉ cần [surface need].
    Họ thật ra cần [deeper need],
    vì [evidence pattern].
    ```
*   **Áp dụng vào Long Châu Chatbot:**
    *   Khách hàng mua sắm dược mỹ phẩm và chăm sóc cá nhân trực tuyến **không chỉ cần một danh mục hàng hóa hay bộ lọc địa điểm tĩnh**.
    *   Họ thực chất cần **một trợ lý đa năng tư vấn cá nhân hóa sản phẩm skincare hàng ngày, chỉ dẫn nhanh vị trí cửa hàng gần nhất theo định vị/ngôn ngữ tự nhiên, đồng thời đảm bảo ranh giới an toàn tuyệt đối khi chạm đến các vấn đề y khoa kê đơn**,
    *   vì các khảo sát thực tế cho thấy họ bị ngợp thông tin sản phẩm và địa chỉ cửa hàng khi đang di chuyển, nhưng lại cực kỳ nhạy cảm và lo sợ về việc AI tự ý chẩn đoán/kê đơn thuốc chữa bệnh nguy hại đến sức khỏe.

---

## 3. Viết opportunity

*   **Form:**
    ```text
    Cơ hội là dùng AI để [augment/automate hành động hẹp],
    giúp user [kết quả],
    trong khi vẫn kiểm soát [failure/risk].
    ```
*   **Áp dụng vào Long Châu Chatbot:**
    *   Cơ hội là dùng AI để **tư vấn cá nhân hóa sản phẩm dưỡng da mụn (Augment), định vị nhanh nhà thuốc gần nhất theo khu vực địa lý nhập tự do và giải đáp chính sách dịch vụ FAQ**,
    *   giúp người dùng chọn đúng sản phẩm, tìm nhanh cửa hàng phù hợp để mua sắm tiện lợi,
    *   trong khi vẫn kiểm soát rủi ro y tế bằng cách **tự động từ chối trả lời và chuyển hướng sang Dược sĩ thật (Automate Safety Guardrail)** khi phát hiện các câu hỏi liên quan đến thuốc đặc trị/kê đơn hoặc tự chẩn đoán bệnh.

---

## 4. Chọn build slice

Build slice của nhóm sẽ được kiểm chứng qua 5 tiêu chí:

| Câu hỏi | Trạng thái đạt được của dự án |
| :--- | :--- |
| **User cụ thể chưa?** | **Đạt:** Khách hàng trẻ (18 - 30 tuổi) có nhu cầu tìm mua sản phẩm Dược mỹ phẩm (sữa rửa mặt, kem chống nắng) trên kênh online Long Châu, cần tìm kiếm cửa hàng chi nhánh gần khu vực của mình, và thỉnh thoảng tò mò hỏi thêm về thuốc trị mụn kê đơn. |
| **Task đủ hẹp chưa?** | **Đạt:** Chỉ thực hiện 4 tác vụ cụ thể: (1) Tư vấn sữa rửa mặt trị mụn cho da dầu mụn qua 3 câu hỏi; (2) Tra cứu 3 nhà thuốc gần nhất dựa trên tên Quận/Huyện do user nhập; (3) Giải đáp chính sách đổi trả hàng hóa/tích điểm; (4) Chặn câu hỏi về thuốc kê đơn và đưa nút chuyển dược sĩ. |
| **AI decision rõ chưa?** | **Đạt:** AI phân tích loại da từ câu trả lời của user để gợi ý sản phẩm (Augmentation); AI phân tích từ khóa địa lý để lọc nhà thuốc phù hợp; AI phân loại intent nhạy cảm y khoa để kích hoạt từ chối (Safety Guardrail). |
| **Failure path rõ chưa?** | **Đạt:** Người dùng cố tình gõ hỏi mua thuốc kê đơn điều trị mụn nặng hoặc hỏi chẩn đoán mụn viêm nặng bôi thuốc gì. AI phải chặn đứng câu hỏi này, cảnh báo rủi ro tự ý dùng thuốc và đưa nút chuyển hotline dược sĩ. |
| **Có evidence không?** | **Đạt:** Có đầy đủ bằng chứng từ việc tự trải nghiệm tìm kiếm trên app Long Châu và review thực tế của khách hàng trẻ trên các group làm đẹp. |

---

## 5. Quyết định: giữ, giảm scope, hay đổi hướng?

*   **Tình huống:** Dự án y tế có rủi ro pháp lý và an toàn sức khỏe cực kỳ cao nếu để AI tự do giao tiếp y khoa.
*   **Quyết định:** Chọn mô hình **Conditional Automation** kết hợp **Augmentation**:
    *   **Augmentation (Tư vấn cá nhân & Tra cứu thông tin):** AI gợi ý sản phẩm skincare thông thường, chỉ đường đến cửa hàng gần nhất theo quận huyện và trả lời FAQ chính sách, user tự đưa ra lựa chọn mua sắm.
    *   **Conditional Automation (Chặn y khoa & Chuyển người thật):** AI tự động chạy bộ lọc từ chối y tế đối với thuốc điều trị, tự động sinh cảnh báo và hiển thị nút kết nối Dược sĩ thật mà không cần nhân viên can thiệp kích hoạt thủ công.

---

## 6. Câu chốt cuối

> [!IMPORTANT]
> Dựa trên **bằng chứng về sự quá tải của kênh chat dược sĩ và nhu cầu tra cứu nhanh địa điểm/skincare của khách hàng**, nhóm sẽ build **prototype Chatbot Long Châu Smart Assistant**, cho **khách hàng trẻ tương tác trực tuyến**, để giải quyết **khó khăn chọn sản phẩm da liễu, bất tiện khi tìm cửa hàng gần nhất và rủi ro tự kê đơn thuốc kê đơn bừa bãi**, bằng cách AI **tư vấn skincare dưỡng da, định vị nhà thuốc theo quận/huyện, giải đáp FAQ cơ bản và tự động chặn lọc câu hỏi y khoa đặc trị**, và sẽ test failure path **người dùng gõ yêu cầu AI kê đơn thuốc đặc trị mụn Isotretinoin hoặc kháng sinh điều trị viêm nhiễm**.

---

## 7. Backlog (Những thứ KHÔNG build trong Day 06)

*   **Tác vụ y khoa nâng cao:** Không cho phép AI đọc toa thuốc viết tay bằng ảnh (OCR).
*   **Tích hợp thanh toán:** Không build cổng thanh toán trực tiếp trong khung chat (chỉ trả link giỏ hàng của Long Châu để thanh toán trên web/app).
*   **Tích hợp Bản đồ động (Dynamic Map GPS Navigation):** Không hiển thị bản đồ trực tiếp chỉ đường động trên chat (chỉ trả text địa chỉ + giờ mở cửa để giảm thiểu độ phức tạp tích hợp API bản đồ trong 1 ngày).
*   **Tư vấn bệnh lý:** Không xây dựng hệ thống chẩn đoán triệu chứng bệnh (Symptom Checker) cho các bệnh lý khác ngoài tư vấn da liễu thông thường.
