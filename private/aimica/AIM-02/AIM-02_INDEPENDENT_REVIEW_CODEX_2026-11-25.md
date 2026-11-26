# AIM-02 — Independent Evidence Review / Current-State Assessment v0.1

Ngày: 2026-11-25 (+07:00). Owner báo cáo: Codex; người yêu cầu/phê duyệt phạm vi review: TJ. Nhiệm vụ: chỉ Independent Review, không nhận lại nhiệm vụ live QA của AGY. Báo cáo nội bộ, chưa phải requirements hoặc kết luận được AIMICA/Business Owner phê duyệt.

## Kết luận để TJ quyết định

Ba cặp transcript–screenshot nhất quán trong vùng hiển thị. Đánh giá độc lập đề xuất: **TC-01 PARTIAL theo kỳ vọng discovery nháp; TC-03A PARTIAL về độ đầy đủ đối chiếu PDF; TC-03B PASS trong phạm vi giải thích hai điều kiện loại trừ đã hỏi.** Không có bằng chứng trong ba lượt này để kết luận PDF chưa được nạp, backend lỗi, nhiễu ngữ cảnh, hoặc bot đạt chất lượng tổng thể.

**Giới hạn về “đồng ý kết luận AGY”:** AIMICA_RESEARCH_REVIEW.md tự ghi là Step 0–2, trước live QA; evidence_index.csv vẫn ghi `Pending evaluation` cho cả ba dòng. Không có bảng kết luận/điểm AGY sau live test trong các file được cung cấp. Vì vậy, báo cáo này không gán cho AGY các kết luận FAIL/PARTIAL/PASS chưa thấy. Các nhận định TJ yêu cầu kiểm tra được đánh giá độc lập bên dưới; cần bảng chấm AGY cuối nếu muốn đối chiếu đồng thuận từng nhãn của AGY.

## Phạm vi, nguồn và phép kiểm tra

Đã đọc AGENTS.md, LAB_ANCHOR.md, PROJECT_STATUS.md, TASK_BOARD.md, HANDOFF.md và AIMICA_RESEARCH_REVIEW.md. Phạm vi mới do TJ giao cho phép review evidence; tài liệu điều phối cũ vẫn ghi AIM-02 chưa bắt đầu. Đây là chênh lệch thời điểm tài liệu, không đủ kết luận AGY kiểm thử trái phép. Giữ nguyên các file đó theo giới hạn hiện tại, không cập nhật trạng thái thay AGY.

Nguồn chính, đường dẫn tương đối từ thư mục báo cáo:

