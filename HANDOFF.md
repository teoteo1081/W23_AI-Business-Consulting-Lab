# Handoff — kết thúc Phase 0

Cập nhật: 2026-11-25 (Asia/Saigon). Thực hiện: Codex. Chủ sở hữu: TJ.

## AI tiếp theo cần hiểu

Đây là Lab của TJ để học tư vấn AI và xây phương pháp dùng lại, không phải source code AIMICA. TJ chỉ cho phép khởi tạo và lập kế hoạch tối thiểu. **Phase 0 đã hoàn tất; dừng tại đây, không tự làm Phase 1.**

Đọc README.md → LAB_ANCHOR.md → AGENTS.md → PROJECT_STATUS.md → TASK_BOARD.md. Không cần chat cũ để hiểu mục tiêu và quyền hạn hiện tại. Nếu có chỉ đạo mới, ghi nhận căn cứ duyệt vào PROJECT_STATUS.md trước khi đổi trạng thái.

## Đã bàn giao

- 11 file tối thiểu: 10 tài liệu Markdown và .gitignore; kế hoạch hai track A/B, discovery nháp và các mẫu thực hành.
- Repo local độc lập, nhánh main chưa có commit; không remote, không stage/push. Các file đều untracked; chưa có backup được xác minh.
- Inventory: 7 skill có SKILL.md thật; local-orchestrator-cli chưa tìm thấy trong vùng đã kiểm tra. Không cài hay tạo skill.
- Kiểm tra thực tế và giới hạn được lưu tại E01–E06 trong PROJECT_STATUS.md. Kiểm tra do cùng AI thực hiện, không tuyên bố có reviewer độc lập.

## Chưa thực hiện

Chưa đọc/khảo sát website AIMICA, chưa biết có chatbot hoặc Zalo hay không, chưa kiểm thử, chưa thu thập dữ liệu khách, chưa liên hệ AIMICA, chưa viết yêu cầu IT cụ thể, chưa đề xuất hợp đồng đã được duyệt. Không có sản phẩm chatbot hay kết quả kinh doanh đã được chứng minh.

## Một nhiệm vụ AIMICA tiếp theo

**AIM-01 — TJ rà soát bộ câu hỏi discovery và chốt phạm vi khảo sát cùng AI.** Trạng thái WAITING_AUTHORIZATION. Xem đầu vào, đầu ra và tiêu chí hoàn thành duy nhất tại TASK_BOARD.md. Không thực hiện trước chỉ đạo cho phép Phase 1; không tự gửi câu hỏi cho khách.

## Khi được TJ yêu cầu tiếp tục

1. Kiểm tra đúng root và trạng thái Git thực tế; chưa có HEAD là bình thường ở checkpoint này. Nếu đã có commit/nhánh/worktree mới, tái dựng trạng thái trước khi kết luận.
2. Đọc lại file, diff và owner; bảo toàn mọi thay đổi của người/AI khác. Không reset/clean hoặc ghi đè.
3. Chỉ nhận phần nằm trong phạm vi mới TJ duyệt, ghi owner và kết quả cần kiểm tra.
4. Sau nhiệm vụ, cập nhật task board, status và handoff; dùng mẫu daily summary khi cần. Không tự commit/push hay chạy nền.

Không có tác vụ đang chạy cần tiếp quản. Không cần quyết định bổ sung để đóng Phase 0. Quyết định cho bước sau thuộc TJ: có mở Phase 1 với AIM-01 hay chưa.
