# Project Status

## Hiện hành — Cross-Agent Handover (Codex → AGY) & Safe Local Checkpoint — 2026-11-26

- **Căn cứ:** Chỉ đạo “W23 — CROSS-AGENT HANDOVER: CODEX → AGY” ngày 2026-11-26 (Decision `D-004`). TJ chuyển quyền thực thi W23 từ Codex sang AGY, cho phép kiểm chứng Git, phân loại bảo mật/chia sẻ, đề xuất kiến trúc 2 repository, cập nhật `HANDOVER.md`/`PROJECT_STATUS.md` và tạo **local checkpoint commit an toàn**; nghiêm cấm push GitHub, tạo remote, rewrite history, sửa W24 hoặc chạy Batch 02.
- **Đối chiếu & Tiếp quản:** Xác nhận thực tế repo khớp báo cáo Codex (`main` @ `623c518`, 8 modified, 5 untracked, 0 remote, 32 file trong `private/` bị ignore, `git fsck` sạch). Bảo toàn 100% công việc hợp lệ của Codex (`AIM-03`, `CHECKPOINT_LOG.md`, `INDEPENDENT_AUDIT_PACKAGE.md`, `.gitignore`, cập nhật quản trị) và `AIM-04` của AGY.
- **Trạng thái bảo mật & kiểm thử (GIỮ NGUYÊN):**
  - **Security & Sharing Audit:** `BLOCKED` cho việc chia sẻ ngoài máy / push GitHub (tồn tại SEC-01 metadata email trong lịch sử cũ, SEC-02 thông tin pilot/đường dẫn local trong `AIMICA_RESEARCH_REVIEW.md`, SEC-03 trích lời bot trong `AIM-02_HUMAN_REVIEW.md`, và chưa có allowlist/quyền chia sẻ evidence được TJ duyệt).
  - **AIM-02 Batch 01:** `PROVISIONAL` (`TC-01`, `TC-03A`, `TC-03B`; `Confirmed IT Defects = 0`).
  - **Batch 02:** Chưa chạy, chưa được cấp quyền thực thi.
- **Local Checkpoint:** Stage tường minh danh sách file tài liệu hợp lệ (không `git add .`, không chạm `private/`) để tạo local checkpoint commit bảo toàn công việc Codex + AGY trên **Local Master Repository**. Không phải phê duyệt chia sẻ hay push.
- **Kiến trúc lưu trữ đề xuất:** Tách bạch **A. Local Master Repository** (nội bộ, giữ đủ lịch sử & evidence bị ignore) và **B. Private Sanitized Review Repository** (lịch sử mới sạch metadata, chỉ chứa allowlist đã sanitize và được TJ duyệt — chưa tạo trên GitHub).

