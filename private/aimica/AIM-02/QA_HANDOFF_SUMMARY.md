# AIM-02 — QA Handoff Summary (Sau Batch 01 & Independent Review)

**Ngày:** 2026-11-25 (Asia/Saigon)  
**Trạng thái chung:** `PROVISIONAL` (Batch 01 đã hoàn tất kiểm thử có kiểm soát và đối soát độc lập; chưa có tiêu chí nghiệm thu chính thức từ AIMICA/Business Owner).

---

## 1. Đã kiểm thử gì?
- Thực hiện **AIM-02 — Live QA Batch 01** trên tài khoản Zalo pilot **"Bot AI Assistant 01"** (được TJ xác nhận quyền kiểm thử) với đúng **3 test cases** tuần tự trong cùng phiên:
  - **TC-01:** Khai thác nhu cầu gia đình 4 người, tài chính vừa phải (*Needs Discovery & Product Accuracy*).
  - **TC-03A:** Phạm vi địa lý đi du lịch Thái Lan của gói *BH Tai Nạn Hộ Gia Đình* và nguồn điều khoản (*Coverage & Source Grounding*).
  - **TC-03B:** Tình huống uống rượu bia tự lái xe máy bị tai nạn của gói *BH Tai Nạn Hộ Gia Đình* (*Exclusions & Cause Assessment*).

## 2. Bằng chứng ở đâu? (Tất cả nằm trong `private/`, bị `.gitignore` loại trừ)
- Transcript gốc (không chỉnh sửa): `private/aimica/AIM-02/raw/batch01_transcript.json`
- 3 ảnh chụp màn hình đã cắt thanh chat riêng tư:
  - `private/aimica/AIM-02/redacted/TC-01.png`
  - `private/aimica/AIM-02/redacted/TC-03A.png`
  - `private/aimica/AIM-02/redacted/TC-03B.png`
- Chỉ mục bằng chứng đã đối soát: `private/aimica/AIM-02/evidence_index.csv`
- Báo cáo Independent Review của Codex (không chỉnh sửa): `private/aimica/AIM-02/AIM-02_INDEPENDENT_REVIEW_CODEX_2026-11-25.md`
- Tài liệu gốc đối chiếu (PDF 22 trang Bảo hiểm AAA): `private/aimica/AIM-02/reference/QTBH_Tai_nan_Con_nguoi_toan_dien_2025.pdf`

## 3. Phát hiện nào có thể kiểm chứng (`VERIFIED`)?
1. **TC-01 (`PARTIAL` theo rubric discovery dự thảo):** Bot nêu đúng phí tham khảo (500k/800k/hộ/năm), STBH (30tr/50tr/người), điều kiện cùng cư trú và có lưu ý giới hạn quyền lợi; tuy nhiên bot gợi ý/nghiêng về *Tai nạn Hộ gia đình* trước khi hỏi ưu tiên bảo vệ (tai nạn vs chữa bệnh) và độ tuổi 2 bé, đồng thời chưa hỏi khoảng ngân sách.
2. **TC-03A (Đúng với phạm vi sản phẩm chuẩn trên web; độ đầy đủ về ngoại lệ hợp đồng còn cần xác nhận — AGY: `PASS` phạm vi web / Codex: `PASS` web + `PARTIAL` đối chiếu PDF):** Bot trả lời đúng giới hạn lãnh thổ Việt Nam theo trang web, trung thực thừa nhận chưa có số điều/khoản PDF để dẫn thay vì bịa đặt; chưa nêu nhánh ngoại lệ hợp đồng quy định lãnh thổ khác (Điều 2 tr.6, Ghi chú tr.8 PDF AAA).
3. **TC-03B (`PASS` trong phạm vi đã kiểm thử):** Bot trích đúng 2 điều khoản loại trừ (vi phạm luật ATGT và rượu bia là nguyên nhân dẫn đến tai nạn — khớp Điều 9.2–9.3 tr.7 PDF AAA), giữ đúng điều kiện nhân quả và không tự đặt ngưỡng nồng độ cồn.

## 4. Giả thuyết nào chưa chứng minh (KHÔNG kết luận là Confirmed IT Defects)?
- **Chưa chứng minh "PDF 22 trang chưa được nạp vào KB":** Thiếu citation số điều ở TC-03A có thể do chưa nạp PDF, hoặc do chưa OCR/truy xuất đúng đoạn, hoặc do cấu hình ưu tiên trả lời theo tóm tắt sản phẩm đang bán.
- **Chưa chứng minh "context contamination" (nhiễu ngữ cảnh):** Lời lưu ý về viện phí trong TC-01 có thể do duy trì hội thoại bình thường với lượt cũ trong phiên; chưa có cặp test đối chứng giữa context sạch và context cũ.
- **Chưa chứng minh khả năng chuyển người thật (Human Handoff thực tế):** Bot mới chỉ đưa số hotline `1900 8888 68`, chưa kiểm thử khả năng chuyển live agent.

## 5. Business Owner cần quyết định gì?
1. **Sales Journey (TC-01):** Cho phép bot *"gợi ý có điều kiện rồi mới hỏi lại"* hay bắt buộc *"hỏi đủ nhu cầu (ưu tiên, tuổi, ngân sách) rồi mới khuyến nghị"*?
2. **Phạm vi tư vấn ngoại lệ hợp đồng (TC-03A):** Bot chỉ cần trả lời theo gói chuẩn đang bán trên web hay phải giải thích thêm nhánh mở rộng lãnh thổ theo Điều 2 Quy tắc khung?
3. **Mức độ chi tiết loại trừ & hồ sơ (TC-03B):** Có yêu cầu bot dẫn số Điều/Khoản PDF và hướng dẫn danh mục hồ sơ (Điều 16) hay giữ mức cảnh báo hiện tại rồi chuyển hotline?
4. **Phê duyệt Rubric & Ngưỡng nghiệm thu:** Chốt bộ tiêu chí chính thức của AIMICA trước khi phân loại bất kỳ lỗi IT nào.
5. **Quy trình làm sạch phiên & tri thức:** Xác nhận với IT cách tạo context sạch hợp lệ (`/new`) và danh mục tài liệu chính thức đã nạp vào bot pilot.

## 6. Đề xuất Batch tiếp theo (Batch 02 — CHƯA chạy, chờ TJ & Business Owner chốt)
Dựa trên đề xuất đối soát của Codex:
1. **Phạm vi địa lý mở rộng vs chuẩn:** Kiểm tra khả năng phân biệt sản phẩm chuẩn với nhánh giả lập hợp đồng có ghi lãnh thổ khác (giải quyết điểm mở của TC-03A).
2. **Loại trừ có điều kiện (rượu bia / giao thông):** Kiểm tra ranh giới bot khi gặp tình huống giả lập tách riêng yếu tố *"không phải nguyên nhân"* vs *"vi phạm ATGT"* và dữ kiện chưa đủ.
3. **Discovery trong context sạch vs context cũ:** Chạy cùng nhu cầu gia đình nhưng ưu tiên chi phí chữa bệnh/nằm viện trên 2 trạng thái (context sạch sau khi IT xác nhận cách reset vs context có gợi ý tai nạn cũ) để kiểm chứng giả thuyết ngữ cảnh.
*(Lưu ý: Vẫn còn TC-09 về Human Handoff từ danh sách ưu tiên ban đầu nếu TJ muốn đưa vào kiểm tra kênh chuyển người thật.)*
