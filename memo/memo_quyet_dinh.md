# Memo quyết định — Day28_Track01_B2

> Bản nháp để nhóm sửa trong buổi lab. Chỗ đánh dấu _(điền)_ phải thay bằng nội dung thật.

## 1. Vấn đề và nguyên nhân gốc

Nhóm khoá phạm vi vào Microsoft 365 Copilot đã cấp license cho toàn phòng, dùng bởi nhân viên khối văn phòng, trong ba quy trình soạn văn bản, tóm tắt cuộc họp và tra cứu tài liệu trên SharePoint. Vấn đề quan sát được là mức dùng tụt sau tháng đầu và người dùng quay lại soạn tay cùng tự mở thư mục tìm file.

Công cụ đã ở mức Deployment chứ chưa tới Adoption. License đã cấp nhưng công việc, trách nhiệm và cách kiểm soát chưa thay đổi, nên chưa có bước nào trong quy trình chính thức nhắc tới Copilot.

Hai nguyên nhân gốc, phân biệt rõ với triệu chứng ít người dùng:

1. **Mức sẵn sàng của kho tài liệu chưa đạt.** SharePoint không có người phụ trách nội dung và không có lịch cập nhật, phân quyền không đồng nhất giữa các phòng. Copilot vì thế trả lời thiếu hoặc dựa trên bản cũ.
2. **Người dùng không có cách kiểm chứng nên không dám tin kết quả.** Câu trả lời không kèm liên kết nguồn và ngày cập nhật, nên kiểm lại bằng tay còn lâu hơn tự làm từ đầu.

## 2. Framework đã dùng và bằng chứng

**Gartner-Lite** dùng để đánh giá mức sẵn sàng của tổ chức trước khi bàn tới mở rộng.

| Hạng mục | Nhận định | Kết quả |
|---|---|---|
| Hướng đi | Mục tiêu rõ: giảm thời gian soạn văn bản và tra cứu tài liệu | ĐẠT |
| Dữ liệu | Kho SharePoint thiếu người phụ trách và lịch cập nhật | THIẾU |
| Governance | Phân quyền và phạm vi tài liệu chưa thống nhất giữa các phòng | THIẾU |
| Vận hành | Chưa có ai chịu trách nhiệm chất lượng câu trả lời | THIẾU |
| Hấp thụ | Chưa có kênh báo lỗi và vòng phản hồi | THIẾU |

Kết luận: pilot nhỏ một phòng để sửa readiness, chưa mở rộng toàn công ty.

**Mollick** dùng để chia lại việc giữa người và AI. Copilot nằm hoàn toàn ở vùng AI hỗ trợ, người kiểm. Không có phần nào tự động hoàn toàn trong ba quy trình này, vì văn bản phát hành ra ngoài có rủi ro và chưa có tiêu chí kiểm tra tự động.

**ADKAR** dùng để tìm điểm nghẽn ở người dùng.

| Bước | Nhận định | Trạng thái |
|---|---|---|
| Awareness | Chưa rõ nên dùng Copilot cho loại việc nào | NGHẼN |
| Desire | Ngại tin kết quả vì không thấy nguồn và ngày cập nhật | NGHẼN |
| Knowledge | Chưa biết cách kiểm chứng nguồn | Cần làm |
| Ability | Chưa thực hành trong quy trình soạn văn bản thật | Cần làm |
| Reinforcement | Chưa có kênh báo lỗi và theo dõi hành vi mới | Cần làm |

Điểm nghẽn nằm ở Desire và Reinforcement, nên mở lớp đào tạo không giải quyết được vấn đề.

**Bằng chứng:** _(điền)_ phỏng vấn ngắn 2–3 người đang có license về lý do bỏ dùng; đếm số kho tài liệu SharePoint không có người phụ trách; quan sát tại chỗ 10 ca soạn văn bản. Bài học tham khảo là Morgan Stanley, độ tin cậy phải đi trước mở rộng.

## 3. Ít nhất 2 thay đổi sau phản biện

| # | Góp ý nhận được (từ nhóm nào) | Thay đổi trong v2 |
|---|---|---|
| 1 | _(điền)_ | _(điền)_ |
| 2 | _(điền)_ | _(điền)_ |

## 4. Quyết định

**Tiếp tục / Sửa / Dừng:** _(chốt cuối chặng 3)_

Hướng nhóm nghiêng về Sửa, tức là giữ pilot ở một phòng nhưng sửa nguyên nhân readiness trước, chưa mở rộng. Nhóm chốt lại sau khi có bằng chứng thật.

## 5. Lý do, bước tiếp theo và owner

Lý do: _(điền)_ Vấn đề không nằm ở mức độ quen tay của người dùng mà ở chất lượng nguồn dữ liệu và ở chỗ thiếu cách kiểm chứng. Mở rộng license thêm khi hai thứ đó chưa sửa sẽ chỉ làm tăng số người thất vọng.

| Giai đoạn | Mục tiêu cổng | Dấu hiệu hoàn thành | Owner |
|---|---|---|---|
| 0–30 ngày | Chứng minh vấn đề | Vẽ xong AS-IS và TO-BE; chỉ định người phụ trách cho từng kho tài liệu trong phạm vi pilot; ghi đủ baseline cho bốn chỉ số chính | _(điền tên)_ |
| 31–60 ngày | Chứng minh chất lượng | Tỷ lệ câu trả lời có nguồn đạt mục tiêu; nút báo lỗi đã chạy và log được rà hàng tuần; tỷ lệ bản nháp phải viết lại giảm | _(điền tên)_ |
| 61–90 ngày | Quyết định mở rộng | So sánh với mục tiêu; chốt owner vận hành lâu dài; kiểm tra governance phân quyền; quyết định mở rộng, sửa tiếp hay dừng và trả license | _(điền tên)_ |

Cổng chỉ được thông qua khi chất lượng, hành vi và giá trị đạt mục tiêu nhóm đã xác nhận, không phải khi hết 30 ngày.
