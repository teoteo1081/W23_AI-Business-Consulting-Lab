# W23 — Quyết định TJ và mục còn cần chốt

**Cập nhật:** 2026-11-26 · Các quyết định D1–D3 đã được TJ xác nhận.

## Đã quyết định

- **D1 — PUBLIC: APPROVED.** W23 được giữ PUBLIC có chủ đích.
- **D2 — lịch sử: APPROVED.** Giữ nguyên lịch sử Git; không rewrite/force push.
- **D3 — đọc tài liệu: APPROVED có điều kiện.** Claude, Codex và AGY được đọc các tài liệu đã được kiểm tra là phù hợp công khai. Không suy ra quyền tái xuất bản mọi nội dung bên thứ ba từ visibility hoặc quyền đọc.

Rà soát 32 file dưới `private/` theo nội dung: không thấy dữ liệu khách thật hay credential; ba test dùng prompt giả lập, output là phản hồi thật của bot; PDF AAA là tài liệu chính thức được công bố, gồm thông tin liên hệ và tên/chữ ký người đại diện của công ty. Báo cáo AIMICA cũ có chi tiết pilot nội bộ, nhà cung cấp/vùng máy chủ và đường dẫn workspace; không đưa phần đó vào handoff Claude. Chi tiết phân loại ở [AIM-03 security review](AIM-03_SECURITY_AND_GITHUB_READINESS_AUDIT.md).

## Một quyết định kinh doanh còn cần TJ

**Có ủy quyền buổi Business Discovery với AIMICA không?**

- **Vì sao:** cần người có thẩm quyền xác nhận mục tiêu, vấn đề ưu tiên, KPI nền và quyền dữ liệu trước Gap Analysis/ROI/Proposal.
- **Lựa chọn:** (A) duyệt TJ dùng brief để mời/trao đổi với đầu mối AIMICA; (B) chỉ giữ brief làm chuẩn bị nội bộ, chưa liên hệ.
- **Khuyến nghị:** A sau khi TJ chỉ định đầu mối và người tham gia; dùng bản brief hiện tại làm agenda, không cam kết giải pháp/chi phí.
- **Nếu chưa quyết định:** tiếp tục giữ AIMICA findings là giả thuyết/PROVISIONAL; không gửi brief hoặc liên hệ khách.

Đây là bước quyết định kinh doanh/quyền liên hệ, không phải blocker bảo mật repo. Không có quyết định D1–D3 nào còn chờ.
