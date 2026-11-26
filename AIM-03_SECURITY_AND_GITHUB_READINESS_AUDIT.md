# AIM-03 — Repository Security & GitHub Readiness Audit

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
