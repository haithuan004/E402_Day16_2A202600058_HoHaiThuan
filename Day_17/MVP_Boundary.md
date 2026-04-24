# MVP Boundary — AI Nurse Assistant (Plan B · B2B)

> **Sản phẩm:** AI Nurse Assistant — hệ thống giám sát thông minh tích hợp vào camera hiện có, giúp điều dưỡng phát hiện sự cố ngã tức thì và tự động hóa hồ sơ an toàn bệnh nhân tại viện dưỡng lão & bệnh viện tư.

---

## 💡 Idea

**"AI Nurse Assistant"** — không chỉ phát hiện ngã, mà trở thành **hệ thống tự động hóa an toàn bệnh nhân** cho viện dưỡng lão & bệnh viện tư, giải quyết 3 pain point cùng lúc:
1. **Phát hiện tức thì** — cảnh báo điều dưỡng trong < 30 giây
2. **Hồ sơ pháp lý tự động** — báo cáo sự cố PDF, tránh tranh chấp
3. **Scale không cần tăng nhân sự** — 1 điều dưỡng giám sát nhiều phòng hơn

---

## 📋 Scope Definition (MVP v1.0)

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

## 🧠 Logic phân loại

| Category | Tiêu chí quyết định |
|---|---|
| **In-Scope** | Tính năng cốt lõi **bắt buộc** để test giả thuyết: "AI giúp giảm thời gian phản ứng xuống < 60 giây" trong pilot 3 tháng |
| **Out-of-Scope** | Tính năng tốt nhưng **làm tăng complexity và kéo dài timeline** — không cần cho MVP, bảo lưu v2 |
| **Non-Goals** | **Ranh giới đỏ** — sản phẩm sẽ KHÔNG làm trong giai đoạn này, tránh scope creep, đặc biệt rủi ro pháp lý |

---

## 👤 Author

- **Hồ Hải Thuận** — BA / Product Lead
- Ngày tạo: 2026-04-24
