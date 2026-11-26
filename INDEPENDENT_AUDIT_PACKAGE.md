# Independent Audit — W23 / AIMICA

Ngày: 2026-11-26. Người chuẩn bị: Codex. Trạng thái: tài liệu local đã chuẩn bị; **chưa được duyệt chia sẻ ngoài máy**. Đây là chỉ dẫn kiểm tra, không phải chatbot đã triển khai, yêu cầu khách duyệt hoặc báo cáo audit độc lập mới.

## Cách đọc và thẩm quyền

Đọc CHECKPOINT_LOG.md → AIM-03_SECURITY_AND_GITHUB_READINESS_AUDIT.md → PROJECT_STATUS.md → TASK_BOARD.md → HANDOFF.md. Sau đó đọc LAB_ANCHOR.md, AGENTS.md, PROJECT_PLAN.md, các tài liệu discovery, QA và AIM-04 theo bảng dưới.

Chỉ đạo mới nhất của TJ trong hội thoại có ưu tiên hơn snapshot tài liệu. Những phần cũ ghi AIM-02 chưa bắt đầu là lịch sử; Batch 01 đã được ghi nhận PROVISIONAL. Chưa được chạy Batch 02. Không tự liên hệ khách, chạy Zalo, truy cập production, gọi API trả phí hoặc thay đổi W24.

| Nhóm | File / evidence | Cách sử dụng và giới hạn |
|---|---|---|
| Governance | README.md, LAB_ANCHOR.md, AGENTS.md, PROJECT_PLAN.md, PROJECT_STATUS.md, TASK_BOARD.md, HANDOFF.md, CHECKPOINT_LOG.md | Phạm vi, authority, trạng thái và Git; đọc cập nhật mới trước snapshot |
| Requirements/discovery | HUMAN_REVIEW.md, INDUSTRY_BRIEF.md, DISCOVERY_QUESTIONS.md, INITIAL_USE_CASES.md | Câu hỏi và giả thuyết; chưa phải requirements khách duyệt. AIMICA_DISCOVERY.md là bản nháp lịch sử |
| QA design/results | AIMICA_RESEARCH_REVIEW.md, AIM-02_HUMAN_REVIEW.md | Rubric nháp và summary; phần pre-QA còn mâu thuẫn về PDF/quyền, không dùng làm trạng thái hiện hành |
| Roadmap | AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md | Đầu ra AGY được giữ nguyên; B2-01..B2-07 là đề xuất chưa chạy. Đọc các phát hiện CONS bên dưới trước khi sử dụng |
| Source evidence LOCAL ONLY | private/aimica/AIM-02/evidence_index.csv; QA_HANDOFF_SUMMARY.md; AIM-02_INDEPENDENT_REVIEW_CODEX_2026-11-25.md | Đã kiểm tra tồn tại, đối soát trạng thái, tham chiếu và hash liên quan; không có trong commit Git. Cần bản chia sẻ được duyệt |
| Primary evidence LOCAL ONLY | raw/batch01_transcript.json; redacted/TC-01.png, TC-03A.png, TC-03B.png; reference/PDF và ảnh trang, tất cả dưới private/aimica/AIM-02/ | Không tự upload/force-add. Nhãn redacted không chứng minh đủ điều kiện chia sẻ |
| Ground truth | URL sản phẩm/nguồn tại research review và PDF AAA được báo cáo 22 trang | Prior review đã kiểm sáu trang liên quan và báo hash khớp nguồn công khai. Audit hợp nhất chỉ tái kiểm hash, không xác nhận mới nội dung PDF, tính áp dụng hợp đồng hoặc pháp luật |

## Traceability: yêu cầu → bằng chứng → finding → roadmap

Tất cả mục tiêu hành vi sau là đề xuất nghiên cứu nội bộ, chưa là acceptance requirements của AIMICA.

| Mục tiêu / câu hỏi gốc | Bằng chứng hiện có | Kết luận được phép giữ | Đề xuất AIM-04 / phụ thuộc |
|---|---|---|---|
| Q04/Q13: discovery hữu ích | TC-01 | PARTIAL theo rubric nháp, PASS số liệu đã kiểm; không xác nhận lỗi nghiệp vụ | B2-04; SOP discovery, reset hợp lệ và nguồn cho nhóm sức khỏe |
| Q05/Q13: phạm vi và ngoại lệ | TC-03A; web và prior review PDF Điều 2/tr.6, ghi chú tr.8 | PASS gói chuẩn web; PARTIAL độ đầy đủ theo expected kết hợp PDF; chưa biết có bán mở rộng | B2-05; Business Owner chốt phạm vi |
| Q05/Q13: loại trừ có điều kiện | TC-03B; prior review Điều 9.2–9.3/tr.7 | PASS giới hạn hai điều kiện đã hỏi; không suy ra quyết định bồi thường thực | B2-06; Claims SME xác nhận wording |
| Q12: an toàn dữ liệu | Chính sách công khai được báo cáo và cảnh báo pilot; chưa có test TC-08 | Chưa kiểm chứng hành vi từ chối hoặc lưu dữ liệu thực tế | B2-01; đối chiếu phạm vi web/app với pilot, chỉ dùng ý định/placeholder |
| Q14: chuyển người | Batch 01 mới thấy chỉ dẫn liên hệ | Chưa chứng minh live takeover, warm handoff hoặc không phải kể lại | B2-02; IT xác nhận routing không tạo ticket thật |
| Q04/Q13: chống hứa vượt nguồn | Chưa chạy TC-04 | UNKNOWN | B2-03; xác minh điều khoản/hạn mức cụ thể trước chấm |
| Q05/Q14: thủ tục bồi thường | Tóm tắt web/PDF trong báo cáo; chưa chạy TC-07 | UNKNOWN về hành vi bot | B2-07; xác minh mốc và điều kiện tính thời hạn, nguồn trang cụ thể |

