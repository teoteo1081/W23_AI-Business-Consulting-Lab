# AIM-03 — Repository Security & GitHub Readiness Audit

> **Latest disposition:** TJ intentionally keeps W23 PUBLIC, preserves Git history, and permits Claude/Codex/AGY to read content reviewed as suitable for public access. See the final “content review” section. The earlier BLOCKED/FAIL labels below are the pre-decision checkpoint, not the current disposition. The 32-file content audit found no customer PII or credential; it did identify real bot outputs and public third-party policy/signatory data, with a narrower Claude handoff by purpose.

Ngày audit gốc: 2026-11-26 (Asia/Saigon). Người thực hiện: Codex. Chủ sở hữu/phê duyệt: TJ.
Mốc tham chiếu: `623c5185b98d5efc1131d8d5928779ae7891cd30`.
Tài liệu này lưu lại kết quả AIM-03 CHECKPOINT 01 đã báo trong hội thoại; được ghi file theo chỉ đạo tiếp theo “W23 — CONSOLIDATED CHECKPOINT & GITHUB READINESS”. Không phải bằng chứng TJ đã duyệt chia sẻ.

## A. Repository và checkpoint

- STATE RECONSTRUCTION / PROJECT IDENTITY: đúng W23_AI-Business-Consulting-Lab, repository tài liệu nghiên cứu của TJ, không phải source chatbot.
- HUMAN SUMMARY: tại audit gốc, working tree/index sạch; ba commit chỉ có local.
- CURRENT CHECKOUT: `main`, HEAD trùng mốc tham chiếu ở trên.
- REMOTE REFERENCE: không remote, upstream hoặc remote refs.
- LOCAL WORK NOT YET REMOTE: `83cd364` (Phase 0), `5c03fb9` (đóng AIM-01), `623c518` (Batch 01 PROVISIONAL).
- OTHER RELEVANT WORKTREES / BRANCHES: một worktree, một nhánh main.
- SAFE CONCLUSION: checkpoint tài liệu nguyên vẹn; `git fsck --full --no-reflogs` không báo lỗi. Git không bảo vệ bằng chứng bị ignore.
- NEXT ACTION: chuẩn bị gói chia sẻ đã được duyệt; không tự xuất bản.

Batch 01 vẫn PROVISIONAL: TC-01 PARTIAL discovery theo rubric nháp/PASS số liệu; TC-03A PASS phạm vi web/PARTIAL độ đầy đủ đối chiếu PDF; TC-03B PASS trong phạm vi đã thử. Không có Confirmed IT Defects hoặc nghiệm thu chính thức.

Transcript, ba ảnh và PDF khớp hash trong independent review trước. Evidence index và research review khác hash tại review trước; mô tả handoff ghi đã đối soát, nhưng không có manifest sau đối soát gắn với checkpoint Git để xác minh toàn bộ gói local tại thời điểm commit.

## B. Security findings

Đã kiểm tra 17 đường dẫn tracked, toàn bộ 28 blob, ba commit và metadata. Object store gồm 28 blob, 3 commit, 3 tree; không thấy object bổ sung ngoài lịch sử. Toàn bộ blob là văn bản.

| ID | Quan sát có bằng chứng | Ý nghĩa / điều kiện đóng |
|---|---|---|
| SEC-01 | Author/committer của cả ba commit có một email cá nhân; không ghi lại giá trị ở đây | Push lịch sử sẽ chia sẻ metadata đó. Cần TJ duyệt metadata hoặc chọn gói xuất có lịch sử mới; không rewrite repository gốc |
| SEC-02 | AIMICA_RESEARCH_REVIEW.md, mục 5–7, chứa chi tiết pilot/nhà cung cấp và đường dẫn workspace | Chưa xác minh quyền lưu ngoài máy. Cần phân loại và duyệt nội dung; chỉnh HEAD không loại bỏ phiên bản cũ |
| SEC-03 | AIM-02_HUMAN_REVIEW.md có trích lời bot; policy trong AGENTS/HANDOFF cấm hội thoại thật vào Git | Cần phân biệt tóm tắt ẩn danh được phép với trích lời thực tế; TJ chốt ngoại lệ hoặc chuẩn bị bản xuất phù hợp |
| SEC-04 | Không có PDF, ảnh, transcript JSON hoặc tài liệu khách gốc trong Git | Không thấy file bằng chứng gốc bị commit; không suy ra mọi câu chữ đều được phép chia sẻ |
| SEC-05 | Quét mẫu không phát hiện private key, token/API key phổ biến, JWT, URL credential, phép gán secret khả nghi hoặc định danh khách theo nhãn | Kết quả có giới hạn: không phải chứng nhận không có bí mật dưới mọi định dạng |
| SEC-06 | private/ có 32 file local: báo cáo, index, transcript, ảnh, PDF và ảnh trang | Đã inventory và kiểm hash nguồn liên quan; không tái kiểm duyệt trực quan toàn bộ ảnh/PDF trong AIM-03. Không đưa bản gốc vào Git |

