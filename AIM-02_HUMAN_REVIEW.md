# AIM-02 — Human Review (Batch 01 Checkpoint)

**Ngày:** 2026-11-25 (Asia/Saigon) | **Trạng thái:** `PROVISIONAL` (chưa nghiệm thu chính thức, chưa xác nhận lỗi IT)

---

## 1. Những gì đã kiểm thử
Đã chạy có kiểm soát **Batch 01** gồm **3 test cases** trên chatbot Zalo pilot (được TJ xác nhận quyền sử dụng) và đối soát độc lập bởi Codex:
- **TC-01 (Khai thác nhu cầu):** Khách hỏi bảo hiểm cho gia đình 4 người, tài chính vừa phải → Chấm `PARTIAL` theo rubric discovery nháp (`PASS` cho số liệu phí/STBH).
- **TC-03A (Phạm vi địa lý):** Khách hỏi đi du lịch Thái Lan có được bảo vệ bởi gói *Tai nạn Hộ gia đình* không và dựa vào điều khoản nào → AGY chấm `PASS` phạm vi gói chuẩn trên web; Codex chấm `PASS` phạm vi web và `PARTIAL` về độ đầy đủ đối chiếu PDF Quy tắc gốc.
- **TC-03B (Loại trừ có điều kiện):** Khách hỏi uống rượu bia rồi tự lái xe máy bị tai nạn có chi trả không → Cả AGY và Codex chấm `PASS` trong phạm vi giải thích hai điều khoản loại trừ đã hỏi.

*(Toàn bộ transcript gốc, 3 screenshot đã che thanh chat riêng tư, `evidence_index.csv` và PDF Quy tắc AAA 22 trang được lưu bảo mật trong `private/aimica/AIM-02/`.)*

## 2. Điểm mạnh chatbot có bằng chứng
- **Không bịa đặt dẫn chứng:** Ở TC-03A, khi không có số điều/khoản PDF, bot thừa nhận rõ *"chưa có số điều/khoản"* và hướng dẫn xem tài liệu chính thức hoặc gọi hotline `1900 8888 68`.
- **Giữ sắc thái điều khoản cẩn trọng:** Ở TC-03B, bot trích đúng hai căn cứ loại trừ (*vi phạm luật ATGT* và *rượu bia là nguyên nhân dẫn đến tai nạn*), không tự suy diễn ngưỡng nồng độ cồn.
- **Số liệu & miễn trừ rõ ràng:** Ở TC-01, bot nêu đúng mức phí 500k/800k/hộ/năm, STBH 30tr/50tr/người, điều kiện cùng cư trú và lưu ý giá tham khảo.

## 3. Các điểm cần xác minh thêm
- **Thứ tự tư vấn (TC-01):** Bot gợi ý/nghiêng về *Tai nạn Hộ gia đình* trước khi hỏi khách ưu tiên bảo vệ tai nạn hay chi phí chữa bệnh, tuổi hai bé và khoảng ngân sách.
- **Ngoại lệ hợp đồng (TC-03A):** Bot trả lời theo phạm vi chuẩn trên web (Việt Nam), chưa nhắc Điều 2 (tr.6) & Ghi chú (tr.8) PDF AAA cho phép quy định lãnh thổ khác trên Hợp đồng/GCNBH.
- **Ngữ cảnh phiên chat:** TC-01 có nhắc *"không phải cam kết trả 100% viện phí"* (có thể liên quan câu hỏi trước trong phiên); **chưa đủ bằng chứng** kết luận đây là lỗi nhiễu ngữ cảnh (*context contamination*).

## 4. Câu hỏi dành cho Business Owner
1. **Quy trình tư vấn (Sales Journey):** Bot được phép *"gợi ý có điều kiện trước rồi hỏi lại"* hay bắt buộc *"hỏi đủ nhu cầu rồi mới khuyến nghị"*?
2. **Phạm vi trả lời ngoại lệ:** Bot chỉ tư vấn gói tiêu chuẩn trên web hay phải giải thích thêm khả năng mở rộng lãnh thổ theo Điều 2 Quy tắc khung? AIMICA có bán mở rộng phạm vi ngoài Việt Nam cho gói này không?
3. **Ngưỡng chấp nhận & Bộ tài liệu chuẩn:** AIMICA phê duyệt rubric/ngưỡng đạt nào và xác nhận bộ PDF Quy tắc chính thức cho các sản phẩm còn lại?

## 5. Câu hỏi dành cho IT
1. **Nguồn tri thức (KB):** Bot pilot hiện đang dùng danh mục nguồn/phiên bản nào; file PDF 22 trang (dạng scan, không có text layer) đã được OCR và nạp vào KB chưa?
2. **Quy tắc trích dẫn:** Có cấu hình hạn chế dẫn số điều hoặc ưu tiên trả lời theo trang sản phẩm web không?
3. **Quản lý phiên (`/new`):** Cách tạo phiên ngữ cảnh sạch hợp lệ để phục vụ kiểm thử đối chứng là gì?
4. **Chuyển người thật (Handoff):** Bot chỉ hiển thị số hotline hay có cơ chế đẩy hội thoại sang nhân viên trực thật trên Zalo?

## 6. Các cải tiến tiềm năng *(chỉ là gợi ý, KHÔNG phải lỗi IT đã xác nhận)*
- Hỏi khoảng ngân sách và ưu tiên (tai nạn vs chữa bệnh) sớm hơn trong luồng tư vấn gia đình.
- Bổ sung dẫn số Điều/Khoản (Điều 2 tr.6, Điều 9.2–9.3 tr.7) và nhắc kiểm tra Hợp đồng/GCNBH nếu có thỏa thuận riêng (sau khi Business Owner chốt phạm vi).
- Chuẩn hóa hướng dẫn thu thập thông tin hồ sơ trước khi chuyển chuyên viên với các ca có điều kiện loại trừ.

## 7. Đề xuất các lựa chọn Batch 02 *(CHƯA chạy, chờ TJ quyết định)*
- **Lựa chọn A (Theo đề xuất đối soát của Codex — 3 thiết kế kiểm chứng sâu):**
  1. Phạm vi địa lý (gói chuẩn vs nhánh hợp đồng mở rộng lãnh thổ).
  2. Loại trừ có điều kiện (tách nguyên nhân rượu bia vs vi phạm ATGT vs thiếu dữ kiện).
  3. Discovery trong context sạch vs context cũ (yêu cầu mới ưu tiên chi phí chữa bệnh/nằm viện).
- **Lựa chọn B (Bổ sung kiểm tra Human Handoff):** Giữ **TC-09** (ca bệnh nền tiểu đường xin gặp tư vấn viên) để kiểm tra kênh chuyển người thật trước khi mở rộng sang sản phẩm khác.
