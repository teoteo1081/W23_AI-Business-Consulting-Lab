# AIMICA — ba use case để khảo sát tiếp

Ngày: 2026-11-25. Tất cả là **HYPOTHESIS / NEEDS CLIENT CONFIRMATION**. Đây là thứ tự nghiên cứu đề xuất, chưa phải backlog triển khai, yêu cầu IT hay lựa chọn khách đã duyệt. Không có thử nghiệm AI/application hoặc lời hứa ROI.

Nguồn quan sát công khai nằm ở [INDUSTRY_BRIEF.md](INDUSTRY_BRIEF.md); câu hỏi để xác nhận nằm ở [DISCOVERY_QUESTIONS.md](DISCOVERY_QUESTIONS.md). Phân tích bên dưới là thiết kế giả thuyết của Lab, không mô tả hệ thống AIMICA hiện có.

## Cách chọn hướng nghiên cứu

**Quyết định mới của TJ ngày 2026-11-25 thay thứ tự đề xuất ban đầu:** ưu tiên đánh giá chatbot Zalo hiện hữu từ góc nhìn khách mua. Đây là QA hiện trạng, không phải xây UC2. Sales/CTV (UC1) và quản lý KPI (UC3) là hướng phụ, chưa chốt triển khai. Bảng và giải thích ưu tiên bên dưới được giữ làm lập luận ban đầu của Lab, không phải ưu tiên hiện hành. Xem Decision Log trong PROJECT_STATUS.md.

Ưu tiên công việc cụ thể, có đầu ra kiểm tra được, nguồn tri thức quản lý được và con người giữ quyền quyết định. Chưa đủ dữ liệu để xếp hạng ROI. Đề xuất xem UC1 trước vì có thể khoanh phạm vi nội bộ và quan sát giá trị qua công việc sales; nếu khách không có tài liệu/người duyệt, chưa có cơ sở thử nghiệm.

| Ưu tiên | Use case và người dùng | Giá trị giả thuyết | Dữ liệu/phụ thuộc chính | Lý do chưa triển khai |
|---|---|---|---|---|
| 1 | UC1 — trợ lý tra cứu và chuẩn bị tư vấn cho sales/CTV | Giảm tra cứu, giảm nội dung dùng sai phiên bản | Nguồn sản phẩm được duyệt và người kiểm duyệt | Chưa biết độ tin cậy tài liệu, khối lượng công việc và quyền truy cập |
| 2 | UC2 — trợ lý hỏi nhu cầu, giải thích và chuyển chuyên viên cho khách | Khách dễ hiểu và giảm lặp thông tin khi chuyển tiếp | Tri thức được duyệt, quy tắc hỏi/chuyển, consent | Chưa xác nhận kênh và ranh giới tư vấn |
| 3 | UC3 — bản tóm tắt funnel và việc cần xem cho quản lý | Giảm thời gian tổng hợp, phát hiện nơi cần kiểm tra | Định nghĩa KPI, CRM/đối soát và phân quyền | Chưa biết dữ liệu có liên kết và thống nhất không |

## UC1 — trợ lý nội bộ hỗ trợ sales/CTV

- **Công việc nhỏ để khảo sát:** sales tìm điều khoản/FAQ đúng phiên bản cho một dòng sản phẩm, lấy câu trả lời có nguồn và bản nháp checklist trao đổi; sales kiểm tra trước khi dùng.
- **Tại sao chọn:** dễ tách nội dung hỗ trợ nội bộ khỏi quyết định gửi khách; có thể đo thời gian tra cứu và chất lượng bản nháp. Đây là giả định về tính khả thi, chưa được xác nhận với AIMICA.
- **Giá trị kinh doanh cần kiểm chứng:** giảm công sức mỗi ca tra cứu mà không tăng sai sót hoặc công kiểm duyệt. Không mặc định làm sales giỏi hơn sẽ tăng doanh số ngay.
- **Công nghệ có thể cần:** trước hết tìm kiếm/tài liệu tập trung. Nếu cần hiểu câu hỏi tự nhiên, cân nhắc LLM kèm truy xuất nguồn (RAG), metadata phiên bản, kiểm soát quyền và lưu dấu nguồn. Báo phí dùng công cụ/quy tắc được chủ sản phẩm chấp thuận, không để LLM tự tính hoặc tự đặt giá.
- **Dữ liệu:** điều khoản và FAQ đã duyệt, ngày hiệu lực, chủ nội dung, tài liệu đào tạo, quy tắc vai trò. Chưa cần dữ liệu khách thật ở bước nghiên cứu đầu.
- **Rủi ro:** trả lời có vẻ đúng nhưng nguồn không hỗ trợ; trộn phiên bản; bỏ sót loại trừ; lộ chính sách nội bộ; sales sao chép bản nháp không kiểm tra.
- **Con người phê duyệt:** chủ nội dung duyệt kho tri thức; người có trách nhiệm tư vấn duyệt đầu ra trước khi gửi khách; quản lý duyệt ngoại lệ.
- **Cần khách xác nhận:** Q05/Q07/Q12–Q14; một loại việc, một nhóm sản phẩm, người duyệt, mẫu câu hỏi và phạm vi quyền.
- **Cách đo đề xuất:** thời gian tra cứu trung vị, câu được chuyên gia xác nhận đúng, lỗi nghiêm trọng, thời gian sửa bản nháp. So với cùng bộ việc dùng công cụ hiện tại; chưa có số liệu nền/ngưỡng.
- **Điều kiện dừng:** thiếu nguồn có chủ sở hữu hoặc không có người xác nhận đúng; chưa chuyển thành thử nghiệm.