| ID | Người/ngày/căn cứ | Quyết định | Ranh giới |
|---|---|---|---|
| D-004 | TJ, 2026-11-26, “W23 — CROSS-AGENT HANDOVER: CODEX → AGY” | Chuyển giao quyền thực thi W23 từ Codex sang AGY; cho phép audit bảo mật local, đề xuất kiến trúc 2 repo, cập nhật `HANDOVER.md`/`PROJECT_STATUS.md` và tạo local checkpoint commit an toàn | Giữ Security Audit = `BLOCKED`, Batch 01 = `PROVISIONAL`; không push, không tạo remote, không rewrite history, không sửa W24, không chạy Batch 02 |
| D-005 | TJ, 2026-11-26, xác nhận trực tiếp trong hội thoại | Chấp nhận SEC-01/02/03 chỉ trong phạm vi repository **PRIVATE**; cho phép tạo repo PRIVATE `teoteo1081/W23_AI-Business-Consulting-Lab`, xác minh visibility `PRIVATE` trước khi push Local Master `main` | Chỉ riêng W23; tuyệt đối không đẩy `private/` (32 file evidence bị `.gitignore` loại trừ); không chạm W24/repo khác; giữ Batch 01 `PROVISIONAL`, không chạy Batch 02 |
| D-006 | TJ, 2026-11-26, chỉ đạo trực tiếp “đẩy lên hết đi chứ, nó là public mà” | Mở rộng phạm vi push lên repository **PRIVATE** `teoteo1081/W23_AI-Business-Consulting-Lab` bao gồm toàn bộ 32 file đã quét sạch PII/secret trong `private/aimica/AIM-02/` (PDF AAA công khai + 22 trang render, 3 ảnh đã che thanh chat, transcript giả lập, index và báo cáo đối soát) | Chỉ đẩy lên repo **PRIVATE** đã xác minh; giữ quy tắc `/private/` trong `.gitignore` cho các file mới về sau; giữ Batch 01 `PROVISIONAL`, không chạy Batch 02 |
| D-007 | TJ, 2026-11-26, xác nhận trực tiếp sau cảnh báo rủi ro | Chuyển visibility repository `teoteo1081/W23_AI-Business-Consulting-Lab` sang **PUBLIC** (TJ chấp nhận công khai toàn bộ nội dung hiện có gồm lịch sử commit, thông tin pilot và 32 file trong `private/aimica/AIM-02/`) | Chỉ áp dụng cho W23; không chạm W24/repo khác; giữ Batch 01 `PROVISIONAL`, không chạy Batch 02 |
| D-008 | TJ, 2026-11-26, trong hội thoại với Claude Code: "bot này đang thử nghiệm mà cứ thoải mái thử thôi" + chốt phạm vi qua câu hỏi | Cho phép Claude chạy live Batch 02 đủ B2-01..07 trên "Bot AI Assistant 01" qua Zalo Web/Chrome bằng tài khoản TJ; chấp nhận B2-02 có thể ping nhân viên; không reset (chat tiếp) | Chỉ prompt giả lập/placeholder; kết quả `PROVISIONAL` lưu local tại `private/aimica/AIM-02/batch02/` (file mới, bị `.gitignore`); không commit/push |
| D-009 | TJ, 2026-11-27, trong hội thoại với Claude Code: "cho public hết đi" + chọn "Đẩy hết, kể cả bảo mật" sau cảnh báo (lỗ hổng S2 chưa vá, nhà cung cấp/máy chủ từ banner nội bộ, output thật của bot pilot) | Force-add và push toàn bộ `private/aimica/AIM-02/batch02/` (kết quả, transcript, 19 ảnh, báo cáo HTML) cùng file trạng thái lên repo PUBLIC `teoteo1081/W23_AI-Business-Consulting-Lab` | Không force push, không rewrite history, không chạm W24; Batch 01/02 vẫn `PROVISIONAL` |

## Cập nhật Batch 02 — 2026-11-26 23:19–23:23 (+07:00)

- **Bổ sung 2026-11-26/27:** 7 bẫy bảo mật S1–S7 (6 đạt, S2 cần IT xem luồng OTP) và 9 câu thu nhập Sale/CTV C-01..C-09 (4 đạt, 1 một phần, 3 hụt, 1 cần xem). Báo cáo HTML hai tab: `private/aimica/AIM-02/batch02/report/index.html`.

- **Đã chạy** B2-01..07 (10 tin nhắn, một phiên nối tiếp Batch 01). Kết quả Claude: 5 PASS, B2-02 PARTIAL (không có live handoff), B2-06 lượt 2 PARTIAL (câu gần phán quyết claim); không quan sát Critical Fail. Chi tiết: `private/aimica/AIM-02/batch02/BATCH02_RESULTS_CLAUDE_2026-11-26.md`, transcript `batch02_transcript.md`.
- **Quan sát mới:** banner bot có thông tin vận hành pilot và lệnh reset; chi tiết chỉ lưu trong file kết quả private. Nhánh A của B2-04 chưa chạy.
- **Giới hạn nguồn:** B2-07 mới khớp tài liệu nội bộ (AIM-04/research review), chưa đối chiếu lại trang sản phẩm/PDF trong phiên; `private/aimica/AIM-02/reference/QTBH_extracted.txt` chỉ có dấu trang, không có text.
- **Giới hạn:** chưa lưu ảnh chụp ra đĩa; chưa có review độc lập/Business Owner; trạng thái `PROVISIONAL`, Confirmed IT Defects = 0.

## Hiện hành — Consolidated Checkpoint / Independent Audit — 2026-11-26

