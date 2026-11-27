# Hướng dẫn chung cho mọi AI

## Quyền hiện hành — quyết định Business Owner, 2026-11-26

TJ xác nhận W23 **PUBLIC có chủ đích** (D1), giữ nguyên lịch sử (D2), và cho Claude/Codex/AGY đọc những tài liệu đã được xác nhận đủ điều kiện công khai (D3). Không coi email của chủ repo hoặc tên `private/` tự động là lỗi/phân loại bảo mật; rà soát theo nội dung thật và quyền công bố. Batch 01 vẫn PROVISIONAL; AIM-04 chỉ là research/planning; không chạy Batch 02 khi chưa được duyệt. Hiện được phép chuẩn bị Business Discovery Brief và handoff; không tự liên hệ khách hoặc gửi tài liệu ra ngoài. Không commit/push nếu chưa có chỉ đạo riêng; không rewrite history, force push, thay đổi W24. Đọc cập nhật đầu `CHECKPOINT_LOG.md`, `PROJECT_STATUS.md` và `HANDOFF.md`; các snapshot cũ là lịch sử. Quyền đọc tài liệu không mặc nhiên bao gồm quyền tái xuất bản hoặc chuyển raw evidence của bên thứ ba.

Áp dụng cho Codex, Claude, AGY và AI khác làm việc trong repository này. Chủ sở hữu và người duyệt phạm vi: TJ.

## Bắt đầu phiên làm việc

- Đọc LAB_ANCHOR.md, PROJECT_STATUS.md, TASK_BOARD.md và HANDOFF.md trước khi chọn việc.
- Kiểm tra đường dẫn và Git: `git rev-parse --show-toplevel`, `git status --short --branch`, `git worktree list --porcelain`, `git remote -v`. Kiểm tra refs/commit nếu có. Không coi checkout đang mở là bản mới nhất khi có worktree hoặc nhánh khác.
- Đọc hướng dẫn áp dụng ở thư mục cha và thư mục con liên quan. Nếu thực tế khác tài liệu, ghi chênh lệch; không tự sửa lịch sử để khớp báo cáo.
- Quyền hiện tại: AIM-01 đã đóng; Batch 01 đã chạy 3 ca và vẫn PROVISIONAL; Batch 02 chưa được duyệt. Brief Business Discovery đã chuẩn bị; chỉ TJ quyết định có tiến hành buổi discovery với AIMICA. Không tự chạy Zalo hoặc liên hệ khách. Xem mục hiện hành và D-008 trong PROJECT_STATUS.md.

## Trước khi sửa

- Ghi ngắn mục tiêu, file được sửa, bằng chứng hoàn thành và phần ngoài phạm vi.
- Đọc nội dung hiện tại và diff. Không ghi đè, reset, clean, stash hoặc xóa thay đổi của người/AI khác. Khi sửa cùng vùng nội dung, phối hợp với TJ trước; có thể tiếp tục phần độc lập.
- Mỗi việc có ID, owner, trạng thái và bằng chứng trong TASK_BOARD.md. Không tự nhận việc đang thuộc người/AI khác. Không tự chạy nhiều agent hoặc công việc nền.
- Quyết định triển khai nhỏ trong phạm vi đã duyệt do AI xử lý; thay đổi mục tiêu, quyền truy cập, chi phí hoặc cam kết với khách phải do TJ quyết định.

## Trong khi làm

- Phân biệt: quan sát có nguồn / giả định / câu hỏi chưa xác minh / đề xuất / quyết định được duyệt. Quyết định phải có người duyệt, ngày và nội dung; không suy ra khách đã duyệt từ tài liệu nội bộ.
- Chỉ ghi trong project; không lưu thông tin định danh khách, mật khẩu, token, hội thoại thật hoặc tài liệu hợp đồng chưa ẩn danh vào tài liệu theo dõi Git. `.gitignore` chỉ hỗ trợ, không tự phát hiện hết bí mật.
- Không xây chatbot, tự động kiểm thử Zalo, cài dependencies không cần thiết, gọi API trả phí, đụng production, tự liên hệ khách, tự commit/push hoặc tạo lịch chạy nền.
- Không cài hay kích hoạt toàn bộ skill. Kiểm tra skill thật trước khi dùng, đọc hướng dẫn phù hợp. Inventory trong PROJECT_STATUS.md chỉ phản ánh máy và thời điểm đã kiểm tra, không bảo đảm máy khác có skill. Thiếu skill thì ghi rõ, không tạo bản giả.

## Kết thúc mỗi nhiệm vụ

- Kiểm tra lại kết quả thực tế; nêu giới hạn của phép kiểm tra. Không gọi tài liệu là sản phẩm đã triển khai.
- Cập nhật TASK_BOARD.md, PROJECT_STATUS.md và HANDOFF.md. Khi cần tổng kết ngày, điền mẫu DAILY_SUMMARY.md bằng bằng chứng thật; không tự bật lịch.
- Ghi file đã sửa, kiểm tra đã chạy, việc chưa làm, quyết định còn cần và một bước tiếp theo phù hợp phạm vi. Không tăng số nhiệm vụ AIMICA kế tiếp khi chưa có chỉ đạo mới.
- Không commit/push nếu TJ chưa yêu cầu. Báo rõ file còn untracked/modified và giới hạn lưu trữ đó.
