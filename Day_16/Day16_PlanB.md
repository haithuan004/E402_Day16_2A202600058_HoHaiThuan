# 🅑 PLAN B — Upgraded Plan (B2B: Viện dưỡng lão & Bệnh viện tư)

## Members
- Hồ Hải Thuận — BA / Product Lead

---

## 1. Idea reframed

**Original idea:**
> Dùng AI nhận diện hành động để phát hiện ngã và hành vi bất thường trong cơ sở y tế, hỗ trợ đội ngũ điều dưỡng phản ứng nhanh hơn.

**Reframed as a product opportunity:**
> Các viện dưỡng lão và bệnh viện tư tại Việt Nam đang đối mặt với thiếu hụt nhân lực điều dưỡng trầm trọng (tỷ lệ 1 điều dưỡng/10–15 bệnh nhân) và áp lực pháp lý ngày càng lớn khi để bệnh nhân ngã. Tôi tái định vị sản phẩm như một **AI Nurse Assistant** — hệ thống giám sát thông minh giúp đội ngũ y tế ưu tiên phản ứng, tự động hóa hồ sơ sự cố, và giảm rủi ro pháp lý — cho phép cơ sở mở rộng quy mô mà không tăng nhân sự tương ứng.

---

## 2. Customer / Segment Card

| Trường | Nội dung |
|---|---|
| **Segment name** | Giám đốc điều hành / Quản lý vận hành viện dưỡng lão tư nhân & khoa Lão khoa BV tư |
| **Operational context** | Cơ sở 30–200 giường, 5–20 điều dưỡng, ca trực đêm thiếu nhân lực nhất |
| **Recurring workflow** | Điều dưỡng tuần tra theo giờ cố định, ghi sổ sự cố thủ công, báo cáo quản lý hàng tuần |
| **Pain moment** | Bệnh nhân ngã ban đêm không được phát hiện kịp → gia đình khiếu nại → bồi thường pháp lý |
| **Why now** | Nghị định 109/2016/NĐ-CP siết tiêu chuẩn an toàn BV; bảo hiểm y tế tư nhân yêu cầu báo cáo sự cố có bằng chứng |
| **Access path** | Hội nghị điều dưỡng quốc gia, Hiệp hội BV Tư nhân VN, pilot với cơ sở đối tác từ network |

**One-sentence description:**
> Một giám đốc điều hành viện dưỡng lão tư nhân đang chịu áp lực từ gia đình bệnh nhân và cơ quan quản lý, cần công cụ để chứng minh cơ sở vận hành an toàn và có trách nhiệm.

---

## 3. Need Map

### Need #1 — Phát hiện ngã tức thì *(priority)*

| Trường | Nội dung |
|---|---|
| **Statement (JTBD)** | Khi bệnh nhân ngã vào ban đêm, tôi muốn điều dưỡng trực được cảnh báo trong 30 giây, để giảm thời gian nằm trên sàn và tránh biến chứng thứ phát. |
| **Current workaround** | Tuần tra mỗi 1–2 giờ; bệnh nhân bấm chuông (nhiều người không thể bấm được sau khi ngã) |
| **Pain signal** | Trung bình 40–60 phút trước khi sự cố được phát hiện tại cơ sở không có AI |
| **Evidence / proxy evidence** | Joint Commission (2023): Falls là sự cố y tế có thể phòng ngừa phổ biến nhất tại cơ sở chăm sóc dài hạn |
| **Why underserved** | Camera CCTV chỉ để xem lại, không phân tích real-time; nhân lực không đủ theo dõi liên tục |

### Need #2 — Tự động hóa hồ sơ sự cố & bằng chứng pháp lý