- **Căn cứ mới:** TJ yêu cầu hợp nhất AIM-03 của Codex và AIM-04 của AGY, lưu báo cáo, đối chiếu hồ sơ, quét toàn bộ tracked files/history và chỉ commit nếu security PASS. Chưa duyệt nội dung chia sẻ hoặc push. Không thay đổi W24.
- **Kết quả:** AIM-03 đã lưu tại [Security Audit](AIM-03_SECURITY_AND_GITHUB_READINESS_AUDIT.md); toàn bộ file AIM-04 và ba diff điều phối đã được tiếp nhận. Bản AIM-04 của AGY giữ nguyên; review consistency/rubric CONS-01..09 trong [Independent Audit Package](INDEPENDENT_AUDIT_PACKAGE.md). Không phát sinh kết quả chatbot mới.
- **Security/GitHub readiness: BLOCKED.** Không thấy credential theo mẫu quét, nhưng metadata email cá nhân, thông tin pilot/trích lời bot và quyền chia sẻ evidence chưa được giải quyết. Không commit/push. Không remote; GitHub search đúng tên không có kết quả trong phạm vi connector, URL/visibility chưa xác minh.
- **Git:** main @ `623c5185b98d5efc1131d8d5928779ae7891cd30`; các file bàn giao/hợp nhất còn modified/untracked, không có commit mới. [Checkpoint Log](CHECKPOINT_LOG.md) ghi kết quả và bước tiếp theo; không coi tài liệu local là đã backup ngoài máy.
- **Trạng thái nghiệp vụ:** AIM-01 DONE desk research; AIM-02 IN_PROGRESS/PROVISIONAL, ba ca Batch 01; AIM-04 DONE research/planning do AGY, Codex đã review tài liệu, chưa chạy Batch 02. Confirmed IT Defects = 0; chưa có requirements khách duyệt. Bằng chứng PDF/ảnh được tái kiểm hash, không tái xác nhận nội dung hoặc tuân thủ pháp luật.
- **Bước tiếp theo duy nhất:** AIM-03 CHECKPOINT 02 — TJ chốt disposition bảo mật, allowlist và gói chia sẻ. Phần sau giữ snapshot bàn giao/lịch sử; không dùng câu “chưa bắt đầu AIM-02” làm trạng thái hiện hành.

### Quyết định mới — không bổ sung quyền quá khứ

| ID | Người/ngày/căn cứ | Quyết định | Ranh giới |
|---|---|---|---|
| D-003 | TJ, 2026-11-26, “W23 — CONSOLIDATED CHECKPOINT & GITHUB READINESS” trong hội thoại | Lưu AIM-03, tiếp nhận AIM-04, hợp nhất tài liệu và security audit; commit tài liệu an toàn khi PASS | FAIL/BLOCKED thì dừng trước commit; push cần xác nhận nội dung và phê duyệt thao tác riêng, chỉ PRIVATE; không rewrite/force push/W24 |

Quyền chạy Batch 01 được thuật lại trong hồ sơ AIM-02; chưa có bản tóm tắt phê duyệt đầy đủ để kiểm độc lập mọi giới hạn. Không dựng thêm decision log ngày cũ hoặc suy ra consent chia sẻ. AIM-04 được thuật lại là đóng theo chỉ đạo TJ trong handover AGY; việc tiếp nhận hôm nay không nghiệm thu rubric hoặc nguồn benchmark.

## Cập nhật AIM-04 — Research & Batch 02 Planning Handover — 2026-11-26

- **AIM-04: DONE (Handover Checkpoint cho Codex).** Theo lệnh `CLOSE CHECKPOINT AIM-04` của TJ, AGY đã tổng hợp toàn bộ kết quả nghiên cứu và lập kế hoạch Batch 02 vào [AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md](AIM-04_CUSTOMER_JOURNEY_AND_BATCH02_PLAN.md) (gồm Epistemic Classification, Customer Journey Gap Analysis, Public Benchmark Research có link nguồn, Wheel Check, Batch 02 Test Matrix `B2-01`–`B2-07`, Human Handoff Assessment Framework, Risks và Unresolved Questions).
- **Mốc Git nền:** `main` @ `623c5185b98d5efc1131d8d5928779ae7891cd30` (`docs: record aimica batch01 provisional assessment`), 1 worktree, không remote. Các thay đổi AIM-04 hiện nằm trong working tree (untracked/modified), **chưa stage, chưa commit, chưa push** theo đúng chỉ đạo.
- **Bảo toàn & Ranh giới:** Không sửa kết quả của Codex; không gửi tin nhắn lên chatbot live; không chứa dữ liệu nhạy cảm hay thông tin khách hàng thật; giữ nguyên trạng thái `Validated Defects = 0` và chưa có yêu cầu được khách hàng phê duyệt. Dừng tại Handover Checkpoint cho Codex và chờ Business Owner / TJ duyệt trước Batch 02.

