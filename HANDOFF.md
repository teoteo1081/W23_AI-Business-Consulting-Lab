# Handoff — AIM-04 Handover Checkpoint cho Codex (Chờ duyệt Batch 02)

## Handoff hiện hành — Claude Code, Batch 02 live — 2026-11-26

- **Làm gì:** theo D-008 (xem PROJECT_STATUS.md), Claude chạy B2-01..07 trên Bot AI Assistant 01 qua Zalo Web; kết quả và transcript tại `private/aimica/AIM-02/batch02/` (local, ignore, không backup Git).
- **Lưu ý trạng thái Git:** repo đã có remote `origin` và đang PUBLIC (D-005..D-007); các dòng "không remote / main @ 623c518" bên dưới là snapshot cũ. Theo D-009, toàn bộ `private/aimica/AIM-02/batch02/` (kể cả bẫy bảo mật S1–S7 và câu thu nhập CTV C-01..C-09) đã được force-add và push công khai.
- **Bước tiếp theo:** Codex/Business Owner review độc lập kết quả Batch 02; quyết định có chạy B2-04 Nhánh A sau `/new` không.

## Handoff hiện hành — Codex consolidated checkpoint — 2026-11-26

- **Đã tiếp nhận:** đọc toàn bộ AIM-04 và diff ba file điều phối AGY. Giữ nguyên file AIM-04; không chấm lại Batch 01 hoặc thay rubric được duyệt. Ghi CONS-01..09 riêng trong INDEPENDENT_AUDIT_PACKAGE.md.
- **Đã lưu:** AIM-03_SECURITY_AND_GITHUB_READINESS_AUDIT.md, INDEPENDENT_AUDIT_PACKAGE.md, CHECKPOINT_LOG.md; cập nhật các đầu mối quản trị và củng cố .gitignore. Không chuyển hoặc sửa bằng chứng private.
- **Kết quả:** Security/GitHub readiness BLOCKED; credential pattern scan chưa thấy secret, nhưng metadata email/nội dung pilot/trích lời bot và quyền chia sẻ chưa đóng. Không commit/push; main vẫn `623c5185b98d5efc1131d8d5928779ae7891cd30`. Không remote; URL/visibility NOT VERIFIED. Thay đổi mới còn local modified/untracked.
- **Đọc tiếp:** CHECKPOINT_LOG.md → AIM-03 report → INDEPENDENT_AUDIT_PACKAGE.md → PROJECT_STATUS.md. Báo cáo trước của AI là nguồn cần đối chiếu, không phải kết quả audit độc lập mới. Evidence gốc không nằm trong Git; không force-add hoặc upload vì nhãn redacted.
- **Một bước tiếp theo:** TJ chốt disposition bảo mật/allowlist tại AIM-03 CHECKPOINT 02; khi đủ điều kiện mới audit lại và dùng quyền commit có điều kiện. Push vẫn cần TJ xác nhận nội dung và duyệt thao tác tới PRIVATE repository đã xác minh. Không tự chạy Batch 02, liên hệ khách hoặc thay đổi W24.
- **Snapshot:** các phần bên dưới bảo toàn bàn giao AGY và lịch sử; mô tả số file/quyền pre-QA tại đó không phải trạng thái hiện hành.

## Cập nhật AIM-04 — Handover Checkpoint cho Codex — 2026-11-26

- **Người bàn giao:** AGY | **Người tiếp nhận:** Codex | **Trạng thái:** `HANDOVER CHECKPOINT` (chưa commit, chưa push).
- **Đầu ra chính:** [AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md](AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md) — tổng hợp đầy đủ Customer Journey Gap Analysis, Public Benchmark Research (8 lĩnh vực kèm link nguồn), Wheel Check (không cài thêm tool), Ma trận kiểm thử Batch 02 (`B2-01`–`B2-07` xếp hạng theo Giá trị KD / Rủi ro / Công sức, dùng 100% dữ liệu giả lập), Khung đánh giá Human Handoff, Rủi ro và Câu hỏi mở cho Business Owner & IT.
- **Kỷ luật bằng chứng:** Phân biệt rõ `VERIFIED FACTS`, `OBSERVATIONS (PROVISIONAL)`, `HYPOTHESES`, `UNKNOWNS`, `RECOMMENDATIONS (NOT CLIENT APPROVED)` và `VALIDATED DEFECTS = 0`. Không chứa PII, không chứa dữ liệu khách hàng thật.
- **Bảo toàn công việc Codex:** Không chỉnh sửa báo cáo Independent Review hay các kết quả của Codex.
- **Tình trạng Git:** Nền `main` @ `623c518`; hiện có 1 file mới (`AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md`) và 3 file điều phối cập nhật (`TASK_BOARD.md`, `PROJECT_STATUS.md`, `HANDOFF.md`) ở working tree, chưa stage/commit/push.
- **Bước tiếp theo cho Codex / TJ:** Codex tiếp nhận rà soát tài liệu AIM-04; chờ TJ / Business Owner chốt các câu hỏi mở và quyết định danh sách Batch 02 (`B2-01`–`B2-03` ưu tiên nhanh hoặc đủ 7 ca) trước khi cấp quyền live QA.

## Cập nhật sau Batch 01 & Evidence Reconciliation — 2026-11-25

- **Đã hoàn tất:** Research & QA Baseline (`AIMICA_RESEARCH_REVIEW.md`), Ground Truth Validation (PDF Quy tắc AAA 22 trang tại `private/aimica/AIM-02/reference/`), Live QA Batch 01 (`TC-01`, `TC-03A`, `TC-03B` theo xác nhận quyền của TJ), Independent Review của Codex (`AIM-02_INDEPENDENT_REVIEW_CODEX_2026-11-25.md`), đối soát `evidence_index.csv` và `QA_HANDOFF_SUMMARY.md` trong `private/aimica/AIM-02/`.
- **Trạng thái hiện tại:** `PROVISIONAL` — chưa phải nghiệm thu chính thức và không gán Confirmed IT Defects.
- **Bước tiếp theo:** Chờ TJ / Business Owner chốt các câu hỏi mở trong `private/aimica/AIM-02/QA_HANDOFF_SUMMARY.md` trước khi duyệt chạy Batch 02. Không tự gửi thêm tin Zalo, không commit/push.

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