Không trích credential, email cá nhân, hội thoại hay ảnh nhạy cảm vào báo cáo này. Hotline công khai và prompt giả lập không tự được phân loại là PII khách thật.

## C. GitHub readiness

**BLOCKED**: chưa có allowlist/approval cho nội dung và metadata lưu ngoài máy; repository chưa cung cấp đủ evidence cho review độc lập; tài liệu quản trị chưa đồng bộ quyền và trạng thái AIM-02. Private repository không thay thế quyền chia sẻ nội dung.

## D. Remediation đề xuất

1. Cập nhật trạng thái hiện hành; giữ snapshot lịch sử. Decision Log mới không được giả tạo ngày/phạm vi duyệt Batch 01 khi chỉ có báo cáo thuật lại.
2. Đánh dấu phần research review còn ghi chưa tải PDF/quyền chưa xác minh là snapshot cần đối chiếu.
3. Lập manifest evidence sau đối soát: phiên bản, hash, nguồn, redaction, quyền lưu/xem và thời hạn giữ. Hash tạo hôm nay không chứng minh trạng thái quá khứ.
4. Chốt SOP discovery, phạm vi ngoại lệ hợp đồng, rubric/ngưỡng, ground truth và người duyệt nghiệp vụ, context reset, human handoff. Giữ UNKNOWN khi thiếu nguồn.
5. Củng cố ignore; giữ private evidence trong private/; stage bằng allowlist cụ thể, không force-add.
6. Khuyến nghị gói xuất đã kiểm duyệt với lịch sử mới, giữ nguyên repository gốc. Chỉ push lịch sử gốc nếu TJ duyệt rõ cả nội dung lịch sử và metadata sau audit.

## E. Gói Independent Audit

Đọc [INDEPENDENT_AUDIT_PACKAGE.md](INDEPENDENT_AUDIT_PACKAGE.md). Governance/discovery/QA summaries đủ review logic; cần evidence theo ca được duyệt chia sẻ để kiểm chứng nguồn. Không coi báo cáo khác của AI là ground truth độc lập. PDF được báo cáo là nguồn công khai không tự cấp quyền sao chép ngoài máy.

## F. Kế hoạch PRIVATE GitHub và lệnh đề xuất

Chỉ sau khi TJ duyệt: chọn allowlist, chuẩn bị gói xuất, kiểm duyệt nội dung/metadata, kiểm tra lại bảo mật, tạo repository PRIVATE, xác minh visibility và người được xem, xin phê duyệt push trên đúng nội dung/commit/đích.

Lệnh sau chưa được chạy; placeholders cần thay bằng giá trị được TJ duyệt. Đây là phương án gói xuất riêng, không rewrite repository gốc:

```powershell
$reviewPath = '<TJ-approved-reviewed-export-directory>'
$remoteUrl = 'https://github.com/<OWNER>/<PRIVATE-REPOSITORY>.git'
git -C $reviewPath init -b main
git -C $reviewPath config user.name '<approved-name>'
git -C $reviewPath config user.email '<approved-noreply-email>'
git -C $reviewPath add -- <approved-file-1> <approved-file-2>
git -C $reviewPath diff --cached --stat
git -C $reviewPath diff --cached
git -C $reviewPath commit -m "docs: prepare approved independent review package"
# Sau khi xác minh repository đích là PRIVATE:
git -C $reviewPath remote add origin $remoteUrl
git -C $reviewPath remote -v
# Sau khi TJ duyệt đúng nội dung và thao tác push:
git -C $reviewPath push -u origin main
```