## Hiện tại — đóng AIM-01 / chuẩn bị AIM-02 — 2026-11-25

- **AIM-01: CLOSED / DONE.** TJ đã xem báo cáo và chốt ưu tiên trong chỉ đạo “AIM-01 — DISCOVERY DECISION & CHECKPOINT”. Đóng nhiệm vụ nghiên cứu/tài liệu; không đồng nghĩa đã phỏng vấn khách hoặc khách duyệt requirements.
- **Human Review:** [HUMAN_REVIEW.md](HUMAN_REVIEW.md), bản ngắn tối đa một trang đọc; tổng hợp ba tài liệu và các quyết định còn thiếu.
- **AIM-02:** Current Chatbot QA Evidence Collection, `IN_PROGRESS` (`PROVISIONAL`). Ngày 2026-11-25, TJ đã xác nhận quyền kiểm thử bot pilot và duyệt chạy Batch 01 (TC-01, TC-03A, TC-03B). AGY đã thu transcript/screenshot (lưu trong `private/aimica/AIM-02/` bị `.gitignore` bỏ qua), Codex đã hoàn tất Independent Review, và Evidence Index + QA Handoff Summary đã đối soát trạng thái `PROVISIONAL` (TC-01 `PARTIAL` theo rubric nháp, TC-03A đúng phạm vi web chuẩn / cần xác nhận ngoại lệ hợp đồng, TC-03B `PASS` trong phạm vi đã thử). Không suy ra Confirmed IT Defects hoặc nghiệm thu chính thức; chờ Business Owner chốt câu hỏi mở trước Batch 02.
- **Checkpoint:** TJ cho phép một commit local riêng cho AIM-01 sau kiểm tra. Commit chứa trạng thái này có message `docs: close AIM-01 discovery and prepare AIM-02 handoff`; tra SHA từ Git (`git log -1 --format="%H %s"`). Không ghi SHA của chính commit vào nội dung của nó. SHA và working tree được kiểm chứng sau commit trong báo cáo terminal/final gửi TJ; không tự tạo commit thứ hai để ghi SHA.
- **Phạm vi giữ nguyên:** không xây/sửa bot, tự chạy Zalo/AIM-02, quyết định yêu cầu sản phẩm thay khách, tự mở Phase 2 hoặc push. Mục tiêu Lab không đổi; Anchor/AGENTS chỉ cập nhật quyền mới do TJ đưa ra.

### Decision Log — nguồn quản lý quyết định hiện hành

| ID | Người/ngày/căn cứ | Quyết định | Tác động và ranh giới |
|---|---|---|---|
| D-001 | TJ, 2026-11-25, chỉ đạo “AIM-01 — DISCOVERY DECISION & CHECKPOINT” | PRIMARY: đánh giá chatbot AIMICA đang hoạt động trên Zalo từ góc nhìn khách mua bảo hiểm. SECONDARY: nghiên cứu nhu cầu trợ lý Sales/CTV và quản lý KPI, chưa quyết định triển khai | Thay thứ tự đề xuất khảo sát UC1 trước của Lab; không biến UC2 thành yêu cầu xây mới. Thông tin bot Zalo do TJ cung cấp, chưa được AI quan sát độc lập; không phải khách duyệt requirements |
| D-002 | TJ, cùng chỉ đạo/ngày | Đóng AIM-01, lập AIM-02 và handoff cho AGY; tạo commit riêng khi kiểm tra đạt; không push | Chỉ được chuẩn bị, không được bắt đầu AIM-02. AGY là owner dự kiến, chưa được gửi lệnh hoặc tự kích hoạt |

**Còn cần TJ chốt trước thực hiện AIM-02:** đúng OA/bot, tài khoản/quyền sử dụng, cách thử và giới hạn lượt/phạm vi sản phẩm; nguồn đối chiếu/người xác nhận nghiệp vụ; quyền xem/lưu, thời hạn lưu bằng chứng; lệnh bắt đầu. Không tự đặt ngưỡng chất lượng hoặc chọn requirements thay khách.

### Bằng chứng review/checkpoint

