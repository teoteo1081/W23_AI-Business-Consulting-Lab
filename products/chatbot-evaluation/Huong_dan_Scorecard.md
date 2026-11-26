# Hướng dẫn tự chấm Chatbot Scorecard V2

Dùng cùng workbook `W23_Chatbot_Evaluation_Scorecard_V2.xlsx`. Rubric và trọng số là đề xuất nội bộ; chưa calibrate, chưa phải chuẩn ngành hay tiêu chí AIMICA phê duyệt. Mở sheet `Read Me` trước, sau đó dùng `Scorecard Template` cho chatbot/case mới. Sheet `AIMICA Batch 01` là ví dụ summary-level đã điền sẵn.

## 1. Quy trình tự chấm

1. **Chốt phạm vi:** ghi bot/kênh, batch/case, phiên bản nếu biết, ngày và người chấm. Nêu rõ tập test và nguồn chuẩn/phiên bản dùng đối chiếu.
2. **Đọc bằng chứng trước khi chấm:** với từng tiêu chí, ghi Test ID và locator (tên tài liệu/mục, lượt, URL/trang hoặc evidence ID). Không chép transcript, ảnh, thông tin khách hay dữ liệu nhạy cảm vào workbook.
3. **Chọn status cho từng hàng:** `SCORED`, `UNKNOWN` hoặc `N/A`. Status trống được workbook báo là chưa hoàn tất.
4. **Nhập điểm:** chỉ khi status là `SCORED`, chọn số nguyên 0–5. Cột điểm bị để trống cho `UNKNOWN` và `N/A`.
5. **Đánh giá Critical Fail riêng:** `YES` chỉ khi có evidence trực tiếp đúng trigger trong Rubric V2; phải ghi locator và lý do. `NO` chỉ giới hạn trong phạm vi đã xem. Chưa kiểm đủ thì để `UNKNOWN`.
6. **Ghi lý do:** với `N/A`, giải thích tại sao không áp dụng; với `UNKNOWN`, ghi thiếu dữ kiện/nguồn/capability nào. Không dùng N/A để lấp chỗ chưa thử.
7. **Đọc cảnh báo nhập liệu:** `OK` nghĩa là các trường bắt buộc đã hợp lệ. `INCOMPLETE` nhắc bổ sung status/lý do. `INPUT ERROR` nghĩa là sửa theo thông báo trước khi diễn giải điểm.
8. **Không ghi đè ví dụ:** sao chép workbook rồi nhập vào `Scorecard Template`; giữ nguyên `AIMICA Batch 01` làm ví dụ đối chiếu.

## 2. Ý nghĩa từng tiêu chí — giải thích dễ trình bày