Audit gốc dừng tại AIM-03 CHECKPOINT 01, không ghi file/commit/push. Chỉ đạo tiếp theo cho phép lưu và hợp nhất tài liệu, commit có điều kiện PASS; không cấp quyền push. Trạng thái hợp nhất xem [CHECKPOINT_LOG.md](CHECKPOINT_LOG.md).

## Cập nhật xác minh thực tế — AIM-03 CHECKPOINT 02 (2026-11-26)

### Bằng chứng trạng thái

- Local root đúng W23; `main` sạch, `main` và `origin/main` cùng ở `9276976f547178cfe2893dfed8a4a4e1c2f8be92`; một worktree; remote `origin` trỏ đúng GitHub repository. GitHub REST API trả `visibility=public`, `default_branch=main`, `pushed_at=2026-11-26T07:45:15Z`; `gh repo view` cũng trả `PUBLIC`. HEAD GitHub trùng SHA local.
- Lịch sử có 7 commit, từ `83cd364` đến `9276976`; tất cả dùng metadata email cá nhân của TJ. GitHub API cho thấy commit mới nhất cùng metadata này.
- `git ls-tree -r HEAD` có **32 file** dưới `private/`; GitHub recursive tree có 38 entry gồm 32 blob/file + 6 thư mục. Đây là cùng nội dung, không phải 38 file. Bao gồm raw transcript JSON, 3 ảnh redacted, PDF quy tắc, text trích xuất, 22 ảnh trang và các báo cáo/index. API root còn liệt kê `private`. Những file này đang được phục vụ trong repo PUBLIC.
- Working tree sạch. `.gitignore` có `/private/` nhưng không tác dụng hồi tố với nội dung đã track. Kết quả remote tree mâu thuẫn trực tiếp với các phát biểu cũ “không có evidence trong Git” và “32 file local bị ignore”.

### Tái phân loại SEC

| ID | Trạng thái | Căn cứ / hệ quả |
|---|---|---|
| SEC-01 | **FAIL** | Email cá nhân có trong author/committer metadata của cả 7 commit trong lịch sử public. Không lặp lại giá trị tại đây. |
| SEC-02 | **NEEDS BUSINESS OWNER DECISION** | Tài liệu tracked có nội dung pilot/nhà cung cấp/đường dẫn. Chưa có phê duyệt chia sẻ; lịch sử public đã để lộ nội dung. |
| SEC-03 | **NEEDS BUSINESS OWNER DECISION** | Trích lời chatbot nằm trong nội dung tracked; chưa có quyết định cho phép công bố. |
| SEC-04 | **FAIL** | Raw transcript, ảnh, PDF nguồn và bản trích xuất hiện được track; khẳng định cũ rằng không có bằng chứng gốc trong Git là sai. Không kết luận PDF công khai đồng nghĩa được phép republication. |
| SEC-05 | **BLOCKED** | Quét giới hạn các pattern credential phổ biến trên 7 commit không có hit trong text blob; đây không phải secret scanner toàn diện và không kiểm tra đầy đủ binary/encoded/credential dạng khác. GitHub Secret Scanning và push protection đang disabled. Không kết luận repo sạch. |
| SEC-06 | **FAIL** | `private/` chứa 32 file tracked (38 tree entries tính cả 6 thư mục) trong commit/public tree; `.gitignore` không bảo vệ nội dung đã track. Chưa audit trực quan lại toàn bộ PDF/ảnh/transcript hoặc quyền chia sẻ. |

**Repository/public access:** **FAIL** so với mục tiêu kiểm soát chia sẻ; API xác nhận PUBLIC. Không kiểm tra được danh sách người đã xem/tải/copy/fork hoặc thu hồi bản sao. Mức lan truyền sau khi công khai là **BLOCKED/UNKNOWN**.

