# Task Board

Cập nhật: 2026-11-25. Trạng thái: DONE = có kết quả và bằng chứng; WAITING_AUTHORIZATION = chưa được phép bắt đầu; IN_PROGRESS = đã được duyệt và có owner; BLOCKED = có trở ngại thực tế được ghi rõ.

| ID | Nhiệm vụ | Owner | Trạng thái | Bằng chứng / điều kiện |
|---|---|---|---|---|
| P0-01 | Kiểm tra thư mục, tạo Git độc lập | Codex | DONE | E01–E02 trong PROJECT_STATUS.md |
| P0-02 | Tạo bộ tài liệu tối thiểu và inventory skill | Codex | DONE | 11 file ở root; E03–E04 |
| P0-03 | Kiểm chứng và bàn giao Phase 0 | Codex | DONE | E05–E06; HANDOFF.md |
| AIM-01 | Business discovery từ nguồn công khai theo phạm vi TJ mở ngày 2026-11-25 | Codex | DONE | INDUSTRY_BRIEF.md, DISCOVERY_QUESTIONS.md, INITIAL_USE_CASES.md; P1-E01–E04 trong PROJECT_STATUS.md. Chỉ hoàn tất desk research, chưa phỏng vấn hoặc khách duyệt |
| AIM-02 | Current Chatbot QA Evidence Collection — chatbot Zalo hiện hữu, góc nhìn khách mua bảo hiểm | AGY (Batch 01) / Codex (Independent Review) | IN_PROGRESS | Batch 01 (TC-01, TC-03A, TC-03B) đã chạy có kiểm soát ngày 2026-11-25 theo xác nhận quyền của TJ; Codex đã hoàn tất Independent Review; `evidence_index.csv` và `QA_HANDOFF_SUMMARY.md` đã đối soát ở trạng thái `PROVISIONAL` trong `private/aimica/AIM-02/`. Chưa nghiệm thu chính thức, chưa chạy Batch 02 |

## AIM-01 — phạm vi cập nhật được TJ duyệt

- **Căn cứ:** chỉ đạo “PHASE 1 — AIM-01: AIMICA BUSINESS DISCOVERY” ngày 2026-11-25 thay phạm vi nháp của nhiệm vụ, cho phép desk research và tài liệu, không yêu cầu giả định đã phỏng vấn hoặc khách duyệt.
- **Đầu vào:** các file Phase 0, commit 83cd364 và website công khai do TJ chỉ định.
- **Đầu ra hoàn tất:** brief có URL và nhãn chắc chắn; phân tích ba nhóm; 15 câu hỏi; ba hướng AI; 5 bài học; trạng thái và handoff đã cập nhật.
- **Giới hạn:** chưa có trả lời phỏng vấn, KPI nền, chính sách thù lao, quyền dữ liệu hoặc requirements phía khách. DONE không có nghĩa discovery với khách đã kết thúc.
- **Không bao gồm:** kiểm thử hệ thống/chatbot/Zalo, điều khiển Chrome, liên hệ khách, xây ứng dụng, Phase 2, API trả phí, commit/push.

## Bước AIMICA tiếp theo duy nhất — chờ TJ

**AIM-02 — chỉ chuẩn bị, không bắt đầu trong checkpoint này.** AIM-01 đã đóng sau khi TJ xem báo cáo; Human Review tại HUMAN_REVIEW.md, quyết định D-001 trong PROJECT_STATUS.md. Việc ghi task không cấp quyền kiểm thử.

- **Đầu vào cần chốt:** link/định danh OA đúng, tài khoản và quyền sử dụng; nhóm sản phẩm/tình huống và giới hạn lượt; cách kiểm tra được phép; tài liệu đối chiếu đúng phiên bản/người xác nhận; quyền lưu, người xem và thời hạn lưu bằng chứng.
- **AGY làm sau khi TJ ra lệnh bắt đầu:** kiểm tra repo/handoff, nhận owner, ghi thời điểm và đối tượng thực tế; thu chuỗi hỏi–đáp và ảnh theo tình huống khách mua trong phạm vi đã chốt. Không kiểm thử tự động Zalo khi chưa có quyền riêng rõ ràng.
- **Mục tiêu quan sát:** bot hiểu/hỏi lại nhu cầu ra sao, giải thích quyền lợi và giới hạn có căn cứ không, có lời hứa vượt nguồn không, và có chuyển người hữu ích không. Đây là mục tiêu thu bằng chứng, chưa phải rubric hay ngưỡng nghiệm thu khách duyệt.
- **Đầu ra:** chỉ mục evidence và bằng chứng đã ẩn danh theo HANDOFF.md; tách quan sát, giả thuyết và phần không đủ nguồn. Thiếu đáp án chuẩn thì ghi UNKNOWN, không tự kết luận đúng/sai nghiệp vụ.
- **Hoàn tất khi:** mỗi tình huống trong phạm vi được duyệt có chuỗi hội thoại/ngữ cảnh/thời điểm và nguồn ảnh đối chiếu được, hoặc lý do không thu được; dữ liệu được kiểm tra/ẩn danh; Board/Status/Handoff cập nhật để TJ review. Không suy ra bot đạt chất lượng tổng thể.
- **Ranh giới:** không mua/đóng phí/nộp hồ sơ thật, không dùng dữ liệu khách thật, không tự mở phạm vi, thay đổi bot hay yêu cầu sản phẩm; không commit/push nếu chưa có lệnh riêng. Không tự bắt đầu Phase 2 từ nhiệm vụ này.