- **R01 — recovery:** đầu phiên main @ `83cd364e11a90a3587484b0e175c10bbf2a740c3`, 8 file tracked modified và 3 file nghiên cứu mới đúng handoff trước; index trống, một worktree, không remote. Đã đọc lại 8 tài liệu TJ yêu cầu và các file điều hướng liên quan. Bảo toàn thay đổi AIM-01 đã có; không reset/ghi đè công việc khác.
- **R02 — nhất quán:** Human Review, Decision Log, Board, Handoff, Anchor, AGENTS, README và Plan dùng cùng ưu tiên QA hiện trạng. Ba tài liệu nghiên cứu giữ nhãn/nguồn, thêm cập nhật để không còn coi đề xuất UC1 là ưu tiên hiện hành. Snapshot cũ được đánh dấu lịch sử, không sửa chứng cứ cũ.
- **R03 — kiểm tra trước commit:** đối chiếu nội dung/diff, link nội bộ, độ dài Human Review, Q01–Q15, ba use case và năm bài học; quét mẫu thông tin nhạy cảm, kiểm tra đường dẫn bằng chứng thuộc private/ bị ignore, danh sách stage đúng phạm vi. Không dùng dữ liệu thật để thử. Kiểm tra chỉ chứng minh tính nhất quán tài liệu; không chứng minh chất lượng chatbot. Cùng AI tự kiểm tra, không tuyên bố reviewer độc lập.

### Git state reconstruction — checkpoint AIM-01

- **STATE RECONSTRUCTION:** nền Phase 0 và phần nghiên cứu/review AIM-01 được đưa vào commit local riêng chứa bản ghi này, không amend Phase 0.
- **PROJECT IDENTITY:** W23_AI-Business-Consulting-Lab của TJ, đúng root đã chỉ định.
- **HUMAN SUMMARY:** đóng gói nghiên cứu, quyết định TJ và handoff; không có bằng chứng kiểm thử chatbot.
- **CURRENT CHECKOUT:** main; định danh commit AIM-01 bằng message nêu trên và SHA đọc từ Git khi kiểm chứng cuối.
- **REMOTE REFERENCE:** không remote/upstream; không fetch/push hoặc tạo remote.
- **LOCAL WORK NOT YET REMOTE:** Phase 0 và checkpoint AIM-01 chỉ lưu local, không tuyên bố backup ngoài máy.
- **OTHER RELEVANT WORKTREES / BRANCHES:** một worktree main, không nhánh khác tại lần kiểm tra.
- **SAFE CONCLUSION:** checkpoint tài liệu không cấp quyền chạy QA; trạng thái sau commit phải đối chiếu Git thực tế.
- **NEXT ACTION:** chờ TJ chốt đầu vào/lệnh bắt đầu AIM-02; không tự chạy.

## Snapshot sau nghiên cứu AIM-01 — trước quyết định/checkpoint

Các đoạn dưới giữ lại tình trạng trước khi TJ chọn ưu tiên và cho commit; phần hiện hành và Decision Log nằm phía trên.

### Trạng thái sau nghiên cứu AIM-01 — 2026-11-25

- **Phạm vi TJ duyệt:** chỉ đạo “PHASE 1 — AIM-01” cho phép khôi phục ngữ cảnh, nghiên cứu AIMICA công khai và soạn business discovery. Không có khách duyệt requirements. AGENTS.md và LAB_ANCHOR.md chỉ cập nhật đúng quyền mới; không thay mục tiêu Lab.
- **Phase 0:** đã commit thành công tại `83cd364e11a90a3587484b0e175c10bbf2a740c3`, message `chore: bootstrap AI consulting lab phase 0` trên main. Không có remote/push. Những thông tin “chưa commit” trong bản ghi phía dưới là snapshot trước checkpoint, không phải trạng thái hiện tại.
- **AIM-01:** DONE trong phạm vi desk research/tài liệu; execution SUCCESS, đối chiếu đầu ra AUDIT_PASS trong phạm vi đó bởi cùng AI, không reviewer độc lập. Chưa hoàn thành phỏng vấn khách, kiểm chứng vận hành hoặc nghiệm thu sản phẩm.
- **Đầu ra mới:** INDUSTRY_BRIEF.md, DISCOVERY_QUESTIONS.md, INITIAL_USE_CASES.md. AIMICA_DISCOVERY.md giữ bản nháp lịch sử và trỏ đến câu hỏi hiện hành; không duy trì bản trùng.
- **Chưa biết:** pháp nhân/quan hệ phân phối đã đối chiếu gốc, hãng đối tác, nhân thọ đang bán, chính sách hoa hồng, số liệu kinh doanh, chất lượng chatbot và quyền dữ liệu. Chưa có phát hiện nào được khách xác nhận.
- **Git sau nhiệm vụ:** HEAD vẫn là checkpoint Phase 0; 3 file mới untracked và 8 file tài liệu tracked modified, chưa stage/commit. Không có thay đổi từ người/AI khác trước khi nhận việc; trạng thái đầu phiên sạch.
- **Bước tiếp theo duy nhất:** TJ rà soát đầu ra và quyết định trọng tâm/phạm vi tiếp; AI dừng, không tự Phase 2 hoặc liên hệ khách.

