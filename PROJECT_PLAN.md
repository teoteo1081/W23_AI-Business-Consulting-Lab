# Kế hoạch hai track

## Cập nhật hiện hành — 2026-11-26

AIM-01 đã đóng; AIM-02 Batch 01 PROVISIONAL đã được ghi nhận, chưa nghiệm thu. AIM-04 đã nghiên cứu/lập kế hoạch B2-01..B2-07; chưa được chạy. Hiện chỉ hợp nhất hồ sơ và chuẩn bị Independent Audit theo chỉ đạo TJ, không mở Phase 2 mới hoặc Batch 03. Xem CHECKPOINT_LOG.md và các phụ thuộc/rubric cần chốt trong INDEPENDENT_AUDIT_PACKAGE.md. Security/sharing BLOCKED; không commit/push trước điều kiện duyệt. Phần kế hoạch AIM-01 dưới đây là snapshot lịch sử, không cấp quyền thực thi.

TJ đã đóng AIM-01 sau nghiên cứu công khai và review. Quyết định hiện hành: ưu tiên QA chatbot Zalo hiện hữu từ góc nhìn khách mua; Sales/CTV và KPI là hướng phụ, chưa chốt triển khai. AIM-02 chỉ được chuẩn bị, chưa bắt đầu. Phase 2–3 vẫn là **đề xuất chưa được duyệt thực hiện**. Không có cam kết tiến độ, chi phí hay kết quả với AIMICA.

| Mốc | Track A — AIMICA và chuẩn bị tư vấn | Track B — học và phương pháp dùng lại | Điều kiện chuyển mốc |
|---|---|---|---|
| Phase 0 — đã hoàn tất | Bộ câu hỏi discovery nháp; xác định ranh giới quyền hạn | Anchor, hướng dẫn AI, mẫu Wheel Check, daily summary | Checkpoint 83cd364; không viết lại bằng chứng cũ |
| Phase 1 — AIM-01 đã hoàn tất/review | Nghiên cứu công khai, ba nhóm người dùng, 15 câu hỏi, ba use case; TJ chọn QA hiện trạng làm trọng tâm | 5 bài học về business/AI và phân biệt bằng chứng/giả thuyết | AIM-02 đã lập nhưng chờ lệnh bắt đầu/phạm vi cụ thể; chưa có khách xác nhận |
| Phase 2 — đề xuất | Đánh giá chatbot trên kênh, dữ liệu và cách kiểm tra được phép; nêu giới hạn mẫu | Xây và hiệu chỉnh rubric, cách lưu bằng chứng, phân biệt lỗi và điều chưa biết | Có quyền kiểm tra cụ thể, tiêu chí và bộ mẫu phù hợp; không suy ra quyền production |
| Phase 3 — đề xuất | Chuyển phát hiện thành yêu cầu IT, tiêu chí nghiệm thu và đề xuất phạm vi hợp đồng | Chuẩn hóa discovery, đánh giá, yêu cầu IT, ước lượng và bàn giao | TJ duyệt nội bộ; chỉ ghi khách duyệt khi có xác nhận thật |

## Cách triển khai khi được mở phạm vi

Mỗi mốc dùng vòng nhỏ: câu hỏi kinh doanh → bằng chứng → nhận định có giới hạn → quyết định → kiểm tra kết quả. Chỉ tạo tài liệu bổ sung khi có đầu ra cụ thể cần lưu. Chưa đặt KPI tăng trưởng, ROI hoặc điểm số chatbot khi thiếu dữ liệu nền.

Đánh giá để chuẩn bị hợp đồng cần làm rõ: người quyết định, vấn đề đáng giải quyết, ranh giới dịch vụ, sản phẩm bàn giao, dữ liệu/quyền truy cập, trách nhiệm hai bên, cách nghiệm thu và cách xử lý thay đổi. Đây là nội dung cần xác minh, không phải điều khoản đã thống nhất.

## Skill dự kiến

Inventory và đường dẫn thực tế ở PROJECT_STATUS.md. `execution-contract` cho mục tiêu và phép kiểm tra; `risk-adaptive-audit` cho độ tin cậy bằng chứng; `git-state-recovery` cho trạng thái repo. Các mốc sau có thể dùng `rubric-engineering` để thiết kế thang đánh giá, `decision-advisor` cho quyết định có ý nghĩa, `technicaldebug` khi thật sự có lỗi kỹ thuật. `po-decision-bridge` chỉ dùng khi TJ gọi rõ. Không phụ thuộc `local-orchestrator-cli` đang chưa tìm thấy.

## Nhiệm vụ kế tiếp duy nhất

`AIM-02 — Current Chatbot QA Evidence Collection` do AGY dự kiến thực hiện, chờ TJ chốt phạm vi và ra lệnh bắt đầu như TASK_BOARD.md/HANDOFF.md ghi nhận. Các mốc sau là lộ trình, không phải danh sách việc được phép tự chạy.
