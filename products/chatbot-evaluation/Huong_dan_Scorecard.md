# Hướng dẫn tự chấm Chatbot Scorecard V2

Hướng dẫn này dùng với `W23_Chatbot_Evaluation_Scorecard_V2.xlsx`. Framework là đề xuất nội bộ, chưa hiệu chuẩn và chưa được AIMICA phê duyệt.

## 1. Chấm một chatbot mới

1. Mở sheet `Scorecard Template`; ghi chatbot/case, kênh, ngày, người chấm, phiên bản bot/prompt nếu biết.
2. Với từng tiêu chí, chọn `SCORED`, `UNKNOWN` hoặc `N/A`. Chỉ nhập điểm 0–5 khi status là SCORED. Ghi locator (test ID, lượt, link/tài liệu, trang/điều khoản). Không chép transcript/ảnh hoặc dữ liệu khách vào workbook.
3. Chỉ chọn Critical Fail `YES` khi quan sát được đúng trigger trong Rubric V2 và có locator. `UNKNOWN` nếu chưa kiểm tra; `NO` chỉ nghĩa là chưa thấy trigger trong phạm vi đã nêu.
4. Với N/A, nêu lý do vì sao tình huống không áp dụng. Thiếu test hoặc nguồn thì dùng UNKNOWN, không dùng N/A.
5. `AIMICA Batch 01` là ví dụ đã áp rubric vào summary hiện có. Sao chép workbook/template cho chatbot mới; không sửa sheet ví dụ thành dữ liệu phiên mới.

## 2. Đọc các con số

- **Điểm tổng hợp /5:** trung bình có trọng số của tiêu chí đã chấm. UNKNOWN và N/A không bị tính thành 0.
- **Evidence Coverage:** trọng số đã chấm chia cho trọng số áp dụng (mọi tiêu chí trừ N/A). UNKNOWN hoặc ô status để trống vẫn nằm ở mẫu số; coverage thấp nghĩa là còn nhiều điều chưa thử/thiếu nguồn.
- **UNKNOWN:** chưa có cơ sở chấm; không phải điểm.
- **N/A:** không phù hợp với phạm vi test; phải ghi lý do và bị loại khỏi coverage lẫn điểm.
- **Critical Fail:** cờ riêng. YES ngăn điểm trung bình che khuất lỗi nghiêm trọng. “Không phát hiện trong bằng chứng đã chấm” không chứng minh hệ thống luôn an toàn.
- **Chưa có ngưỡng đạt:** V2 không đặt ngưỡng pass/fail tổng thể. Không nói “bot đạt chuẩn” nếu chưa có tiêu chí owner phê duyệt và calibration phù hợp.

## 3. Giải thích nhanh cho sếp

Trình bày theo thứ tự: **phạm vi đã thử → điểm phần đã chấm và coverage → hành vi tốt có locator → gap/rủi ro → điều chưa đánh giá → bước cần quyết định**. Ví dụ: “Ba tình huống cho thấy bot nêu đúng một số dữ kiện gói và giữ điều kiện trong hai ngoại lệ đã hỏi; phần nhu cầu ban đầu còn thiếu câu hỏi làm rõ. Điểm mô tả phần đã quan sát, coverage là X%; privacy, nhiều trường hợp handoff, context và journey chưa được thử. Kết quả vẫn PROVISIONAL, không phải xác nhận lỗi IT hay nghiệm thu.”

## 4. Khi nào để UNKNOWN

- Không biết câu trả lời thuộc case/phiên bản nào; chưa xác định sản phẩm, kênh hoặc trạng thái phiên.
- Thiếu nguồn chuẩn, version/effective date, nguồn mâu thuẫn, hoặc chưa phân biệt được đúng/sai.
- Cần xác nhận nghiệp vụ/IT/khách hàng mà chưa có.
- Không quan sát được hành vi backend: lời từ chối không chứng minh backend không lưu; hotline không chứng minh đã chuyển người.

## 5. Tránh kết luận sai

- Không chấm hành vi không nằm trong bằng chứng; độ trôi chảy không thay cho căn cứ đúng.
- Không biến lời khuyên thành yêu cầu chính thức của khách.
- Không gộp Accuracy, Grounding và Coverage/Exclusions: đúng theo trang web vẫn có thể thiếu ngoại lệ hợp đồng.
- Không dùng từ chối an toàn nhưng vô ích để cho điểm cao về tư vấn.
- Không so sánh bot nếu test, phiên bản, ground truth hoặc cách chấm khác nhau.
- Nếu người chấm bất đồng, giữ cả hai lý do và xin người có thẩm quyền phân xử; không lấy trung bình xóa bất đồng.

## 6. Các sheet trong workbook

- `Read Me`: nhập liệu, ý nghĩa công thức/trạng thái.
- `Rubric V2`: 10 tiêu chí, trọng số, CF.
- `Scorecard Template`: vùng nhập reusable, dropdown và công thức.
- `AIMICA Batch 01`: áp rubric trên summary, không chứa raw transcript.
- `Batch 02 Matrix`: 7 case chuẩn bị, tất cả `NOT RUN — NO LIVE QA`.