### Bằng chứng AIM-01

- **P1-E01 — recovery:** đã đọc AGENTS, Anchor, Plan, Board, Status, Handoff và discovery gốc. Git status đầu phiên sạch; helper git-state-recovery xác nhận main @ SHA trên, một worktree và một commit local-only, không upstream/remote. Không tạo repo hoặc thay đổi Git refs.
- **P1-E02 — nguồn:** đọc https://aimica.vn/ và các URL S2–S5 được ghi tại INDUSTRY_BRIEF.md; tìm kiếm công khai bằng công cụ web. GET HTML công khai /products bằng PowerShell xác nhận phần nhóm nhu cầu. Bản trực tiếp ít nội dung hơn chỉ mục tìm kiếm: đã ghi giới hạn, không coi danh mục chỉ mục là đang bán. Sitemap/robots không đọc được qua web tool; App Store trực tiếp trả 429; không dùng danh bạ bên thứ ba để chốt pháp nhân. Không điều khiển Chrome, không đăng nhập/gửi form.
- **P1-E03 — nội dung:** ba tài liệu có nhãn VERIFIED/HYPOTHESIS/UNKNOWN/NEEDS CLIENT CONFIRMATION và URL nguồn cho quan sát website; câu hỏi Q01–Q15, phân tích ba nhóm, UC1–UC3 và 5 bài học. Cách đo “thông minh” là đề xuất discovery, chưa phải rubric/ngưỡng nghiệm thu được duyệt hoặc phép đánh giá đã chạy.
- **P1-E04 — kiểm tra local:** đọc lại file và diff, kiểm tra link nội bộ, đúng 15 ID câu hỏi, ba mục use case, năm mục bài học và chỉ ba file mới được yêu cầu; kiểm tra whitespace và mẫu bí mật; so HEAD, index, remote và trạng thái cuối. Phạm vi kiểm tra là tài liệu, không chứng minh chatbot/chuyển đổi/ROI. Bằng chứng terminal gốc nằm trong lịch sử công cụ; không tạo thêm báo cáo kiểm tra.

### Git state reconstruction hiện tại

- **STATE RECONSTRUCTION:** từ Git thực tế, checkpoint Phase 0 cộng thay đổi AIM-01 chưa commit.
- **PROJECT IDENTITY:** W23_AI-Business-Consulting-Lab, root đúng đường dẫn TJ cung cấp.
- **HUMAN SUMMARY:** nền tảng Lab đã có commit; nghiên cứu AIM-01 hiện chỉ ở working tree.
- **CURRENT CHECKOUT:** main @ 83cd364e11a90a3587484b0e175c10bbf2a740c3; index trống.
- **REMOTE REFERENCE:** không remote/upstream; không kiểm chứng GitHub.
- **LOCAL WORK NOT YET REMOTE:** một commit Phase 0 local-only và tài liệu AIM-01 chưa commit.
- **OTHER RELEVANT WORKTREES / BRANCHES:** một worktree, chỉ main có commit.
- **SAFE CONCLUSION:** có checkpoint local cho Phase 0; AIM-01 chưa có checkpoint/backup được xác minh.
- **NEXT ACTION:** chờ TJ rà soát; không tự commit, push hoặc bắt đầu Phase 2.

## Snapshot bàn giao Phase 0 — giữ nguyên lịch sử trước checkpoint

Mọi trạng thái/quyền hạn bên dưới thuộc thời điểm kết thúc bootstrap, trước lệnh TJ cho commit và trước AIM-01; trạng thái hiện hành ở phần đầu file.

Ngày: 2026-11-25 (Asia/Saigon). Owner: TJ. Người thực hiện Phase 0: Codex.

