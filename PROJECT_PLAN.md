# Kế hoạch hai track

Mọi mốc sau Phase 0 dưới đây là **đề xuất chưa được duyệt thực hiện**. Không có cam kết tiến độ, chi phí hay kết quả với AIMICA.

| Mốc | Track A — AIMICA và chuẩn bị tư vấn | Track B — học và phương pháp dùng lại | Điều kiện chuyển mốc |
|---|---|---|---|
| Phase 0 — hiện tại | Bộ câu hỏi discovery nháp; xác định ranh giới quyền hạn | Anchor, hướng dẫn AI, mẫu Wheel Check, daily summary | Đủ bộ tài liệu và kiểm chứng local; dừng tại đây |
| Phase 1 — đề xuất | TJ rà soát câu hỏi, xác định đầu mối, mục tiêu và phạm vi khảo sát | TJ thực hành tách sự thật/giả định; ghi cách hỏi và nguồn bằng chứng | TJ cho phép bắt đầu; phạm vi và cách thu thập dữ liệu được ghi rõ trước khảo sát |
| Phase 2 — đề xuất | Đánh giá chatbot trên kênh, dữ liệu và cách kiểm tra được phép; nêu giới hạn mẫu | Xây và hiệu chỉnh rubric, cách lưu bằng chứng, phân biệt lỗi và điều chưa biết | Có quyền kiểm tra cụ thể, tiêu chí và bộ mẫu phù hợp; không suy ra quyền production |
| Phase 3 — đề xuất | Chuyển phát hiện thành yêu cầu IT, tiêu chí nghiệm thu và đề xuất phạm vi hợp đồng | Chuẩn hóa discovery, đánh giá, yêu cầu IT, ước lượng và bàn giao | TJ duyệt nội bộ; chỉ ghi khách duyệt khi có xác nhận thật |

## Cách triển khai khi được mở phạm vi

Mỗi mốc dùng vòng nhỏ: câu hỏi kinh doanh → bằng chứng → nhận định có giới hạn → quyết định → kiểm tra kết quả. Chỉ tạo tài liệu bổ sung khi có đầu ra cụ thể cần lưu. Chưa đặt KPI tăng trưởng, ROI hoặc điểm số chatbot khi thiếu dữ liệu nền.

Đánh giá để chuẩn bị hợp đồng cần làm rõ: người quyết định, vấn đề đáng giải quyết, ranh giới dịch vụ, sản phẩm bàn giao, dữ liệu/quyền truy cập, trách nhiệm hai bên, cách nghiệm thu và cách xử lý thay đổi. Đây là nội dung cần xác minh, không phải điều khoản đã thống nhất.

## Skill dự kiến

Inventory và đường dẫn thực tế ở PROJECT_STATUS.md. `execution-contract` cho mục tiêu và phép kiểm tra; `risk-adaptive-audit` cho độ tin cậy bằng chứng; `git-state-recovery` cho trạng thái repo. Các mốc sau có thể dùng `rubric-engineering` để thiết kế thang đánh giá, `decision-advisor` cho quyết định có ý nghĩa, `technicaldebug` khi thật sự có lỗi kỹ thuật. `po-decision-bridge` chỉ dùng khi TJ gọi rõ. Không phụ thuộc `local-orchestrator-cli` đang chưa tìm thấy.

## Nhiệm vụ kế tiếp duy nhất

`AIM-01` được mô tả trong TASK_BOARD.md. Các mốc trên là lộ trình, không phải danh sách việc đang được phép tự chạy.