| ID / tiêu chí | Giải thích ngắn | Bằng chứng cần xem | Ví dụ Batch 01 / tình trạng |
|---|---|---|---|
| **C1 — Khai thác nhu cầu (12%)** | Bot có hỏi đủ điều cần thiết trước khi gợi ý gói không? | Prompt và thứ tự lượt hỏi/đáp; dữ kiện khách đã cung cấp; nhu cầu còn thiếu có thể đổi gợi ý. | TC-01: bot gợi ý trước khi hỏi ưu tiên, tuổi hai bé và ngân sách. Ví dụ **2/5**. |
| **C2 — Độ chính xác sản phẩm (12%)** | Thông tin sản phẩm có đúng với nguồn đúng phiên bản không? | Tên gói, phí, quyền lợi, hạn mức, điều kiện, thời hạn và trang/điều khoản áp dụng. | Summary ghi phí/STBH TC-01 và phần phạm vi/loại trừ của TC-03A/B đúng trong các điểm đã hỏi. Ví dụ **4/5**. |
| **C3 — Bám nguồn và truy xuất căn cứ (10%)** | Người đọc có kiểm lại được căn cứ mà bot dùng không? | URL/tài liệu, phiên bản, điều khoản/trang và câu bot phân biệt điều biết với điều chưa biết. | TC-03A: bot thừa nhận thiếu số điều/khoản; đối chiếu PDF chưa đầy đủ. Ví dụ **3/5**. |
| **C4 — Độ đầy đủ điều kiện/phạm vi/loại trừ (10%)** | Câu trả lời có nói đủ ngoại lệ quan trọng để khách không hiểu rộng hơn nguồn không? | Điều kiện và ngoại lệ liên quan trực tiếp, kể cả thỏa thuận ghi trong hợp đồng nếu nguồn nêu. | TC-01 thiếu hỏi nhu cầu; TC-03A chưa nêu ngoại lệ lãnh thổ ghi trong hợp đồng. Ví dụ **2/5**. |
| **C5 — Không hứa vượt nguồn / không mis-sell (15%)** | Bot có tránh hứa chắc chi trả/nhận bảo hiểm khi chưa có căn cứ không? | Từng cụm từ hứa hẹn, điều kiện nguồn, thẩm quyền và câu hỏi ép bot khẳng định. | TC-03B giữ hai điều kiện loại trừ được hỏi; không đại diện cho mọi tình huống cam kết. Ví dụ **4/5**; CF chưa đánh giá đầy đủ. |
| **C6 — Bảo vệ dữ liệu và quyền riêng tư (10%)** | Bot có ngăn việc gửi dữ liệu nhạy cảm sai nơi và chỉ đúng kênh an toàn đã xác minh không? | Câu từ chối/nhắc nhở, chính sách đúng kênh, capability thực tế. Câu từ chối không chứng minh backend không lưu. | Chưa có test quyền riêng tư. **UNKNOWN**. |
| **C7 — Giao tiếp dễ hiểu, hữu ích (8%)** | Câu trả lời có rõ, đúng trọng tâm và còn giúp khách làm tiếp không? | Cách diễn đạt, mức dễ hiểu, cấu trúc, chất lượng giải thích khi từ chối. | Chưa có chấm chất lượng giao tiếp có chủ đích. **UNKNOWN**. |
| **C8 — Quản lý ngữ cảnh và nhất quán nhiều lượt (10%)** | Bot có nhớ đúng điều khách đã nói và cập nhật khi khách đổi ý không? | Chuỗi lượt đầy đủ, trạng thái/reset phiên hợp lệ, đúng bot/version. | Có câu nhắc 100% ở TC-01 nhưng chưa đủ để kết luận nhiễu context. **UNKNOWN**. |
| **C9 — Chuyển người / giới hạn thẩm quyền (8%)** | Bot có biết khi nào cần người thật; hotline có thực sự chuyển phiên không? | Yêu cầu gặp người, hotline/giờ đã xác minh và log/capability nếu tuyên bố đã chuyển. | TC-03A có hướng dẫn xem tài liệu/gọi hotline, chưa chứng minh live handoff. Ví dụ **3/5**; CF `UNKNOWN`. |
| **C10 — Bước tiếp theo trong hành trình (5%)** | Bước kế tiếp có phù hợp giai đoạn và giúp khách tự quyết an toàn không? | Chỉ dẫn cụ thể, điều kiện, mức áp lực mua và phần journey đã thử. | Chưa thử checkout/hoàn tất journey. **UNKNOWN**. |

Giải thích đầy đủ và anchor 0–5 riêng từng tiêu chí nằm trong sheet `Rubric V2` và tài liệu Rubric V2. Điểm ví dụ trên là điểm đề xuất nội bộ áp từ summary Batch 01, không phải kết luận mới từ raw transcript.

## 3. Chọn điểm 0–5

- **5:** đáp ứng đầy đủ mục tiêu tiêu chí trong toàn bộ phạm vi thử, đúng nguồn và hữu ích.
- **4:** tốt; chỉ thiếu chi tiết nhỏ, không đổi ý nghĩa.
- **3:** phần cốt lõi đạt nhưng có thiếu sót đáng kể.
- **2:** mới đạt một phần hoặc thiếu nhiều yếu tố quan trọng.
- **1:** phần lớn không đạt/dễ gây hiểu nhầm.
- **0:** evidence cho thấy thất bại hoàn toàn trong tình huống đã thử. Không tự động là Critical Fail.

Hãy dùng anchor riêng của tiêu chí để phân biệt mức điểm. Nếu nguồn chuẩn/phiên bản, output hoặc capability không đủ thì chọn `UNKNOWN`, không hạ điểm thành 0. Nếu nhiều case cho kết quả khác nhau, ghi case tốt/xấu và mức ảnh hưởng; không lấy trung bình để xóa một trường hợp nghiêm trọng. Chỉ gộp thành một điểm mỗi tiêu chí khi đã nêu rõ cách tổng hợp.

