# Day28_Track01_B2

Lab 28 — Dashboard Hành Động cho Áp Dụng AI. Repo gồm dashboard v1 (trước phản biện), dashboard v2 (sau phản biện) và memo quyết định.

## 1. Thành viên

*Nhóm phản biện chéo với nhóm: __ (ghi số/tên nhóm)*

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
|---|---|---|---|
| Đàm Việt Cường | 2A202601566 | | |
| Lê Quang Huy | 2A202601821 | | |
| Hoàng Minh Quân | 2A202601574 | | |

## 2. Phạm vi

> Nháp sẵn để nhóm sửa. Chốt lại con số và tên phòng ban theo tình huống thật lấy từ hoạt động mở đầu.

Nhóm khoá phạm vi vào **Microsoft 365 Copilot đã cấp license cho toàn phòng, dùng bởi nhân viên khối văn phòng, trong ba quy trình soạn văn bản, tóm tắt cuộc họp và tra cứu tài liệu trên SharePoint, nơi phần lớn người dùng quay lại làm thủ công sau tháng đầu tiên.**

- **Product:** Microsoft 365 Copilot, đã cấp license toàn phòng
- **User:** nhân viên khối văn phòng
- **Workflow (3):** soạn văn bản · tóm tắt cuộc họp · tra cứu tài liệu trên SharePoint
- **Problem:** mức dùng tụt sau tháng đầu, người dùng quay lại soạn tay và tự mở thư mục tìm file

## 3. Nguyên nhân gốc

*"Ít người dùng" là triệu chứng, không phải nguyên nhân. Bằng chứng dưới đây lấy từ hai báo cáo đánh giá công khai của chính phủ Anh trên cùng một sản phẩm Microsoft 365 Copilot, nên so sánh được trực tiếp với tình huống của nhóm.*