| Trường | Nội dung |
|---|---|
| **Statement (JTBD)** | Khi cần báo cáo với cơ quan y tế hoặc gia đình bệnh nhân, tôi muốn có dữ liệu sự cố đầy đủ và tự động, để tránh tranh chấp pháp lý và chứng minh quy trình chăm sóc đúng chuẩn. |
| **Current workaround** | Ghi chép thủ công vào sổ, dễ bỏ sót hoặc bị chỉnh sửa hậu kỳ |
| **Pain signal** | 30% khiếu nại y tế tại VN liên quan đến thiếu bằng chứng quy trình chăm sóc |
| **Evidence / proxy evidence** | Phỏng vấn proxy với 3 quản lý viện dưỡng lão tại HCM (qua LinkedIn + hội nhóm chuyên môn) |
| **Why underserved** | Không có phần mềm nào tích hợp camera AI + nhật ký sự cố tự động tại thị trường VN |

### Need #3 — Mở rộng quy mô không cần tăng nhân sự

| Trường | Nội dung |
|---|---|
| **Statement (JTBD)** | Khi muốn mở rộng cơ sở mà không tăng nhân sự tương ứng, tôi muốn hệ thống giám sát scale theo số phòng, để kiểm soát chi phí vận hành. |
| **Current workaround** | Tuyển thêm điều dưỡng (chi phí cao, khó tuyển) hoặc chấp nhận rủi ro thiếu giám sát |
| **Pain signal** | Chi phí nhân sự điều dưỡng chiếm 55–65% tổng chi phí vận hành |
| **Evidence / proxy evidence** | Báo cáo ngành chăm sóc người cao tuổi ASEAN 2024 — Deloitte |
| **Why underserved** | Chưa có giải pháp SaaS phục vụ segment này tại VN với giá hợp lý |

---

## 4. Strategy Statement

> For **giám đốc điều hành viện dưỡng lão và bệnh viện tư tại Việt Nam**
> who struggle with **thiếu nhân lực giám sát và áp lực pháp lý khi xảy ra sự cố ngã**,
> our product helps them **phát hiện sự cố tức thì, tự động tạo hồ sơ sự cố, và giảm thời gian phản ứng xuống dưới 60 giây**
> through **hệ thống AI Nurse Assistant tích hợp vào camera hiện có, với dashboard quản lý và báo cáo tự động**,
> unlike **camera CCTV thông thường hoặc giải pháp wearable đắt tiền từ nước ngoài**,
> because we can leverage **mô hình skeleton-based action recognition được fine-tune trên môi trường bệnh viện VN và tích hợp sâu vào workflow điều dưỡng thực tế**.

---

## 5. Moat Hypothesis

**Moat mechanism:** Clinical workflow lock-in + proprietary incident data flywheel

If we deploy **50 lần** in **viện dưỡng lão / bệnh viện**, the following improve:

1. Mô hình fall detection cải thiện độ chính xác trong môi trường y tế VN (ánh sáng, trang phục bệnh nhân, layout phòng đặc thù)
2. Tích hợp sâu vào quy trình điều dưỡng → switching cost cao (đào tạo lại, mất dữ liệu lịch sử sự cố)
3. Dataset sự cố y tế độc quyền → nền tảng mở rộng sang phân tích rủi ro, dự báo sức khỏe bệnh nhân

**Why competitors cannot easily replicate this:**
> Dữ liệu sự cố y tế được bảo vệ bởi quy định riêng tư — không thể mua hoặc scrape công khai. Mỗi cơ sở triển khai tạo ra dữ liệu độc quyền và mối quan hệ tin cậy với đội ngũ y tế. Đối thủ nước ngoài thiếu hiểu biết về quy trình vận hành và ngôn ngữ địa phương để tích hợp nhanh.

---

## 6. Initial TAM / SAM / SOM view

| Layer | Estimate | Key assumptions | Confidence |
|---|---|---|---|
| TAM | 12.500–25.000 tỷ VNĐ/năm | 1.400+ viện dưỡng lão + 200 BV tư VN, 50–125 triệu VNĐ/cơ sở/năm | low |
| SAM | 750–2.000 tỷ VNĐ/năm | 300 cơ sở tư nhân tại HCM, HN, ĐN đủ ngân sách và nhu cầu | med |
| SOM | 12,5–50 tỷ VNĐ/năm | 20–50 cơ sở trong 18 tháng, ARPU 50–87,5 triệu VNĐ/năm | med |