## UC2 — hỗ trợ khách hiểu nhu cầu và chuyển người

- **Công việc nhỏ để khảo sát:** giải thích khái niệm thuộc FAQ đã duyệt, hỏi thông tin tối thiểu cần làm rõ và tạo tóm tắt bàn giao có consent. Không tự quyết định sản phẩm phù hợp, phí, nhận bảo hiểm hay bồi thường.
- **Tại sao chọn:** tập trung vào một điểm trong journey thay vì bot trả lời mọi thứ; có thể kiểm tra cả hữu ích lẫn chuyển đúng người.
- **Giá trị cần kiểm chứng:** khách hoàn thành bước tìm hiểu dễ hơn, chuyên viên giảm hỏi lặp; chuyển đổi chỉ là kết quả cần đo sau, không phải cam kết.
- **Công nghệ có thể cần:** FAQ/tìm kiếm hoặc biểu mẫu dẫn dắt có thể đủ. Khi hội thoại biến thiên nhiều, cân nhắc LLM + truy xuất nguồn, kiểm tra trường dữ liệu, cơ chế chuyển người và phân quyền. Tích hợp kênh/CRM là phụ thuộc chưa được phép thực hiện.
- **Dữ liệu:** câu hỏi đã ẩn danh, nội dung được duyệt, trường tối thiểu, danh sách tình huống phải chuyển người, người nhận và thời gian xử lý. Không tự thu dữ liệu sức khỏe/định danh.
- **Rủi ro:** hứa quyền lợi không tồn tại, hỏi quá nhiều dữ liệu, tạo kỳ vọng được bồi thường, giữ khách trong bot quá lâu, tóm tắt sai. Từ chối tất cả cũng không giải quyết được nhu cầu.
- **Con người phê duyệt:** chủ nghiệp vụ duyệt phạm vi trả lời; chuyên viên xử lý tình huống vượt quyền; khách tự xác nhận thông tin và quyết định mua; các quyết định chính thức theo quy trình có thẩm quyền.
- **Cần khách xác nhận:** Q03–Q06/Q11–Q14; ai dùng, kênh nào, quyền xử lý dữ liệu, trách nhiệm và khả năng tiếp nhận handoff.
- **Cách đo đề xuất:** hoàn thành job tìm hiểu, trả lời đúng, chuyển đúng/nhầm, tóm tắt đủ và mức hỏi lặp; không tối ưu riêng tỷ lệ giữ khách trong bot.
- **Điều kiện dừng:** chưa có nơi nhận chuyển tiếp hoặc chưa chốt ranh giới tư vấn và dữ liệu.

## UC3 — hỗ trợ quản lý đọc funnel và chuẩn bị hành động

- **Công việc nhỏ để khảo sát:** từ báo cáo có định nghĩa và quyền truy cập rõ, tạo tóm tắt số liệu và câu hỏi cần quản lý xem; mọi con số truy ngược được về báo cáo nguồn.
- **Tại sao chọn:** hỗ trợ quản lý hiểu hoạt động của đội; phát hiện nhu cầu thật trước khi chọn dashboard, automation hoặc AI.
- **Giá trị cần kiểm chứng:** giảm công tổng hợp, rút ngắn thời gian nhận biết hồ sơ tồn; chưa chứng minh tác động doanh thu.
- **Công nghệ có thể cần:** bảng tính/BI và quy tắc định kỳ có thể đủ. Chỉ cân nhắc LLM cho diễn giải, không giao LLM tính KPI hay tự truy vấn tùy ý. Cần lớp tính toán có kiểm tra, data dictionary và phân quyền; chưa xây hoặc chạy lịch.
- **Dữ liệu:** trạng thái lead/đơn/hợp đồng, thời gian, owner, định nghĩa doanh thu và hoàn/hủy; bảng liên kết ẩn danh được phép dùng.
- **Rủi ro:** đếm trùng, nhầm phí thu hộ với doanh thu, so sai cohort, lộ thu nhập CTV; kết luận thiếu công bằng về nhân sự từ dữ liệu thiếu.
- **Con người phê duyệt:** người quản lý dữ liệu xác nhận KPI; quản lý kinh doanh duyệt hành động; tài chính duyệt đối soát/chi trả. Không tự phân bổ lead, phạt hay xếp loại nhân sự.
- **Cần khách xác nhận:** Q08–Q10/Q12/Q14–Q15; nguồn chính, owner, định nghĩa và mức dữ liệu được xem.
- **Cách đo đề xuất:** số liệu khớp nguồn, thời gian soạn báo cáo, nhận định có căn cứ và công sửa; “phát hiện bất thường” phải được quản lý xác minh.
- **Điều kiện dừng:** chưa thống nhất KPI hoặc không nối được trạng thái theo thời gian. Làm rõ dữ liệu trước khi thêm AI.