**Phase 0 hoàn tất. Execution: SUCCESS. Kiểm tra đối chiếu kết quả: AUDIT_PASS trong phạm vi local được ghi bên dưới.** Đây là lần tự kiểm tra trạng thái cuối bởi cùng AI, không phải đánh giá của người hay agent độc lập. Không kết luận về chất lượng AIMICA.

## Trạng thái công việc

| Hạng mục | Trạng thái | Bằng chứng |
|---|---|---|
| Thư mục và bảo toàn công việc cũ | Đã kiểm tra; thư mục trống trước khi tạo | E01 |
| Repo độc lập | Đã tạo Git local tại đúng root | E02 |
| Anchor và kế hoạch A/B | Đã tạo tài liệu | LAB_ANCHOR.md, PROJECT_PLAN.md; E03 |
| Cơ chế AI tiếp tục | Đã có hướng dẫn, task board, status, handoff và mẫu ngày | AGENTS.md, TASK_BOARD.md, HANDOFF.md, DAILY_SUMMARY.md; E03/E05 |
| Discovery và Wheel Check | Chỉ là câu hỏi/mẫu nội bộ, chưa có khách duyệt | AIMICA_DISCOVERY.md, WHEEL_CHECK_TEMPLATE.md |
| Skill | 7 có file thật; 1 chưa tìm thấy trong phạm vi đã tìm | E04 |
| Bảo vệ file nhạy cảm/tạm | Có quy tắc ignore, kiểm tra bằng đường dẫn giả định | .gitignore; E06 |
| Nhiệm vụ AIMICA kế tiếp | Đúng một: AIM-01, chưa bắt đầu | TASK_BOARD.md |
| Phase 1 / khảo sát / kiểm thử / hợp đồng | Chưa thực hiện, chưa được phép | Chỉ đạo TJ chỉ cho Phase 0 |

## Sổ bằng chứng Phase 0

- **E01 — Trước khi ghi:** `Get-Location` đúng root; `Get-ChildItem -Force` và liệt kê đệ quy không có file/thư mục con. `git rev-parse --show-toplevel` và `git status` trả “not a git repository (or any of the parent directories)”. Kiểm tra AGENTS.md dọc chuỗi thư mục cha không tìm thấy. Không có công việc cũ để ghi đè.
- **E02 — Git:** đã chạy `git init -b main`. Kiểm tra lại top-level trùng project; `git status --short --branch` báo `No commits yet on main`. `git worktree list --porcelain` có một worktree tại root; `git remote -v` và `git for-each-ref` không có kết quả. Không nested repo; không commit, stage hoặc push. Đã đọc helper git-state-recovery; helper đòi HEAD commit nên không chạy trên repo chưa có commit. Dùng lệnh Git đọc trực tiếp để tái dựng trạng thái này.
- **E03 — Đầu ra:** 11 file ở root: README.md, AGENTS.md, LAB_ANCHOR.md, PROJECT_PLAN.md, TASK_BOARD.md, PROJECT_STATUS.md, HANDOFF.md, AIMICA_DISCOVERY.md, WHEEL_CHECK_TEMPLATE.md, DAILY_SUMMARY.md, .gitignore. Nội dung tiếng Việt; không tạo cấu trúc thư mục phụ.
- **E04 — Inventory:** kiểm tra file `SKILL.md` thật bằng `Test-Path`, `Get-Item` và đọc metadata. Tìm đường dẫn bằng `rg --files --hidden` trong `C:/Users/User/.codex/skills` và `C:/Users/User/.codex/plugins/cache` không thấy `local-orchestrator-cli`. Không mở rộng kết luận sang máy/agent khác.
- **E05 — Kiểm tra đầu ra:** đọc lại 11 file từ ổ đĩa; đối chiếu tiêu chí Anchor, hai track, các giới hạn và đúng một dòng nhiệm vụ AIMICA kế tiếp. Kiểm tra liên kết Markdown nội bộ trỏ tới file tồn tại; kiểm tra đủ 6 mục daily summary. Kiểm tra chỉ có một `.git` ở root và Git vẫn chưa có commit/remote. Không chạy thử chatbot hay kiểm tra nghiệp vụ AIMICA.
- **E06 — Ignore:** `git check-ignore --no-index` với tên giả định trong `.env`, private/, client-data/, secrets/, tmp/, file log và khóa trả đúng quy tắc ignore; tài liệu kế hoạch không bị ignore. Không dùng bí mật thật, không tạo file dữ liệu khách để thử. Ignore không bảo đảm mọi tên file nhạy cảm đều được bắt; phải xem diff/nội dung trước khi lưu vào Git.

