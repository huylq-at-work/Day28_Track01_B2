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

*"Ít người dùng" là triệu chứng, không phải nguyên nhân. Hai nguyên nhân dưới đây là giả thuyết đã nháp; nhóm phải gắn bằng chứng thật trước checkpoint phút 40.*

| # | Nguyên nhân gốc | Framework | Bằng chứng |
|---|---|---|---|
| 1 | Mức sẵn sàng của kho tài liệu chưa đạt: SharePoint không có người phụ trách nội dung, không có lịch cập nhật, phân quyền không đồng nhất, nên Copilot trả lời thiếu hoặc dựa trên bản cũ | Gartner-Lite — trục Readiness (dữ liệu và governance THIẾU trong khi Direction ĐẠT) | _(điền)_ phỏng vấn ngắn 2–3 người có license; đếm số kho tài liệu không có owner |
| 2 | Người dùng không có cách kiểm chứng nên không dám tin kết quả, nghẽn ở Desire chứ không phải thiếu kiến thức | ADKAR — nghẽn tại Desire và Reinforcement, không phải Knowledge | _(điền)_ câu trả lời phỏng vấn về lý do bỏ dùng; quan sát tại chỗ 10 ca |

**Hệ quả cho phần giải pháp:** mở lớp đào tạo không giải quyết được hai nguyên nhân này. Cần sửa nguồn dữ liệu và cách kiểm chứng trước, rồi mới tính chuyện tăng mức dùng.

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

## Cấu trúc repo

```
├── README.md
├── dashboard/dashboard_hanh_dong_v2.xlsx   ← bản v2 sau kiểm tra chéo
├── memo/memo_quyet_dinh.md                 ← 5 phần
└── v1/dashboard_hanh_dong_v1.xlsx          ← bản trước phản biện, để đối chiếu
```
