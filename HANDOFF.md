# Handoff — AGY / AIM-02 (chưa bắt đầu)

## Handoff hiện hành — 2026-11-25

**TJ đã đóng AIM-01 và chọn QA chatbot Zalo hiện hữu từ góc nhìn khách mua bảo hiểm làm ưu tiên chính.** Sales/CTV và KPI là nghiên cứu phụ, chưa quyết định triển khai. Thông tin có bot Zalo do TJ cung cấp; chưa có kiểm chứng vận hành độc lập. Chưa ra lệnh bắt đầu AIM-02; AGY không mở/gửi tin Zalo từ handoff này.

**Đọc:** AGENTS.md → LAB_ANCHOR.md → PROJECT_STATUS.md (D-001) → TASK_BOARD.md → HUMAN_REVIEW.md. Khi cần chi tiết, đọc INDUSTRY_BRIEF.md (nguồn/giới hạn), DISCOVERY_QUESTIONS.md (Q04–Q05, Q11–Q14 và cách đo đề xuất), INITIAL_USE_CASES.md (giả thuyết, không phải yêu cầu xây mới).

**Trước khi chạy:** TJ cần chốt đúng OA/bot và tài khoản, phạm vi/cách thử/giới hạn lượt, quyền kiểm tra và lưu bằng chứng, nguồn sản phẩm/người xác nhận nghiệp vụ, thời hạn lưu. Khi có lệnh mới, AGY kiểm tra Git/diff, ghi owner và phạm vi; không ghi đè thay đổi khác.

**Mục tiêu thu bằng chứng:** khách có được hỏi rõ nhu cầu, giải thích có căn cứ và giới hạn, hướng dẫn bước tiếp theo/chuyển người hữu ích không. Ghi cả hành vi hữu ích và vấn đề; chưa có đáp án chuẩn thì ghi UNKNOWN. Không kết luận chất lượng từ thông điệp quảng cáo hoặc một ảnh rời.

**Nơi lưu dự kiến trong project (chưa tạo, chưa có evidence):**

- `private/aimica/AIM-02/raw/`: bản gốc được phép lưu; hạn chế truy cập và không đưa vào Git.
- `private/aimica/AIM-02/redacted/`: bản đã che dữ liệu cá nhân để TJ xem.
- `private/aimica/AIM-02/evidence_index.csv`: `case_id, evidence_id, captured_at_timezone, bot_identifier, context, prompt, response, image_path, reference_source, observation, unknowns, redaction_status`. Giữ cả chuỗi nhiều lượt, không chỉ câu trả lời cuối; che định danh trong chỉ mục khi cần.

Các đường dẫn trên thuộc `/private/`, đã bị .gitignore bỏ qua; không force-add. Không dùng dữ liệu thật của khách. Nếu bản gốc lộ dữ liệu ngoài phạm vi cho phép, dừng việc lưu/chia sẻ đó và báo TJ. File tracked chỉ ghi tóm tắt đã ẩn danh và evidence ID; không chép hội thoại thật vào repo. Evidence local bị ignore không có backup Git; TJ cần chốt quyền và thời hạn lưu.

**Đầu ra khi được chạy:** chỉ mục + chuỗi hỏi–đáp/ảnh đủ ngữ cảnh cho từng tình huống hoặc lý do không thu được; cập nhật Board/Status/Handoff sau khi kiểm tra dữ liệu. Không mua, đóng phí, nộp hồ sơ thật, xây/sửa bot hoặc tự tạo requirements/Phase 2. Không có phiên kiểm thử hay tác vụ nền nào đang chạy.

**Checkpoint:** commit AIM-01 chứa bản handoff này, message `docs: close AIM-01 discovery and prepare AIM-02 handoff`; tra SHA bằng `git log --format="%H %s" -1`. Không remote/push. Kiểm tra Git thực tế trước khi tiếp tục, không mặc định HEAD vẫn giữ nguyên.

## Snapshot sau nghiên cứu AIM-01 — trước quyết định ưu tiên/checkpoint

Phần dưới giữ lịch sử bàn giao trước khi TJ chọn hướng QA; các câu “chưa commit/chờ chọn trọng tâm” không phải trạng thái hiện hành.

## Hiện tại — 2026-11-25

TJ đã cho phép AIM-01 theo chỉ đạo “PHASE 1 — AIMICA BUSINESS DISCOVERY”. Phần nghiên cứu công khai và tài liệu đã hoàn tất, chưa phỏng vấn/khách duyệt. Đọc trạng thái hiện tại ở PROJECT_STATUS.md; phần Phase 0 dưới đây được giữ như bản bàn giao lịch sử, không phải quyền hiện hành.

- **Checkpoint nền:** main @ `83cd364e11a90a3587484b0e175c10bbf2a740c3`; đầu phiên sạch; không remote. Kết quả AIM-01 chưa stage/commit: 3 file mới và 8 tài liệu tracked sửa.
- **Đầu ra để TJ đọc:** INDUSTRY_BRIEF.md → DISCOVERY_QUESTIONS.md → INITIAL_USE_CASES.md. Có nguồn công khai, ba nhóm người dùng, 15 câu hỏi, ba use case đề xuất và 5 bài học. Không tạo file trùng với câu hỏi Phase 0: bản cũ chỉ làm lịch sử và dẫn link.
- **Bằng chứng:** P1-E01–E04 trong PROJECT_STATUS.md. Nguồn đọc trực tiếp và chỉ mục được phân biệt; /products chưa xác minh toàn bộ danh mục hiện hành. Quảng cáo AI không chứng minh năng lực thật. Không khẳng định pháp nhân, đối tác, nhân thọ hoặc hoa hồng khi thiếu xác nhận.
- **Giới hạn quyền:** không thử chatbot/Zalo, điều khiển Chrome, xây AI app, gọi API trả phí, liên hệ khách, chạy Phase 2 hoặc tự commit/push. Không tác vụ nền hoặc dependency mới.
- **Bước tiếp theo duy nhất:** TJ rà soát ba tài liệu, chọn trọng tâm và quyết định phạm vi tiếp. AI không tự mở thêm nhiệm vụ. Nếu TJ cho phỏng vấn, hỏi các vai trò theo Q01–Q15 và ghi câu trả lời có nguồn; chưa được tự gửi câu hỏi.
- **Khi tiếp quản:** đọc AGENTS/Anchor hiện hành, kiểm tra Git và diff, giữ các thay đổi chưa commit; không diễn giải DONE của AIM-01 thành khách đã duyệt requirements. Cập nhật Board/Status/Handoff sau nhiệm vụ mới.

## Snapshot handoff Phase 0 — trước checkpoint và trước AIM-01

Nội dung sau giữ lại lịch sử, bao gồm trạng thái chưa commit/chưa có quyền Phase 1 tại thời điểm đó.

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