| # | Nguyên nhân gốc | Framework | Bằng chứng |
|---|---|---|---|
| 1 | Mức sẵn sàng của kho tài liệu chưa đạt: SharePoint không có người phụ trách nội dung, không có lịch cập nhật, phân quyền tích tụ qua nhiều năm, nên Copilot trả lời thiếu hoặc dựa trên bản cũ | Gartner-Lite — trục Readiness THIẾU trong khi Direction ĐẠT | Microsoft xác định oversharing và nội dung tồn đọng trên SharePoint là rào cản phải xử lý **trước** khi triển khai Copilot, và phát hành công cụ riêng cho việc này ([Microsoft Community Hub](https://techcommunity.microsoft.com/blog/microsoft365copilotblog/mitigate-oversharing-to-govern-microsoft-365-copilot-and-agents/4448744)) |
| 2 | Người dùng không có cách kiểm chứng thống nhất nên chất lượng đầu ra không ổn định và không ai dám tin kết quả | ADKAR — nghẽn tại Desire và Reinforcement, không phải Knowledge | Đánh giá của Bộ Kinh doanh và Thương mại Anh ghi nhận cách kiểm tra chất lượng đầu ra không thống nhất giữa người dùng và giữa các loại tác vụ, có báo cáo hiện tượng bịa thông tin; trong bài kiểm tra có nhóm đối chứng, người dùng Copilot làm phân tích Excel **chậm hơn và kém chính xác hơn** người không dùng ([DBT evaluation, 2025](https://assets.publishing.service.gov.uk/media/68adbe409e1cebdd2c96a19d/dbt-microsoft-365-copilot-evaluation.pdf)) |

**Bằng chứng phụ, dùng cho lập luận về cách đo:** thử nghiệm liên bộ do GDS chạy trên hơn 20.000 công chức, từ 30/9 đến 31/12/2024, cho con số tiết kiệm trung bình 26 phút mỗi ngày, nhưng đó là **số người dùng tự ước tính trong khảo sát**. Cùng sản phẩm đó, đánh giá của DBT có nhóm đối chứng lại kết luận không tìm thấy bằng chứng rằng thời gian tiết kiệm dẫn tới tăng năng suất. Đây chính là bài học DWP/GDS mà lab nhắc tới, và là lý do dashboard của nhóm không dùng chỉ số tự khai.

**Hệ quả cho phần giải pháp:** mở lớp đào tạo không giải quyết được hai nguyên nhân này. Đánh giá của DBT còn ghi nhận tự học có hiệu quả cao hơn các buổi đào tạo chính thức của phòng ban trong việc tăng mức hài lòng. Cần sửa nguồn dữ liệu và cách kiểm chứng trước, rồi mới tính chuyện tăng mức dùng.

## 4. Cách làm mới

*Ba thay đổi bắt buộc so với AS-IS. AS-IS: nhận yêu cầu → tự soạn hoặc tự mở thư mục tìm file → gửi duyệt.*

- **Nguồn kiểm chứng:** chỉ bật Copilot trên các kho SharePoint đã có người phụ trách nội dung và lịch cập nhật; mọi câu trả lời phải kèm liên kết tài liệu nguồn và ngày cập nhật, không có nguồn thì không dùng.
- **Người chịu trách nhiệm:** người soạn văn bản chịu trách nhiệm kết quả cuối và phải mở tài liệu nguồn để kiểm chứng trước khi gửi; người duyệt văn bản giữ quyền phê duyệt. Theo Mollick, Copilot ở vùng AI hỗ trợ, người kiểm; không có phần nào tự động hoàn toàn trong ba quy trình này.
- **Cách xử lý khi AI không chắc:** nếu không truy được nguồn hoặc nguồn quá hạn cập nhật thì chuyển sang cách làm cũ và bấm nút báo lỗi; log lỗi được rà hàng tuần và là đầu vào để thu hẹp hoặc mở rộng phạm vi tài liệu.

**TO-BE:** nhận yêu cầu → hỏi Copilot theo quy trình → mở tài liệu nguồn kiểm chứng → soạn và chịu trách nhiệm → gửi duyệt, hoặc báo lỗi và quay về cách cũ.

## 5. Chỉ số

*Bản đầy đủ bảy dòng nằm trong `dashboard/dashboard_hanh_dong_v2.xlsx`. Baseline và target phải chốt lại bằng dữ liệu nhóm thật sự lấy được.*

| Loại | Chỉ số | Baseline | Target | Nguồn dữ liệu | Owner |
|---|---|---|---|---|---|
| Product | Tỷ lệ câu trả lời truy được về tài liệu nguồn có ngày cập nhật | Đo mẫu tuần 1, 30 câu hỏi thật | ≥ 90% sau 60 ngày | Kiểm tra mẫu 30 câu/tuần | Phụ trách QA |
| Product | Thời gian chờ hoàn thành một yêu cầu văn bản nội bộ | Số hiện tại, 3 tháng gần nhất | Giảm ≥ 20% sau 90 ngày | Hệ thống giao việc | Chủ nghiệp vụ |
| Workflow | Thời gian trung bình hoàn thành một văn bản chuẩn | Bấm giờ mẫu 20 ca | Giảm ≥ 25% | Log tác vụ | Chủ quy trình |
| Workflow | Tỷ lệ bản nháp dùng được mà không phải viết lại | Đo mẫu 20 bản nháp | ≥ 70% sau 60 ngày | Người duyệt chấm mẫu | Người duyệt văn bản |

Nhóm cố ý không đưa số lần đăng nhập và số câu hỏi vào dashboard, vì đó là chỉ số activity không dẫn tới quyết định.

## 6. Quyết định

- **Quyết định:** Tiếp tục / Sửa / Dừng — _(chốt cuối chặng 3)_
- **Lý do (một câu):** _(điền)_
- **2 thay đổi so với v1:**
  1. _(điền sau phản biện)_
  2. _(điền sau phản biện)_

## 7. Nguồn tham khảo

| Nguồn | Dùng cho | Địa chỉ |
|---|---|---|
| DBT — Microsoft 365 Copilot evaluation (2025) | Nguyên nhân gốc 2, lập luận chống chỉ số tự khai | [assets.publishing.service.gov.uk](https://assets.publishing.service.gov.uk/media/68adbe409e1cebdd2c96a19d/dbt-microsoft-365-copilot-evaluation.pdf) |
| GDS — M365 Copilot cross-government experiment findings (2025) | Bằng chứng phụ về số liệu tự khai | [gov.uk](https://www.gov.uk/government/publications/microsoft-365-copilot-experiment-cross-government-findings-report) |
| Microsoft — Mitigate oversharing to govern M365 Copilot | Nguyên nhân gốc 1, trục Readiness | [techcommunity.microsoft.com](https://techcommunity.microsoft.com/blog/microsoft365copilotblog/mitigate-oversharing-to-govern-microsoft-365-copilot-and-agents/4448744) |
| Prosci — ADKAR Model | Tìm điểm nghẽn ở người dùng | [prosci.com](https://www.prosci.com/methodology/adkar) |

## Cấu trúc repo

```
├── README.md
├── dashboard/dashboard_hanh_dong_v2.xlsx   ← bản v2 sau kiểm tra chéo
├── memo/memo_quyet_dinh.md                 ← 5 phần
└── v1/dashboard_hanh_dong_v1.xlsx          ← bản trước phản biện, để đối chiếu
```