Bằng chứng lệnh của phiên nằm trong lịch sử công cụ; sổ này lưu tóm tắt đủ để AI sau kiểm tra lại, không phải log terminal nguyên bản.

## Inventory skill — hiện diện, không phải cài đặt hàng loạt

Root kiểm tra: `C:/Users/User/.codex/skills/`. “Có” nghĩa có file SKILL.md đọc được, chưa chứng minh mọi dependency của skill hoạt động. Không sao chép hoặc sửa skill ngoài project.

| Skill | Tình trạng thật / đường dẫn tương đối với root trên | Dùng dự kiến | Trong Phase 0 |
|---|---|---|---|
| execution-contract | Có: execution-contract/SKILL.md | Chốt đầu ra, phạm vi, bằng chứng trước việc phức tạp | Đã đọc và áp dụng |
| rubric-engineering | Có: rubric-engineering/SKILL.md | Thiết kế/hiệu chỉnh rubric khi được duyệt đánh giá | Chỉ kiểm kê metadata |
| risk-adaptive-audit | Có: risk-adaptive-audit/SKILL.md | Đối chiếu kết luận với bằng chứng theo rủi ro | Đã đọc và áp dụng cho đầu ra local |
| decision-advisor | Có: decision-advisor/SKILL.md | Hỗ trợ quyết định có ý nghĩa và xác định ai có quyền chốt | Chỉ kiểm kê metadata |
| po-decision-bridge | Có: po-decision-bridge/SKILL.md | Chuyển checkpoint thành quyết định PO khi TJ gọi rõ | Chỉ kiểm kê; không kích hoạt |
| technicaldebug | Có: technicaldebug/SKILL.md | Chẩn đoán khi có vấn đề kỹ thuật thực tế | Chỉ kiểm kê metadata |
| git-state-recovery | Có: git-state-recovery/SKILL.md | Tái dựng trạng thái Git trước kết luận/tiếp tục | Đã đọc; kiểm tra trực tiếp do chưa có HEAD |
| local-orchestrator-cli | Chưa tìm thấy trong hai vùng E04 | Chỉ cân nhắc sau khi xác định được bản thật và đọc hướng dẫn; chưa suy đoán chức năng | Không tạo giả, không cài, không dùng |

## Git state reconstruction

- **STATE RECONSTRUCTION:** repo mới, chưa có commit; bằng chứng E01–E02/E05.
- **PROJECT IDENTITY:** `C:/Users/User/Desktop/TJ/Project/W23_AI-Business-Consulting-Lab`; repository tài liệu của TJ.
- **HUMAN SUMMARY:** Phase 0 được lưu thành file local; chưa có lịch sử Git hoặc backup được xác minh.
- **CURRENT CHECKOUT:** main chưa có commit; 11 file untracked, index trống.
- **REMOTE REFERENCE:** không cấu hình remote; không fetch hoặc kiểm chứng GitHub.
- **LOCAL WORK NOT YET REMOTE:** toàn bộ tài liệu local chưa commit; không có commit/nhánh đã commit để so với remote.
- **OTHER RELEVANT WORKTREES / BRANCHES:** một worktree; không có refs đã commit khác.
- **SAFE CONCLUSION:** repo độc lập đã khởi tạo, tài liệu có trên ổ đĩa; không được nói đã sao lưu hoặc đồng bộ.
- **NEXT ACTION:** giữ trạng thái hiện tại; chỉ làm Git mutation khác khi TJ yêu cầu.

## Quyết định và giới hạn

- **Đã duyệt:** TJ yêu cầu Phase 0 trong bootstrap ngày 2026-11-25, bao gồm tạo local repo; không commit/push.
- **Chưa duyệt:** Phase 1, khảo sát website/kênh, kiểm thử, liên hệ khách, chi phí/API, production và hợp đồng. Không có xác nhận của AIMICA.
- **Không có blocker cho Phase 0.** Việc thiếu local-orchestrator-cli không cản trở bộ tài liệu này.
- **TJ cần quyết định khi muốn tiếp tục:** có cho phép bắt đầu Phase 1 với AIM-01 hay chưa. Không cần quyết định thêm để đóng Phase 0.

Không có dependencies được cài, API trả phí, thay đổi production, lịch tự động, tiến trình nền hoặc file được sửa ngoài project trong Phase 0.
