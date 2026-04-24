Idea: AI Nurse Assistant — hệ thống giám sát thông minh tích hợp vào camera hiện có, giúp điều dưỡng phát hiện sự cố ngã tức thì và tự động hóa hồ sơ an toàn bệnh nhân tại viện dưỡng lão & bệnh viện tư.

Problem: 1 điều dưỡng phụ trách nhiều phòng, không thể giám sát 100% bệnh nhân, dẫn đến chậm trễ phát hiện sự cố ngã, tăng nguy cơ biến chứng và rủi ro pháp lý cho viện.

Target User: Người quản lí/giám đốc của các viện dưỡng lão & bệnh viện tư.

User Story #1: As a manager, I want to receive instant alerts when a patient falls so that I can respond quickly and prevent further harm.

User Story #2: As a manager, I want to view a timeline of incidents for each patient so that I can track their care and identify patterns.


AI-specific

Model selection: Tôi chọn ST-GCN (Spatial Temporal Graph Convolutional Network) — mô hình nhận diện hành động dựa trên skeleton (bộ khung xương người trích xuất từ camera). Lý do:
- Privacy-safe: không lưu khuôn mặt hay hình ảnh thô, chỉ xử lý tọa độ keypoint → phù hợp môi trường y tế nhạy cảm
- Robust với ánh sáng thấp và góc camera không chuẩn — hai điều kiện phổ biến tại phòng bệnh nhân ban đêm
- Đã được fine-tune trên dữ liệu người cao tuổi Việt Nam (từ dự án thực chiến), cho F1-score cao hơn mô hình phương Tây trên cùng test set
- Inference nhẹ, chạy được trên edge device (Jetson Nano) hoặc server on-premise, không phụ thuộc cloud

Data source: Dữ liệu huấn luyện mô hình lấy từ 3 nguồn:
1. Dataset nội bộ: video skeleton thu thập tại 2 cơ sở y tế đối tác (có ký thỏa thuận bảo mật), gồm 4 lớp hành động: walking / standing / sitting / falling — ~8.000 track sau augmentation
2. Dataset công khai: NTU RGB+D 60 (Trung Quốc) và CASIA-B dùng để pre-train backbone, sau đó fine-tune với dữ liệu VN
3. Synthetic augmentation: xoay, lật, thêm nhiễu Gaussian vào keypoint, thay đổi tốc độ để tăng độ đa dạng mà không vi phạm privacy

Fallback UX: Khi AI sai / không tự tin (confidence score < 0.75) →
- KHÔNG gửi push notification cảnh báo ngay — tránh false alarm gây mất tin tưởng
- Lưu clip ngắn 10 giây vào hàng đợi "Cần xác nhận" trên dashboard
- Hiển thị badge "⚠️ Unconfirmed Event" để điều dưỡng xem lại trong lần tuần tra tiếp theo
- Ghi log sự kiện vào dataset nội bộ để cải thiện mô hình trong vòng lặp học liên tục (human-in-the-loop)

Hypothesis Validation

Riskiest Assumption: Giả định nguy hiểm nhất là mô hình ST-GCN có thể phát hiện ngã đủ chính xác (precision > 85%, false alarm < 2 lần/ca trực) trong môi trường thực tế của viện dưỡng lão VN — với ánh sáng thấp, góc camera không chuẩn và trang phục bệnh nhân đa dạng — mà không cần can thiệp thủ công liên tục.

Hypothesis: Tôi tin rằng việc triển khai AI Nurse Assistant vào 1 viện dưỡng lão pilot sẽ giúp đội ngũ điều dưỡng giảm thời gian phát hiện sự cố ngã từ trung bình 40–60 phút xuống dưới 2 phút, đạt được mức độ tin tưởng đủ để cơ sở gia hạn hợp đồng sau 3 tháng thử nghiệm.

Aha Moment: Hành vi cốt lõi chứng tỏ họ nhận được giá trị — điều dưỡng trực nhận push notification, mở app, xác nhận sự cố thật và đến phòng bệnh nhân trong vòng 2 phút. Lần đầu điều này xảy ra thành công trong ca trực thực tế là "Aha Moment" của sản phẩm.

PMF Signal:
- Sean Ellis Test: > 40% người dùng (quản lý + điều dưỡng trực) trả lời "rất thất vọng" nếu không còn dùng sản phẩm
- Retention: Tỷ lệ điều dưỡng chủ động mở app để xem lại dashboard (không chỉ khi có alert) sau tuần thứ 2
- Aha Metric: Số lần alert được xác nhận là đúng (true positive) / tổng alert trong 30 ngày đầu ≥ 85%