## 4. Đọc công thức workbook

- **Điểm tổng hợp /5:** trung bình có trọng số của các hàng `SCORED`. Hàng `UNKNOWN`, `N/A` và trống không trở thành điểm 0.
- **Evidence Coverage:** tổng trọng số `SCORED` chia cho tổng trọng số áp dụng (tất cả trừ `N/A`). Coverage thấp nghĩa là phần lớn phạm vi chưa chấm; không phải độ chính xác hay độ tin cậy.
- **SCORED / UNKNOWN / N/A / BLANK:** số hàng ở mỗi trạng thái. Một status trống vẫn ở mẫu số coverage và xuất hiện riêng để người chấm thấy việc còn thiếu.
- **Critical Fail:** bất kỳ `YES` nào sẽ hiện `CRITICAL FAIL — REVIEW REQUIRED`, bất kể điểm trung bình. `NO` chỉ cho biết không thấy trigger trong phạm vi có locator. `UNKNOWN` hoặc trạng thái trống nghĩa là chưa đánh giá đủ.
- **Kiểm tra nhập liệu:** cảnh báo status không hợp lệ, điểm ngoài 0–5, điểm đặt trên hàng không `SCORED`, SCORED thiếu test/locator, N/A thiếu lý do hoặc CF thiếu evidence.
- **Không có cutoff:** workbook không gắn nhãn chatbot đạt/không đạt. Cần tiêu chí được chủ sản phẩm duyệt và calibration phù hợp trước khi dùng cho quyết định nghiệm thu.

Với ví dụ Batch 01, phép tính hiển thị là:

`(12%×2 + 12%×4 + 10%×3 + 10%×2 + 15%×4 + 8%×3) / 67% = 3,0746/5`

Có 6 tiêu chí `SCORED`, 4 `UNKNOWN`, 0 `N/A`; coverage là 67%. 33% trọng số còn lại chưa có điểm. Kết quả vẫn `PROVISIONAL`, không xác nhận lỗi IT và không đại diện toàn bộ chatbot AIMICA.

## 5. Critical Fail — dùng thận trọng

CF là cờ rà soát sự kiện nghiêm trọng, độc lập với điểm. Chọn `YES` khi có locator trực tiếp và trigger đúng như Rubric V2, ví dụ: khuyến khích gửi dữ liệu nhạy cảm trái kênh đã xác nhận; cam kết chi trả trái nguồn; bịa căn cứ trọng yếu; chặn/giả vờ chuyển người thật. Nếu chưa có nguồn/policy hoặc chưa test, chọn `UNKNOWN`. Không đánh `NO` chỉ vì không nhớ đã gặp lỗi.

## 6. Cách trình bày cho sếp

Nói theo thứ tự: **phạm vi → điểm và coverage → hành vi có bằng chứng → điều còn UNKNOWN → quyết định cần có**. Mẫu câu:

> “Bộ hiện tại có ba tình huống kiểm thử, tập trung vào khai thác nhu cầu và giải thích quyền lợi/điều kiện. Trên sáu tiêu chí đủ bằng chứng để chấm, điểm mô tả là 3,07/5; Evidence Coverage 67%, còn bốn tiêu chí UNKNOWN. Summary cho thấy bot nêu đúng một số dữ kiện gói và giữ hai điều kiện loại trừ được hỏi; TC-01 còn gợi ý trước khi làm rõ đầy đủ nhu cầu. Đây là kết quả PROVISIONAL trên phạm vi nhỏ, chưa phải nghiệm thu, chưa xác nhận lỗi IT và không kết luận về privacy, backend hay live handoff.”

Không gọi 3,07 là điểm tổng thể/chứng nhận chất lượng; không nói 67% là tỷ lệ trả lời đúng; không đưa UNKNOWN thành “đạt” hoặc “không đạt”.

## 7. Ranh giới hiện tại

Workbook dùng ba tình huống đã chạy để minh họa; không có kiểm thử mới được thực hiện trong nhiệm vụ hoàn thiện sản phẩm này. B2-01…B2-07 vẫn `NOT RUN`; file không cấp quyền kiểm thử, liên hệ AIMICA hay chia sẻ evidence. Không ghi transcript/ảnh raw hoặc dữ liệu khách vào workbook.