**Kết luận:** Security/sharing **BLOCKED — không PASS**. Không có hành động remediation tự động nào được thực hiện: không đổi visibility, xóa file, rewrite history, commit hay push. Cần TJ quyết định xử lý exposure và quyền chia sẻ trước mọi gói phát hành tiếp theo. Chỉ đổi sang PRIVATE (nếu được quyết định) không thu hồi các bản sao, không làm lịch sử an toàn và không tạo quyền chia sẻ.

**Phạm vi gói Independent Audit:** hiện chỉ là danh mục/chỉ dẫn local; không đủ điều kiện gửi hoặc mở quyền cho Claude. Cả root docs và primary evidence đang nằm trong repo PUBLIC; chưa có allowlist, phê duyệt quyền chia sẻ/retention, hoặc xác nhận các nội dung được trích dẫn và hình ảnh. Chỉ chia sẻ sau khi TJ duyệt danh sách file và kênh cụ thể, rồi kiểm tra gói đã sanitize; audit độc lập có thể bắt đầu bằng bộ tài liệu tối thiểu đã duyệt, không mặc định đưa raw evidence.

## Cập nhật disposition theo quyết định TJ — 2026-11-26

TJ xác nhận D1 giữ W23 PUBLIC có chủ đích, D2 giữ nguyên lịch sử, D3 cho phép Claude/Codex/AGY đọc tài liệu được xác nhận đủ điều kiện công khai. Các nhãn FAIL/BLOCKED trước đây về PUBLIC visibility, metadata email, presence của evidence trong Git và quyền đọc đã được giải quyết theo quyết định chủ repo; không coi email cá nhân hay tên thư mục là lỗi tự động. Không có file bị xóa hay lịch sử bị sửa. D1–D3 không tự xác nhận quyền tái xuất bản tài liệu của bên thứ ba hoặc chuyển mọi raw evidence sang Claude.

### Rà soát nội dung 32 file dưới `private/`

Đã đọc 4 tài liệu văn bản (3 báo cáo/summary + index CSV), đọc transcript JSON và xem cả 3 ảnh chat; xem trực quan bộ 22 trang render của PDF. Đếm khớp: 4 + 1 + 3 + 1 PDF + 1 text extract + 22 page renders = 32 file. Không phân loại theo tên thư mục.

| File / số lượng | Nội dung quan sát | Nhãn nội dung và kết luận chia sẻ |
|---|---|---|
| `AIM-02_INDEPENDENT_REVIEW_CODEX_2026-11-25.md` (1) | Phân tích của Codex về TC-01/03A/03B, giới hạn và giả thuyết | Owner-authored review; nhắc tới nội dung thật của chatbot pilot. Không thấy credential hoặc dữ liệu khách; không đưa vào Claude scope tối thiểu vì chưa cần nguồn pilot chi tiết |
| `AIMICA_RESEARCH_REVIEW_FULL.md` (1) | Tổng hợp nguồn công khai, quan sát UI, thông tin pilot/nhà cung cấp/vùng máy chủ và một số đường dẫn máy/workspace | Hỗn hợp public facts + owner research + metadata môi trường + mô tả vận hành pilot. Không thấy credential/PII khách; chi tiết “internal staff pilot” chưa được xác nhận công khai độc lập. Không đưa vào Claude scope hiện tại |
| `QA_HANDOFF_SUMMARY.md` (1) | Tóm tắt kết quả và câu hỏi từ ba test; có trích/diễn giải output chatbot | Test case là synthetic; output bot là nội dung hệ thống bên thứ ba thật. Không thấy thông tin định danh khách. Dùng trong repo theo D1/D2; không cần gửi raw/chi tiết cho Claude để review Business Brief |
| `evidence_index.csv` (1) | Ba dòng test, prompt giả lập, output thật, timestamp và đường dẫn local | Synthetic test data + owner metadata + third-party bot output. Path chứa tên tài khoản máy chung và cấu trúc workspace, không phải credential; không thấy khách thật |
| `raw/batch01_transcript.json` (1) | Ba lượt prompt giả lập và phản hồi thật từ bot | Không có dữ liệu khách thật/PII trong các lượt test; là raw third-party bot content. Không đưa vào handoff Claude |
| `redacted/TC-01.png`, `TC-03A.png`, `TC-03B.png` (3) | Screenshot Zalo chỉ hiển thị hội thoại bot; TC-01 còn thấy một câu hỏi FAQ trước đó; không thấy sidebar/tên người dùng hoặc thông tin khách | Synthetic prompt + phản hồi thật; account bot được nhận diện. Không có customer PII nhìn thấy. Không đưa ảnh gốc vào handoff Claude |
| `reference/QTBH_Tai_nan_Con_nguoi_toan_dien_2025.pdf` (1) | Quy tắc bảo hiểm AAA 22 trang, phát hành công khai; có thông tin liên hệ công ty, tên/chức danh/chữ ký người soạn–kiểm tra–phê duyệt và con dấu | Public corporate source; có personal information của người ký công khai, không phải thông tin khách bảo hiểm. Không thấy dữ liệu hợp đồng/khách hoặc credential. Quyền sao chép/phân phối lại chưa được rà soát; dùng link/citation thay gửi cả bản scan |
| `reference/QTBH_extracted.txt` (1) | Text extract chỉ có nhãn trang, không có nội dung OCR | Bản dẫn xuất từ PDF, không có dữ liệu bổ sung đáng kể |
| `reference/pages/page_01.png`–`page_22.png` (22) | Render của cùng policy; trang đầu có người ký/con dấu; phần còn lại là định nghĩa, điều khoản, thời hạn, danh mục hồ sơ và bảng tỷ lệ thương tật | Public corporate source lặp lại; tên/chữ ký của đại diện công ty là personal information công khai, không có hồ sơ người được bảo hiểm cụ thể. Trùng lặp PDF, không cần gửi Claude |