**Top 3 unknowns requiring further research:**

1. Quy trình phê duyệt mua sắm công nghệ tại BV tư mất bao lâu và ai là decision maker thực sự?
2. Cơ sở có cho phép AI tiếp cận dữ liệu camera bệnh nhân không (privacy & compliance)?
3. Đối thủ nào đang cung cấp giải pháp tương tự tại ASEAN và giá như thế nào?

**Judgment:**
- [x] Worth pursuing now — pain rõ ràng, người trả tiền xác định (B2B), barrier to entry cao, có thể pilot với 1 cơ sở trong 3 tháng.
- [ ] Worth pursuing but not now (need to validate [...] first)
- [ ] Not worth pursuing as currently framed

---

## 7. Positioning Note

**What we are:**
> AI Nurse Assistant — hệ thống giám sát thông minh tích hợp vào camera hiện có, giúp điều dưỡng phát hiện sự cố tức thì và tự động hóa hồ sơ an toàn bệnh nhân.

**What we are not / not yet:**
> Tôi không cung cấp thiết bị y tế được cấp phép, không thay thế điều dưỡng, và chưa phải nền tảng quản lý hồ sơ bệnh án (EMR) toàn diện.

---

## 8. Scope Definition (MVP v1.0)

| Category | Nội dung |
|---|---|
| **In-Scope** | ✅ Phát hiện ngã real-time từ camera IP hiện có (RTSP stream) |
| | ✅ Cảnh báo tức thì đến điều dưỡng trực qua app mobile (push notification < 30 giây) |
| | ✅ Dashboard web cho quản lý: xem lịch sử sự cố, timeline, clip ngắn |
| | ✅ Tự động tạo báo cáo sự cố (thời gian, phòng, loại sự cố) theo định dạng PDF |
| | ✅ Hỗ trợ tối đa 20 camera/cơ sở trong phiên bản pilot |
| **Out-of-Scope** | ⏳ Nhận diện danh tính bệnh nhân (face recognition) — bảo lưu v2 |
| | ⏳ Tích hợp với hệ thống HIS/EMR bệnh viện — cần API riêng từng cơ sở |
| | ⏳ Phân tích dáng đi (gait analysis) để dự báo nguy cơ ngã — cần thêm dữ liệu |
| | ⏳ App mobile cho gia đình bệnh nhân — không phải người dùng chính ở segment B2B |
| | ⏳ Hỗ trợ camera fisheye / PTZ — phức tạp về góc nhìn, để sau |
| **Non-Goals** | 🚫 Thay thế điều dưỡng — sản phẩm là công cụ hỗ trợ, không phải tự động hóa toàn bộ |
| | 🚫 Cấp phép thiết bị y tế (Medical Device) — tránh overhead pháp lý trong MVP |
| | 🚫 Lưu trữ video 24/7 toàn bộ (không phải giải pháp cloud storage) |
| | 🚫 Phát hiện các sự cố ngoài ngã: đánh nhau, trốn khỏi phòng — out of model scope |
| | 🚫 Hỗ trợ đa ngôn ngữ (ngoài tiếng Việt) trong MVP |

---

## 9. Self-assessment before Day 17

Trong 6 mắt xích (Idea / Customer / Need / Strategy / Moat / Market Size), mắt xích nào yếu nhất?

> **Strategy** — Tôi chưa xác định rõ "distinct approach" so với đối thủ quốc tế (Nuralogix, startup Singapore) đang nhắm vào ASEAN. Cần nghiên cứu competitive landscape sâu hơn trước Day 17.

Open questions tôi muốn khám phá thêm ở Day 17:

1. Pilot với cơ sở đầu tiên: miễn phí hay tính phí thấp? Điều kiện để họ đồng ý thử là gì?
2. Có cần xin giấy phép thiết bị y tế (Bộ Y tế) để triển khai không, và timeline bao lâu?
3. Mô hình doanh thu nào phù hợp hơn: one-time setup fee + subscription, hay thuần subscription?
