# Lab Anchor

## Cập nhật hiện hành — 2026-11-26

Theo chỉ đạo hợp nhất W23 của TJ, Codex tiếp nhận AIM-04 và chuẩn bị hồ sơ Independent Audit. Batch 01 được báo cáo PROVISIONAL; AIM-04 là kế hoạch chưa thực thi Batch 02. Audit security/sharing BLOCKED; chưa commit hoặc push phần hợp nhất. Chỉ được commit sau PASS; push cần TJ duyệt nội dung và thao tác riêng, đúng đích PRIVATE đã xác minh. Không thay mục tiêu Lab, không chạy batch/Phase 2 mới, không rewrite history hoặc thay đổi W24. CHECKPOINT_LOG.md là mốc hợp nhất; các phần phạm vi AIM-01 bên dưới là snapshot lịch sử. Chưa có yêu cầu khách duyệt.

Chủ sở hữu: TJ. Ngày khởi tạo: 2026-11-25 (Asia/Saigon).

## Đích đến

TJ có thể hiểu bài toán kinh doanh, đánh giá chatbot có bằng chứng, giao yêu cầu có tiêu chí nghiệm thu cho IT và phát triển phương pháp AI Consulting tái sử dụng. Case đầu tiên là AIMICA; Lab không sở hữu hay đại diện hệ thống AIMICA.

## Phạm vi được duyệt hiện tại

**Cập nhật ngày 2026-11-25 — TJ chỉ đạo “AIM-01 — DISCOVERY DECISION & CHECKPOINT”:** đóng AIM-01, ghi Human Review/quyết định và tạo commit riêng sau kiểm tra, không push. Ưu tiên chính: đánh giá chatbot AIMICA hiện hữu trên Zalo từ góc nhìn khách mua bảo hiểm; hướng Sales/CTV và quản lý KPI là nghiên cứu phụ, chưa quyết định triển khai. Chỉ chuẩn bị AIM-02 và handoff AGY, chưa cho phép bắt đầu hoặc tự chạy Zalo. Decision Log trong PROJECT_STATUS.md là căn cứ; không thay mục tiêu Lab hay suy ra khách duyệt requirements.

**Cập nhật quyền ngày 2026-11-25 — TJ duyệt trong chỉ đạo “PHASE 1 — AIM-01”:** cho phép khôi phục ngữ cảnh, nghiên cứu nguồn công khai AIMICA, phân tích ba nhóm người dùng, soạn 15 câu hỏi, đề xuất tối đa ba use case và bài học; cập nhật tài liệu theo dõi. Không kiểm thử Zalo, điều khiển Chrome, xây ứng dụng, chạy Phase 2, gọi API trả phí hoặc tự commit/push. Đây là mở phạm vi do TJ duyệt, không phải khách duyệt requirements.

**Phạm vi gốc Phase 0 (đã hoàn tất):** kiểm tra thư mục/Git, tạo repo local nếu độc lập, tạo tài liệu tối thiểu, kiểm kê skill, lập kế hoạch và chuẩn bị bàn giao. Lệnh bootstrap của TJ là căn cứ duyệt cho phạm vi này.

Cho phép ghi tài liệu và cấu hình Git cục bộ trong project. Không có quyền suy ra hợp đồng, quyền truy cập hệ thống khách hoặc phê duyệt từ AIMICA.

## Hai track

- **A — AIMICA:** chuẩn bị discovery, đánh giá có giới hạn, yêu cầu IT và đề xuất tư vấn khi được duyệt ở các phase sau.
- **B — Phương pháp:** TJ học cách đặt câu hỏi, kiểm tra bằng chứng, đưa quyết định và chuẩn hóa mẫu có thể dùng với khách khác.

## Nguyên tắc

1. Bài toán kinh doanh trước công nghệ; xác định kết quả cần đạt trước khi chọn giải pháp.
2. Mọi kết luận đáng kể có nguồn, thời điểm, phạm vi và giới hạn; chưa biết thì ghi chưa biết.
3. Tách tài liệu nội bộ, đề xuất cho khách và nội dung khách thực sự duyệt.
4. Làm nhỏ, có thể kiểm tra, không nhân bản file chỉ để đủ cấu trúc.
5. Tôn trọng công việc có sẵn; cập nhật trạng thái và handoff sau mỗi nhiệm vụ.
6. Tái sử dụng phương pháp, không mang dữ liệu riêng của khách sang case khác.

## Ranh giới

Không xây chatbot; không tự động kiểm thử Zalo; không cài dependencies không cần thiết; không gọi API trả phí; không đụng production; không sửa ngoài project; không tự commit/push; không lịch hoặc tiến trình nền. Phase 1 chỉ có quyền nghiên cứu/tài liệu nêu trên; Phase 2 và việc liên hệ khách chưa được phép thực hiện.

## Tiêu chí đóng Phase 0

- Repo độc lập đúng đường dẫn, không nested repo và không ghi đè dữ liệu cũ.
- Có README dễ hiểu, Anchor, kế hoạch A/B, hướng dẫn chung, trạng thái và handoff.
- Có câu hỏi discovery chưa được khách duyệt, mẫu Wheel Check và mẫu daily summary.
- Có inventory skill dựa trên file thực tế, `.gitignore` và kiểm chứng tương ứng.
- Có đúng một nhiệm vụ AIMICA kế tiếp: AIM-01, chờ TJ cho phép Phase 1.

Đóng Phase 0 không đồng nghĩa đã đánh giá AIMICA hay sẵn sàng ký hợp đồng. Thay đổi Anchor phải ghi ai duyệt, ngày và thay đổi trong PROJECT_STATUS.md.
