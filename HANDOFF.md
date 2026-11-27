# W23 Handoff — trạng thái, vai trò và bước tiếp theo

## Hiện hành — Chatbot Evaluation Framework V2.1 — 2026-11-26

- **Sản phẩm hoàn thiện local:** [Rubric V2.1](products/chatbot-evaluation/Rubric_V2.md), [Excel Scorecard tự chấm](products/chatbot-evaluation/W23_Chatbot_Evaluation_Scorecard_V2.xlsx), [Batch 02 Matrix](products/chatbot-evaluation/Batch02_Test_Matrix_V2.md), [Executive Summary](products/chatbot-evaluation/Executive_Summary_AIMICA_Batch01.md), [Hướng dẫn tiếng Việt](products/chatbot-evaluation/Huong_dan_Scorecard.md).
- **Phân biệt framework và AIMICA:** sheet Rubric/Template dùng chung; tab `AIMICA Batch 01` và executive summary chỉ chứa điểm/locator từ summary hiện có, không nhúng raw transcript/ảnh. Trọng số và cutoffs là proposal, chưa calibrate hoặc AIMICA phê duyệt.
- **Batch 01:** áp rubric trên summary đã có: 3.07/5 phần đã chấm, 67% Evidence Coverage, 6 tiêu chí SCORED / 4 UNKNOWN / 0 N/A. Kết quả vẫn PROVISIONAL; Confirmed IT Defects = 0. Không chấm lại raw evidence trong checkpoint này.
- **Batch 02:** B2-01..B2-07 được ánh xạ vào C1–C10, kèm prompt giả lập/expected behavior/gates. Tất cả `NOT RUN`; chưa có authorization để live QA.
- **Kiểm tra file:** Excel COM recalculate, kiểm các nhánh tính điểm/coverage/N-A/CF/đầu vào lỗi và PDF render các sheet chính; không thấy lỗi công thức. Đây là tự kiểm sản phẩm, không phải audit độc lập hay calibration.
- **Quyền/phạm vi:** không liên hệ AIMICA, không gửi tài liệu ra ngoài, không chỉnh W24, không commit/push.
- **Bước tiếp theo:** TJ xem Rubric V2.1 và hướng dẫn; dùng template khi có evidence mới được phép chấm. Batch 01 vẫn PROVISIONAL; chưa chạy thêm QA, chưa liên hệ khách, không commit/push.

## Snapshot — W23 Business Discovery / Handoff đa AI — 2026-11-26 (đang để lại, không phải việc hiện hành)

- **Owner decisions:** W23 PUBLIC có chủ đích; giữ nguyên lịch sử; Claude/Codex/AGY được đọc tài liệu đã rà soát đủ điều kiện công khai. Không còn chờ quyết định D1–D3.
- **Rà nội dung evidence:** 32 file dưới `private/` đã phân loại theo nội dung. Không thấy PII khách hoặc credential. Ba test prompts là synthetic, output là bot thật; AAA PDF là policy công khai có thông tin liên hệ, tên/chữ ký người ký. Báo cáo nghiên cứu cũ nêu chi tiết pilot/provider và workspace, không cần cho brief. Xem bảng phân loại trong [AIM-03 audit](AIM-03_SECURITY_AND_GITHUB_READINESS_AUDIT.md).
- **Đầu ra:** [AIMICA Business Discovery Brief](AIMICA_BUSINESS_DISCOVERY_BRIEF.md) — problem discovery, câu hỏi, KPI evidence cần xin, gates tới Gap Analysis/Solution Design/ROI/Commercial Proposal. Chưa gửi AIMICA.
- **Claude — independent brief reviewer:** chỉ đọc `AIMICA_BUSINESS_DISCOVERY_BRIEF.md`, `INDEPENDENT_AUDIT_PACKAGE.md`, `LAB_ANCHOR.md`, `INDUSTRY_BRIEF.md`, `DISCOVERY_QUESTIONS.md`, `HUMAN_REVIEW.md`. Trả về: (1) giả định/yêu cầu chưa có nguồn, (2) tối đa 3 câu hỏi có giá trị thông tin cao nhất, (3) kiểm tra đường dẫn từ discovery đến proposal. Không chấm lại QA, không kết luận từ primary evidence, không sửa brief. Đây là phạm vi handoff đã chuẩn bị; chưa gửi lời nhắn/đính kèm.
- **AGY — customer journey & Track B mapper:** đọc `AIMICA_BUSINESS_DISCOVERY_BRIEF.md`, `AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md`, `DISCOVERY_QUESTIONS.md`, `WHEEL_CHECK_TEMPLATE.md`. Chỉ lập bảng liên kết journey gaps → câu hỏi discovery → reusable template/lesson; chỉ ra phần nào không phục vụ quyết định kinh doanh. Giữ nguyên AIM-04; không thiết kế thêm batch, chạy Zalo hay lặp review brief của Claude.
- **Codex — integrator:** đã tổng hợp nguồn hiện có thành brief; sau phản hồi AI, chỉ hợp nhất phần không mâu thuẫn với Anchor/evidence. Không tự liên hệ khách, chia sẻ file hay chạy Batch 02.
- **Claude scope excludes** raw transcript, evidence index CSV, 3 screenshots, full PDF/page renders và `AIMICA_RESEARCH_REVIEW_FULL.md` chứa chi tiết internal-pilot/workspace. Chúng không cần cho review brief này; đây là giới hạn theo mục đích, không phải kết luận rằng toàn bộ là confidential. Không gửi kèm.
- **Bước tiếp theo duy nhất:** TJ xem brief và quyết định có ủy quyền buổi discovery với AIMICA; nếu có, chỉ định đầu mối/người tham gia/kênh. Không liên hệ khách cho tới khi TJ quyết định.

## Snapshot AIM-03 CHECKPOINT 02 trước quyết định mới (superseded)

- Local `main` sạch, `origin/main` trùng tại `9276976f547178cfe2893dfed8a4a4e1c2f8be92`; GitHub API xác nhận repo PUBLIC, default `main`.
- Bảy commit có email cá nhân trong metadata. Có 32 file tracked dưới `private/` (GitHub tree có 38 entry gồm 6 thư mục), gồm raw transcript, screenshots, PDF và renders. Tài liệu handoff cũ ghi private evidence chỉ local/ignored và GitHub chưa được xác minh là **không còn đúng**.
- Security/sharing = **BLOCKED / NOT PASS**. SEC-01/04/06 FAIL; SEC-02/03 cần quyết định TJ; SEC-05 BLOCKED. Không biết ai đã truy cập/tải/copy. Đổi sang PRIVATE không thu hồi bản sao.
- Không gửi Independent Audit package cho Claude; chưa có allowlist/chấp thuận chia sẻ. Không đổi visibility, xóa file, rewrite history, commit/push hoặc chạy Batch 02.
- Đọc [phiếu quyết định](AIM-03_CHECKPOINT02_HUMAN_DECISION_SHEET.md), [security audit](AIM-03_SECURITY_AND_GITHUB_READINESS_AUDIT.md), [checkpoint log](CHECKPOINT_LOG.md). Các snapshot bên dưới không phản ánh trạng thái Git mới.
- **Bước tiếp theo duy nhất:** chờ TJ chốt D1–D3 (exposure/visibility, disposition lịch sử, allowlist). Sau quyết định mới xác định remediation/checklist kế tiếp; không tự mở phase.

## Snapshot — Codex consolidated checkpoint trước quyết định mới

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