## 5 kiến thức Business/AI dành cho TJ

### 1. Mô hình kinh doanh là ai tạo giá trị, ai trả tiền và ai chịu trách nhiệm

Đừng dùng tổng phí bảo hiểm làm doanh thu nền tảng. **Ví dụ giả định hoàn toàn:** khách đóng 1.000.000 đồng, đơn vị phân phối nhận 80.000 đồng và mất 30.000 đồng chi phí phục vụ; phần còn lại trước các khoản khác là 50.000 đồng, không phải 1.000.000 đồng. Các con số này không phải chính sách AIMICA. Discovery phải tìm đúng dòng tiền trước khi tính ROI.

### 2. Journey và funnel trả lời hai câu hỏi khác nhau

Journey mô tả người dùng cần làm gì và gặp khó ở đâu; funnel đo số người đi qua từng bước. **Ví dụ giả định:** 100 lead có 40 lead đủ điều kiện, tạo 10 hợp đồng hiệu lực; tỷ lệ trên lead đủ điều kiện là 10/40 = 25%, trên tổng lead là 10/100 = 10%. Nếu không chốt mẫu số và cửa sổ thời gian, hai báo cáo đều có thể trông hợp lý nhưng không so sánh được.

### 3. “Thông minh” phải gắn với công việc và bằng chứng

Một câu trả lời trôi chảy chưa chứng minh tư vấn tốt. **Ví dụ giả định:** khách hỏi một tình huống có được chi trả không; AI hữu ích cần xác định đúng sản phẩm, phiên bản và dữ kiện còn thiếu, giải thích theo nguồn hoặc chuyển người. Câu khẳng định chắc chắn thiếu căn cứ có thể nguy hiểm hơn việc hỏi lại. Đo cả chất lượng, lỗi, thời gian và chi phí kiểm duyệt; bộ đo ở DISCOVERY_QUESTIONS.md còn cần khách chốt.

### 4. RAG cung cấp nguồn tham chiếu, không bảo đảm AI hiểu đúng

RAG là tìm phần tài liệu liên quan rồi đưa cho mô hình để soạn câu trả lời. **Ví dụ giả định:** lấy nhầm điều khoản cũ vẫn có thể tạo câu trả lời sai kèm trích dẫn. Vì vậy cần phiên bản, quyền truy cập, người sở hữu nội dung và kiểm tra nguồn có thật sự hỗ trợ kết luận. Nếu một trang FAQ có tìm kiếm đã đủ, chưa cần dùng LLM.

### 5. Human-in-the-loop là quyền quyết định có người chịu trách nhiệm

Không chỉ thêm nút “chuyển người”. Phải xác định ai nhận, nhận thông tin gì, trong bao lâu và ai có quyền phê duyệt. **Ví dụ giả định:** AI chuẩn bị checklist hồ sơ; người nghiệp vụ xác nhận và hệ thống chính thức quyết định theo quy trình. Thưởng sales chỉ theo số đơn cũng có thể lệch mục tiêu chất lượng, nên đo sai sót/hủy/khiếu nại cùng hiệu suất. Đây là rủi ro cần hỏi, không phải cáo buộc AIMICA.

## Quyết định tiếp theo đề xuất

TJ đã chọn hướng QA chatbot Zalo hiện hữu; AIM-02 được chuẩn bị nhưng chưa được bắt đầu. TJ cần chốt đúng bot, phạm vi, quyền kiểm tra và nguồn đối chiếu trước lệnh thực hiện. Sales/CTV và KPI tiếp tục là nghiên cứu phụ. Chưa có use case nào được AIMICA phê duyệt; không tự triển khai, phỏng vấn hoặc mở Phase 2.
