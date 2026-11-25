# Project Status

## Hiện tại — đóng AIM-01 / chuẩn bị AIM-02 — 2026-11-25

- **AIM-01: CLOSED / DONE.** TJ đã xem báo cáo và chốt ưu tiên trong chỉ đạo “AIM-01 — DISCOVERY DECISION & CHECKPOINT”. Đóng nhiệm vụ nghiên cứu/tài liệu; không đồng nghĩa đã phỏng vấn khách hoặc khách duyệt requirements.
- **Human Review:** [HUMAN_REVIEW.md](HUMAN_REVIEW.md), bản ngắn tối đa một trang đọc; tổng hợp ba tài liệu và các quyết định còn thiếu.
- **AIM-02:** Current Chatbot QA Evidence Collection, owner dự kiến AGY, WAITING_AUTHORIZATION. Chỉ lập nhiệm vụ/handoff; chưa chạy Zalo, chưa có evidence hay kết quả QA. Nguồn, mục tiêu và nơi lưu nằm ở HANDOFF.md.
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