## Review AIM-04: nội dung cần chốt trước dùng rubric

Codex đã đọc toàn bộ file bàn giao và ba diff điều phối; tài liệu AGY được giữ nguyên. Hash nhận bàn giao: `58ef77a3ec307f61b23cdbb346377aab4d7475e74a179ab5bca920db4882c123` (SHA-256). Review rubric có tiếp xúc trước với nội dung; không phải blind calibration. Trạng thái thiết kế: REVIEWED; chưa chạy grader/calibration hoặc live QA.

| ID | Finding / nơi tham chiếu | Khuyến nghị để Business Owner quyết định |
|---|---|---|
| CONS-01 | Mục 3 dùng >90% intent accuracy; mục 6.3 có mục tiêu 100% context retention, không có nguồn/mẫu/ngưỡng khách duyệt | Ghi là mục tiêu nháp nếu muốn giữ; không áp dụng như industry standard hoặc acceptance gate |
| CONS-02 | Mục 4 chủ yếu là URL grounding redirect, không có direct canonical URL/title/date/đoạn hỗ trợ; benchmark có nhận định về tỷ lệ bỏ cuộc chưa có dữ liệu so sánh | Chuẩn hóa source register, phân biệt vendor recommendation và kết quả định lượng; chưa xác minh lại trang nguồn trong phiên này |
| CONS-03 | B2-01 lấy chính sách web/app làm căn cứ pilot; câu trả lời từ chối không chứng minh hệ thống không lưu dữ liệu | Chốt áp dụng chính sách cho đúng hệ thống; chỉ chấm hành vi quan sát được, tách kiểm tra backend nếu có quyền riêng. Nhắc pháp luật trong tài liệu không phải xác nhận tuân thủ |
| CONS-04 | B2-03/B2-07 gọi ground truth VERIFIED nhưng một số điều khoản, điều kiện thời hạn và cơ sở quyền lợi chưa được kiểm lại ở audit này | Yêu cầu citation trang/đoạn, phiên bản và nghiệp vụ xác nhận trước score; không mặc định STBH bằng hạn mức mọi khoản chi y tế |
| CONS-05 | B2-06 cho PARTIAL khi nhánh 1 hứa chắc chắn chi trả, trong khi mục tiêu chính cấm hứa quá mức | Đề xuất phân loại lỗi hứa vượt nguồn thành FAIL khi tiêu chí được duyệt; giữ riêng phần giải thích hữu ích. Không thay kết quả Batch 01 |
| CONS-06 | B2-07 PARTIAL cho trường hợp giấy tờ đúng nhưng thời hạn không đạt; FAIL lại bao gồm sai thời hạn; thiếu nhánh sót một nhóm giấy tờ | Làm các nhánh loại trừ nhau; quy định critical error và UNKNOWN khi nguồn chưa đủ |
| CONS-07 | Handoff framework yêu cầu warm handoff/no-repeat/ngoài giờ trong khi cơ chế thực tế chưa xác minh | Đánh giá riêng giới thiệu hotline và chuyển phiên thật; thiếu capability/nguồn thì UNKNOWN hoặc NOT APPLICABLE có lý do, không tự gán lỗi |
| CONS-08 | Công thức xếp hạng dùng business value × risk / effort nhưng bảng chỉ có nhãn định tính; thứ tự khác ưu tiên ba thiết kế Codex trước đó | Đây là ưu tiên mới do AGY đề xuất, không phải phép tính hoặc quyết định TJ. TJ chọn batch; không tự tăng batch/task hoặc chạy Batch 03 |
| CONS-09 | Governance/root research còn trạng thái pre-QA; Decision Log chưa có bản phê duyệt Batch 01 đầy đủ | Bản hợp nhất ghi nhận báo cáo đã có, không dựng lại consent hoặc khách sign-off. Bổ sung bản tóm tắt approval được phép lưu khi TJ cung cấp/chốt |

## Người audit độc lập cần trả lời

1. Kết luận có truy tới đúng case, nguồn và phiên bản không? Phân biệt báo cáo trước với bằng chứng đã tự kiểm.
2. Giữ PROVISIONAL/UNKNOWN, các hành vi hữu ích và Confirmed IT Defects = 0; chỉ đổi khi có bằng chứng và thẩm quyền.
3. Phát hiện logic/rubric nào có thể kết luận từ tài liệu, điểm nào cần evidence hoặc Business Owner/IT?
4. Source register và quyền chia sẻ đã đủ chưa? Không lấy permission kiểm thử làm permission upload.
5. Đề xuất một checkpoint tiếp theo trong phạm vi TJ duyệt, không tự kích hoạt roadmap.

Đầu ra audit nên ghi finding ID, mức ảnh hưởng, locator/source version, quan sát so với giả thuyết, giới hạn và điều kiện đóng. Không chép thông tin nhạy cảm.

## Gói chia sẻ chưa đủ điều kiện phát hành

Local document review đã có tài liệu cần thiết. Kiểm chứng độc lập QA từ GitHub vẫn BLOCKED vì primary evidence và prior independent review chỉ local; chưa có allowlist, quyền chia sẻ/retention và visibility đã xác minh. Không tạo bản transcript thay thế rồi gọi đó là evidence gốc. Khi có quyền, tạo bản chia sẻ có traceability tới nguồn local và bản redaction được kiểm duyệt. File inventory/hash không thay thế nội dung nguồn.
