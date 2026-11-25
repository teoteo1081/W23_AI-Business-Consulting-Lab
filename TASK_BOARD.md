# Task Board

Cập nhật: 2026-11-25. Trạng thái: DONE = có kết quả và bằng chứng; WAITING_AUTHORIZATION = chưa được phép bắt đầu; IN_PROGRESS = đã được duyệt và có owner; BLOCKED = có trở ngại thực tế được ghi rõ.

| ID | Nhiệm vụ | Owner | Trạng thái | Bằng chứng / điều kiện |
|---|---|---|---|---|
| P0-01 | Kiểm tra thư mục, tạo Git độc lập | Codex | DONE | E01–E02 trong PROJECT_STATUS.md |
| P0-02 | Tạo bộ tài liệu tối thiểu và inventory skill | Codex | DONE | 11 file ở root; E03–E04 |
| P0-03 | Kiểm chứng và bàn giao Phase 0 | Codex | DONE | E05–E06; HANDOFF.md |
| AIM-01 | TJ rà soát câu hỏi discovery và chốt phạm vi khảo sát AIMICA cùng AI | TJ; AI hỗ trợ sau khi được phép | WAITING_AUTHORIZATION | TJ chưa cho phép Phase 1; chưa có xác nhận khách |

## AIM-01 — nhiệm vụ AIMICA kế tiếp duy nhất

- **Đầu vào:** AIMICA_DISCOVERY.md, LAB_ANCHOR.md và chỉ đạo mới của TJ cho phép Phase 1.
- **Cách làm sau khi được phép:** trao đổi nội bộ với TJ để chọn mục tiêu kinh doanh cần hỏi, đầu mối xác minh, kênh/dữ liệu được phép tiếp cận và các điểm chưa biết. Không tự gửi câu hỏi cho khách.
- **Đầu ra:** cập nhật AIMICA_DISCOVERY.md với câu trả lời có nguồn hoặc nhãn chưa xác minh; ghi phạm vi TJ duyệt và phần cần khách xác nhận.
- **Hoàn thành khi:** TJ xác nhận phạm vi khảo sát nội bộ; quyền truy cập hoặc xác nhận của khách còn thiếu được ghi đúng là thiếu. Nếu chưa chốt, giữ nhiệm vụ chưa hoàn tất.
- **Không bao gồm:** khảo sát hệ thống thật, kiểm thử chatbot, liên hệ khách, đề xuất hợp đồng như đã được chấp thuận.

Không tạo nhiệm vụ AIMICA kế tiếp thứ hai trước khi TJ đổi phạm vi. Khi nhận việc, kiểm tra owner và thay đổi hiện có rồi cập nhật trạng thái; sau khi xong ghi bằng chứng và handoff.