| ID | Nguồn đã kiểm tra | Điều chứng minh / giới hạn |
|---|---|---|
| E1 | [Transcript](raw/batch01_transcript.json), ba object case_id TC-01/TC-03A/TC-03B | Prompt, response, giờ gửi/chụp và nhãn cùng session do AGY ghi; không phải log backend |
| E2 | [Index](evidence_index.csv), ba dòng dữ liệu | Các trường chung khớp E1 hoàn toàn; observation vẫn Pending evaluation; không phải nguồn độc lập thứ hai cho nội dung response |
| E3 | [TC-01](redacted/TC-01.png), [TC-03A](redacted/TC-03A.png), [TC-03B](redacted/TC-03B.png) | Đã xem cả ba ảnh; nội dung hỏi–đáp khớp E1 trong vùng hiển thị, không thấy danh sách chat riêng bên trái. Ảnh chỉ xác nhận giờ ở độ phân giải phút, không xác thực mili giây trong JSON |
| E4 | [PDF AAA](reference/QTBH_Tai_nan_Con_nguoi_toan_dien_2025.pdf), 22 trang vật lý | Đọc bằng ảnh các trang 1, 6, 7, 8, 10, 11 liên quan; không tuyên bố đọc toàn bộ 22 trang |
| E5 | [Trang sản phẩm](https://aimica.vn/products/spbh-tai-nan-ho-gia-dinh), GET công khai HTTP 200 trong lượt audit | Kiểm bảng phí/STBH, cư trú, giới hạn lãnh thổ, loại trừ và link PDF; không dùng Chrome/CDP hoặc đăng nhập |
| E6 | [Baseline review](../../../AIMICA_RESEARCH_REVIEW.md), mục 3–5 | Rubric/Expected nội bộ sơ bộ, chưa được AIMICA phê duyệt; không có điểm live cuối |

PDF không có text layer trên cả 22 trang. Không dùng QTBH_extracted.txt làm ground truth. Đã render lại trong bộ nhớ sáu trang nêu trên từ PDF gốc và so từng pixel với PNG có sẵn: cả sáu khớp; sau đó đọc trực quan. Không tạo bản render mới. PDF công khai được trang sản phẩm liên kết có cùng SHA-256 với E4. Điều này xác minh đúng bản đối chiếu đang công khai, không chứng minh bản đó được áp dụng cho mọi hợp đồng hoặc đã có trong bot.

Tiêu chí hoàn thành review: mỗi test có đối chiếu E1/E3, Expected/Actual, nguồn nghiệp vụ, nhãn chắc chắn và giới hạn; có câu hỏi IT/Business và đúng ba thiết kế test tiếp theo. Kiểm định là L2 đối chiếu evidence, kèm xem xét các cách giải thích thay thế; **không chạy L3/live chatbot**. Không cần tái kiểm thử để hoàn thành phạm vi review này.

## Current-State Assessment v0.1 — kết quả từng test

### TC-01 — tư vấn gia đình, EV-TC-01

- **Expected nháp:** hỏi ưu tiên tai nạn/chi phí chữa bệnh, tuổi con và ngân sách trước khi chốt gói. Số người và tuổi vợ chồng đã có trong prompt; không nên bắt bot hỏi lại thông tin đã được cung cấp chỉ để đủ checklist.
- **Actual đã xác minh:** bot giới thiệu bảo hiểm tai nạn có điều kiện theo ưu tiên, đưa hai mức phí/STBH, nghiêng về một mức nếu phù hợp tài chính; sau đó hỏi ưu tiên và tuổi hai trẻ. Chưa hỏi ngân sách bằng khoảng tiền. Có lưu ý giới hạn quyền lợi và cư trú; không cam kết trả toàn bộ viện phí.
- **Đối chiếu nguồn:** hai mức 500.000/800.000 đồng/hộ/năm và 30/50 triệu đồng/người khớp E5. Minh họa tử vong do tai nạn theo STBH phù hợp Điều 4.1, trang PDF 7, trong phạm vi và điều kiện áp dụng. Chưa đủ dữ kiện để xác nhận gói thực sự phù hợp gia đình giả lập.
- **Chấm đề xuất:** PARTIAL cho discovery theo baseline nháp; PASS cho các con số được kiểm tra. Không gọi là FAIL nghiệp vụ chỉ vì thứ tự giới thiệu–hỏi lại. Bot có khuyến nghị sơ bộ, chưa chốt giao dịch hay xác nhận phù hợp cuối cùng.
- **VERIFIED FINDING:** gợi ý/khuyến nghị sơ bộ xuất hiện trước câu hỏi làm rõ; vẫn có hỏi lại, không phải hoàn toàn không discovery.
- **POTENTIAL IMPROVEMENT:** hỏi khoảng ngân sách và làm rõ ưu tiên sớm hơn; có thể thử cách diễn đạt/flow trước khi nghĩ đến sửa code.
- **NEEDS BUSINESS CONFIRMATION:** Sales Journey cho phép “gợi ý có điều kiện rồi hỏi” hay bắt buộc “hỏi đủ rồi mới khuyến nghị”? Khi nào được coi là chốt gói? Chưa có SOP/ngưỡng được duyệt.
- **Mức độ:** thấp, thuộc tối ưu trải nghiệm và tiêu chí kinh doanh chưa chốt. Không có bằng chứng mất khách, tư vấn sai giá hoặc thiệt hại.

### TC-03A — Thái Lan và nguồn điều khoản, EV-TC-03A

- **Expected nháp:** phân biệt phạm vi Việt Nam của sản phẩm chuẩn và khả năng phạm vi khác được ghi cụ thể trên hợp đồng/giấy chứng nhận; có căn cứ PDF.
- **Actual đã xác minh:** bot trả lời không thuộc phạm vi hiện cung cấp, dẫn mục giới hạn địa lý trên trang sản phẩm; thừa nhận chưa có số điều/khoản chính xác và chỉ kênh xem tài liệu/hỏi người thật. Không nhắc nhánh hợp đồng có phạm vi mở rộng.
- **Đối chiếu nguồn:** E5 giới hạn sản phẩm công khai tại Việt Nam. Điều 2, PDF trang 6, cho phép lãnh thổ khác khi hợp đồng/giấy chứng nhận quy định cụ thể. Ghi chú trang 8 mô tả khả năng thỏa thuận điều chỉnh phạm vi/loại trừ bằng văn bản có xác nhận hai bên. Không có hợp đồng cụ thể hoặc bằng chứng AIMICA đang bán mở rộng này.
- **Chấm đề xuất:** PASS cho giải thích phạm vi sản phẩm chuẩn trên website và sự thận trọng không bịa số điều; PARTIAL cho độ đầy đủ theo Expected kết hợp PDF. Không chấm FAIL chỉ vì không nói mọi khả năng của quy tắc khung: câu trả lời đã giới hạn vào phạm vi đang cung cấp.
- **VERIFIED FINDING:** thiếu dẫn Điều 2 và thiếu giải thích nhánh hợp đồng quy định lãnh thổ khác trong lượt này.
- **POTENTIAL IMPROVEMENT:** nêu giới hạn sản phẩm chuẩn, rồi yêu cầu kiểm hợp đồng/giấy chứng nhận nếu có thỏa thuận riêng; không hứa có thể mua mở rộng khi chưa xác nhận.
- **HYPOTHESIS:** PDF chưa được nạp. **Chưa được chứng minh.** Một câu trả lời thiếu citation không phân biệt được thiếu tài liệu, chưa truy xuất được, chưa có mapping điều khoản, hay lựa chọn trả lời chỉ theo sản phẩm đang bán. Đây là các khả năng phân biệt khi điều tra, không phải mô tả backend thực tế.
- **NEEDS BUSINESS CONFIRMATION:** bot chỉ tư vấn gói tiêu chuẩn hay phải giải thích ngoại lệ hợp đồng? Có được cung cấp/mở rộng phạm vi ngoài Việt Nam không, ai xác nhận?
- **Mức độ:** thấp cho thiếu citation đơn thuần; có thể trung bình về tính đầy đủ nếu nhiệm vụ tư vấn hợp đồng mở rộng được xác nhận. Chưa có bằng chứng từ chối bồi thường sai hoặc thiệt hại thực tế.

### TC-03B — rượu bia và điều kiện loại trừ, EV-TC-03B

- **Expected nháp:** không tự động kết luận từ việc đã uống rượu bia; giữ điều kiện quan hệ nguyên nhân và phân biệt loại trừ vi phạm giao thông.
- **Actual đã xác minh:** bot trích cả hai loại trừ, nêu rõ điều kiện rượu bia là nguyên nhân dẫn đến tai nạn, nhắc cần đối chiếu riêng vi phạm an toàn giao thông. Không tự đặt ngưỡng nồng độ cồn; hướng dẫn kiểm quy tắc và xác nhận trường hợp cụ thể.
- **Đối chiếu nguồn:** nội dung khớp Điều 9.2–9.3, PDF trang 7. Điều 16, trang 10–11, quy định hồ sơ liên quan tai nạn và giấy phép lái xe theo trường hợp, giúp thấy cần thông tin hồ sơ chứ không chỉ một câu mô tả. Đây không phải kết luận pháp lý về trách nhiệm trong một vụ tai nạn thật.
- **Chấm đề xuất:** PASS cho nội dung điều kiện loại trừ và xử lý chưa đủ dữ kiện trong lượt này. Không mở rộng PASS thành xác nhận toàn bộ nghiệp vụ bồi thường, mọi ngưỡng luật giao thông hay khả năng dẫn đúng số điều.
- **VERIFIED FINDING / điểm tốt:** đã nêu đúng điều kiện nguyên nhân và hai căn cứ loại trừ riêng. Khẳng định “bot bỏ điều kiện nguyên nhân” sẽ trái với E1/E3/E4.
- **POTENTIAL IMPROVEMENT:** bổ sung số Điều 9.2–9.3 và bước thu thập thông tin/handoff được Business duyệt; không mặc định phải viết code mới.
- **Mức độ:** không thấy lỗi nội dung được hỏi; không có căn cứ gán mức nghiêm trọng cao. Cần giữ sự thận trọng, tránh biến câu hỏi về điều kiện thành cam kết có/không chi trả khi thiếu hồ sơ.

### Context — có phải nhiễu hội thoại?

E1 ghi rõ ba lượt diễn ra tuần tự trong cùng session; ảnh cho thấy bong bóng trả lời trước phía trên. TC-01 còn có một đoạn chat cũ trước batch ở phần trên ảnh, nhưng không có đầy đủ lịch sử trong E1. Hiển thị lịch sử trên Zalo không tự chứng minh nội dung nào được truyền vào model.

Các câu trả lời của ba lượt vẫn tập trung vào sản phẩm/tình huống đang hỏi. Lời lưu ý viện phí trong TC-01 có liên quan tới giới hạn sản phẩm dù không được hỏi trực tiếp; chưa đủ chứng minh bị nhiễu. Nhắc nội dung trước, nếu có, có thể là duy trì hội thoại bình thường. **HYPOTHESIS: context contamination — chưa xác minh.** Chưa có cặp context sạch/context cũ đối chứng, chưa thấy dữ kiện lỗi thời làm thay đổi câu trả lời trái yêu cầu mới. Cũng không thể kết luận cơ chế memory hoạt động tốt từ ba lượt này.

## Những điểm bot đang làm tốt

- Câu trả lời tiếng Việt bám câu hỏi, có bước hỏi lại thay vì chỉ đưa sản phẩm.
- Giá/STBH được nêu trong TC-01 phù hợp nguồn web đã kiểm; có phân biệt phí theo hộ và quyền lợi theo người.
- TC-03A dùng phạm vi sản phẩm công khai, thừa nhận thiếu số điều thay vì bịa dẫn chứng.
- TC-03B giữ điều kiện nguyên nhân, nêu vi phạm giao thông riêng và tránh tự đưa ngưỡng cồn.
- Có hướng dẫn tra tài liệu và kênh liên hệ; đây mới là handoff bằng lời, chưa kiểm chứng chuyển live agent hay khả năng xử lý thực tế.

Không suy ra an toàn dữ liệu, độ chính xác toàn danh mục, conversion, chất lượng handoff hoặc readiness từ ba lượt này.

## Các kết luận vượt bằng chứng cần tránh

| Nhận định cần kiểm tra | Ý kiến audit |
|---|---|
| Đề xuất sản phẩm trước câu hỏi luôn là lỗi | Không đồng ý như quy tắc chung; chưa có quyết định Sales Journey. Quan sát thứ tự là đúng, đánh giá thiết kế phải được Business chốt |
| Không dẫn Điều 2 chứng minh PDF chưa nạp KB | Không đồng ý; chỉ xác minh được thiếu citation/nhánh ngoại lệ ở lượt đó |
| TC-03B bỏ điều kiện nguyên nhân hoặc cứ uống là bị loại trừ | Không đồng ý; transcript và screenshot cho thấy bot giữ đúng điều kiện, đồng thời nhắc loại trừ giao thông |
| Nội dung chat trước xuất hiện là context contamination | Không đồng ý nếu chỉ dựa ảnh/history; cần chứng minh sai lệch do context |
| TC-03B PASS nghĩa bot chính xác toàn bộ | Không đồng ý; PASS bị giới hạn vào hai điều kiện được kiểm tra |
| PDF đã xác minh “100%” cho mọi tình huống sản phẩm | Quá rộng; bản PDF được xác minh nguồn, nhưng hợp đồng cụ thể, thỏa thuận khác và policy Business vẫn chưa có |

Đây là nhận xét đối với các mệnh đề, không phải xác nhận AGY đã thực sự viết chúng trong một bản kết luận live chưa được cung cấp.

## Những vấn đề đáng hỏi IT

1. **Nguồn và phiên bản:** bot pilot đang được cấu hình dùng những nguồn sản phẩm nào, phiên bản/ngày hiệu lực nào? Có thể cung cấp danh mục nguồn/metadata đã làm sạch cho đúng thời điểm batch không? Không yêu cầu nội dung người dùng hoặc secrets.
2. **PDF và citation:** PDF 22 trang này đã được đưa vào phạm vi tri thức được phép sử dụng chưa? Nếu có, nội dung bản scan được xử lý thế nào, có kiểm đọc được Điều 2 và Điều 9.2–9.3 không? Việc bản gốc không có text layer là quan sát, không chứng minh hệ thống thiếu OCR hay nạp lỗi.
3. **Dấu vết câu trả lời:** nếu hệ thống có tracing/retrieval logs, có thể cung cấp các nguồn/đoạn đã dùng cho TC-03A, bỏ dữ liệu cá nhân? Có quy tắc chỉ theo gói đang bán hoặc hạn chế dẫn số điều không? Không mặc định hệ thống dùng RAG hoặc kiến trúc cụ thể.
4. **Session:** định nghĩa một phiên chat, cách bắt đầu context sạch và tác động của thao tác reset được hỗ trợ là gì? Không tự reset phiên để kiểm tra.
5. **Handoff:** bot chỉ hiển thị kênh liên hệ hay có đường chuyển người thật? Cách kiểm thành công và giới hạn pilot là gì?

Ưu tiên điều tra nguồn/metadata/quy tắc nội dung trước đề xuất thay model, xây RAG hay viết tính năng mới. IT xác minh cơ chế; IT không tự quyết định đáp án bảo hiểm hoặc SOP bán hàng.

## Quyết định cần Business Owner xác nhận

1. Chấp nhận gợi ý có điều kiện trước discovery hay bắt buộc hỏi đủ? Thông tin tối thiểu nào cần có trước khuyến nghị, không cần hỏi lại dữ kiện khách đã cung cấp?
2. Thứ tự ưu tiên giữa trang sản phẩm, quy tắc khung và điều khoản hợp đồng/thỏa thuận riêng; ai chịu trách nhiệm duyệt đáp án chuẩn? Đối tượng pilot là nhân viên nội bộ hay khách mua cũng cần được xác nhận trước dùng kết quả để đánh giá hành trình khách hàng.
3. Có bán/hỗ trợ phạm vi ngoài Việt Nam cho gói này không? Bot có nhiệm vụ giải thích nhánh hợp đồng mở rộng hay chỉ chuyển chuyên viên?
4. Ca rượu bia/giao thông cần hỏi những thông tin nào, mức kết luận bot được phép đưa ra và điểm chuyển người thật là gì? Bộ ví dụ và đáp án cần chuyên viên nghiệp vụ/đơn vị bảo hiểm có thẩm quyền xác nhận.
5. Rubric và ngưỡng chấp nhận nào được duyệt? Điểm hiện tại chỉ là đánh giá nghiên cứu, không phải nghiệm thu. Chưa có bằng chứng AIMICA đã duyệt các thay đổi hoặc yêu cầu mới.

Các cải tiến có thể chỉ cần chỉnh nội dung nguồn, mẫu trả lời, liên kết citation, flow/prompt hoặc SOP; chỉ chọn giải pháp sau khi xác minh nhu cầu và cơ chế hiện có.

## Nếu chỉ chọn ba bài kiểm thử tiếp theo

Đây là ba **thiết kế test**, có thể gồm nhiều nhánh đối chứng; chưa được chạy, chưa cấp quyền live. Chốt số lượt, scope, đáp án nghiệp vụ và quyền gửi trước khi thực hiện.

| Ưu tiên | Thiết kế | Expected đề xuất / giá trị phân biệt |
|---|---|---|
| 1 | Phạm vi địa lý: cùng câu hỏi Thái Lan, đối chiếu gói tiêu chuẩn với tình huống giả lập có hợp đồng ghi rõ lãnh thổ khác, và một nhánh chưa biết điều khoản | Phân biệt sản phẩm chuẩn với quy tắc khung; dẫn đúng Điều 2/nguồn hoặc thừa nhận giới hạn; không hứa mở rộng đang bán. Giải quyết gap TC-03A mà không cần suy đoán KB |
| 2 | Loại trừ có điều kiện: các tình huống giả lập đã được nghiệp vụ duyệt để tách quan hệ nguyên nhân rượu bia, vi phạm giao thông và dữ kiện chưa đủ | Giữ nguyên hai căn cứ độc lập, không suy “không phải nguyên nhân thì chắc chắn được trả”, không tự đặt ngưỡng cồn. Kiểm ranh giới quyết định có ảnh hưởng bồi thường thay vì chỉ lặp lại câu trích đúng |
| 3 | Discovery trong context sạch và context có gợi ý tai nạn cũ: dùng cùng yêu cầu mới ưu tiên chi phí chữa bệnh/nằm viện, yêu cầu xem xét lại lựa chọn trước | Phân biệt duy trì hội thoại hữu ích với bám dữ kiện lỗi thời; hỏi thông tin thiếu và điều chỉnh gợi ý theo nhu cầu mới. Chấm trình tự theo SOP Business đã duyệt, không theo sở thích auditor. Cần IT chỉ cách tạo context sạch hợp lệ; không dùng dữ liệu thật |

## Dấu vết kiểm tra và bảo toàn

Snapshot Git: đúng root W23_AI-Business-Consulting-Lab, main @ `5c03fb9b43055c3415d406708944ae4984f80cba`, một worktree, không remote/upstream. AIMICA_RESEARCH_REVIEW.md đã untracked trước audit; không sửa file đó. Không fetch do không remote; không stage/commit/push. Báo cáo này nằm trong private/ bị ignore, chưa có backup Git; không force-add.

Các trường bắt buộc của state recovery: STATE RECONSTRUCTION = kiểm trực tiếp và helper chỉ đọc; PROJECT IDENTITY = root TJ chỉ định; HUMAN SUMMARY = checkpoint AIM-01 và evidence AIM-02 local; CURRENT CHECKOUT = main/SHA trên; REMOTE REFERENCE = không có; LOCAL WORK NOT YET REMOTE = hai commit local và file review untracked; OTHER RELEVANT WORKTREES / BRANCHES = chỉ main/một worktree; SAFE CONCLUSION = tài liệu điều phối cũ chưa phản ánh batch mới; NEXT ACTION = TJ đọc audit, không tự tiếp tục live QA.

SHA-256 nguồn để phát hiện thay đổi trong lúc audit:

| Nguồn | SHA-256 |
|---|---|
| AGENTS.md | 70296d847051980cec65955738715ba330bc065f06ddfad4dd89034a5a50c7ac |
| LAB_ANCHOR.md | 9b98f27ac4b65d54da1d6e3e9db033c5db3a972e1a1ccab3b0d5382015f5be7e |
| AIMICA_RESEARCH_REVIEW.md | 3d30eb9426743feb13a0287d757a368bf534b8f846212316acd4de83ec3aafac |
| raw/batch01_transcript.json | 328ebacb4c2919ac6662e85db72d66868dbf414c0505bfa8b8dfc86739966284 |
| evidence_index.csv | 47717f7d211a9238e2e25b0037b6a01953f4ba9e4c735e920fb4d7c4ce1fcfdb |
| redacted/TC-01.png | 3af2d16bc3b26d92adcbcb84b09df99260a2e2500ae96c54092ede5afb68321f |
| redacted/TC-03A.png | 535c6c82141fd25d8de8e733541ee62801a40c6299c148aaae6af5fbb7827b29 |
| redacted/TC-03B.png | 75ceafa510c7ceae69dfd03fb009e6b3861f29a9c43c3dc8f90a02dc336083d6 |
| reference/PDF AAA | fbc62fd2891f4745e70d007dc2ca1c81042aa4eb100e68bb8dec11009deee8e2 |
| HTML trang sản phẩm, GET trong audit | 24cf1f2788303f6d2d3db22a71e991f0aa648d0830c41f08cd75e6a7242728f5 |

Mốc thu metadata trong audit: 2026-11-25T05:10:09Z (12:10:09 +07:00). Không lưu thêm HTML/PDF tải về; checksum nguồn web chỉ định danh response tại lần đọc, không thay bản lưu lịch sử website tại giờ live test. Nguồn web có thể đổi sau audit.

Execution: **SUCCESS trong phạm vi Independent Review**. Bằng chứng hỗ trợ đối chiếu nội dung ba ca; **INSUFFICIENT_EVIDENCE** để xác nhận điểm cuối của AGY, nguyên nhân backend, context contamination hoặc chất lượng tổng thể. Nhãn đề xuất là đánh giá độc lập của Codex so với evidence do AGY thu, không phải live test tái lập, không phải blind calibration hay review thêm bởi người thứ ba. Dừng sau báo cáo này; không tự sửa bot, tài liệu AGY, automation hoặc chạy ba test đề xuất.