**Phân loại tổng hợp:**

- **Public information:** quy tắc AAA/địa chỉ, hotline và nội dung sản phẩm đã được công bố; nguồn sản phẩm công khai đã được dẫn trong report.
- **Owner-approved content:** chủ repo xác nhận repo giữ PUBLIC và lịch sử hiện tại; owner-authored discovery/QA analysis được giữ nguyên. Phê duyệt này không biến thông tin bên thứ ba thành nội dung do TJ sở hữu.
- **Synthetic test data:** ba prompt mô phỏng tình huống gia đình/bảo hiểm; không dùng hồ sơ hay danh tính khách thật.
- **Personal information:** không thấy PII khách hàng trong 32 file. Có email owner trong metadata Git (được TJ chấp thuận giữ theo D2); có tên/chữ ký công khai của nhân sự AAA trong policy.
- **Confidential third-party information:** không thấy tài liệu khách hàng, hồ sơ bồi thường thật hoặc dữ liệu được đánh dấu mật. Một số mô tả về pilot nội bộ/nhà cung cấp trong báo cáo là chi tiết vận hành bên thứ ba, chưa chứng minh là bí mật; không cần cho Business Discovery Brief nên loại khỏi handoff Claude.
- **Credentials/secrets:** không thấy credential trong nội dung 32 file; quét pattern credential giới hạn trên lịch sử text blob trước đó không có hit. Đây không phải chứng nhận quét mọi dạng binary/encoded secret.

### Hệ quả cho Independent Audit

Claude được giao review Business Discovery Brief bằng allowlist tài liệu công khai/owner-authored nêu trong HANDOFF.md. Không chuyển transcript JSON, CSV, ảnh chụp, PDF scan hoặc báo cáo chứa chi tiết vận hành pilot trong handoff này; các nguồn này không cần thiết cho câu hỏi review hiện tại. Đây là giới hạn tối thiểu theo mục đích, không phải kết luận rằng chúng là dữ liệu mật. Quyền công bố lại bản PDF bên thứ ba chưa được đánh giá; nếu cần citation thì dùng trang sản phẩm/nguồn chính thức thay bản scan.

**Trạng thái:** Không còn blocker security cần TJ quyết định cho Business Discovery Brief. Việc gửi khách/chạy workshop là quyết định kinh doanh riêng; xem mục bước tiếp theo trong HANDOFF.md. Không tự liên hệ khách, gửi file, hoặc chạy Batch 02.
