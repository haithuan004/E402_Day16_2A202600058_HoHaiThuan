# Day 16 Submission — Team SafeAge AI

## Members
- Hồ Hải Thuận — BA / Product Lead
- Nguyễn Văn A — AI Engineer
- Trần Thị B — Backend Engineer

---

# 🅐 PLAN A — Original Plan (B2C: Hộ gia đình)

## 1. Idea reframed

**Original idea:**
> Dùng AI nhận diện hành động (action recognition) để phát hiện người cao tuổi bị ngã tại nhà và gửi cảnh báo cho gia đình.

**Reframed as a product opportunity:**
> Hầu hết gia đình Việt Nam có người cao tuổi sống một mình đều dựa vào camera thông thường — nhưng camera thông thường không tự phân tích hành vi, khiến gia đình không nhận được cảnh báo kịp thời khi sự cố xảy ra. Chúng tôi tin rằng nếu tích hợp mô hình AI nhận diện hành động (fall detection) vào camera IP hiện có, chúng tôi có thể cung cấp một lớp bảo vệ chủ động — giúp gia đình an tâm mà không cần theo dõi liên tục và không cần mua phần cứng mới.

---

## 2. Customer / Segment Card

| Trường | Nội dung |
|---|---|
| **Segment name** | Gia đình có người cao tuổi sống bán độc lập (con cái 30–45 tuổi, cha/mẹ 65–80 tuổi) |
| **Operational context** | Con cái đi làm 8–10 tiếng/ngày, người cao tuổi ở nhà một mình |
| **Recurring workflow** | Kiểm tra camera thủ công qua app khi rảnh, gọi điện hỏi thăm định kỳ |
| **Pain moment** | Không biết người thân có bị ngã hoặc gặp sự cố trong khi không để ý |
| **Why now** | Tỷ lệ người cao tuổi VN tăng nhanh (dự kiến 21% dân số vào 2038); camera IP giá rẻ (Ezviz, Imou) đã phổ biến rộng |
| **Access path** | Facebook Groups nuôi dưỡng cha mẹ, hội phụ huynh, nhà thuốc, bệnh viện lão khoa |

**One-sentence description:**
> Một gia đình 3–4 người, con cái tuổi 30–45, có cha/mẹ sống một mình và lo lắng thường trực mỗi khi không thể trực tiếp quan sát.

---

## 3. Need Map

### Need #1 — Cảnh báo kịp thời khi ngã *(priority)*

| Trường | Nội dung |
|---|---|
| **Statement (JTBD)** | Khi tôi đang ở cơ quan, tôi muốn biết ngay lập tức nếu cha/mẹ tôi bị ngã, để tôi có thể gọi cấp cứu kịp thời. |
| **Current workaround** | Xem lại camera thủ công, gọi điện định kỳ mỗi 2–3 giờ |
| **Pain signal** | Nhiều ca ngã không được phát hiện trong 4–8 giờ, dẫn đến biến chứng nặng |
| **Evidence / proxy evidence** | WHO: 30% người cao tuổi trên 65 tuổi ngã ít nhất 1 lần/năm; 50% không được trợ giúp ngay |
| **Why underserved** | Camera thường không phân tích hành vi; wearable bị từ chối đeo vì khó chịu |

### Need #2 — Dễ sử dụng, không cần kỹ thuật

| Trường | Nội dung |
|---|---|
| **Statement (JTBD)** | Khi tôi mua camera giám sát, tôi muốn tính năng cảnh báo thông minh mà không cần tự cấu hình AI, để dùng ngay mà không cần kiến thức kỹ thuật. |
| **Current workaround** | Dùng app camera gốc không có AI; hoặc thuê dịch vụ giám sát đắt tiền |
| **Pain signal** | Tỷ lệ bỏ cuộc cao khi thiết lập camera thông minh; feedback "quá phức tạp" phổ biến |
| **Evidence / proxy evidence** | Review camera AI trên Shopee/Lazada: 40–60% đánh giá 1–2 sao do khó cài đặt |
| **Why underserved** | Giải pháp hiện tại yêu cầu kỹ thuật hoặc subscription phức tạp |

### Need #3 — Cảnh báo chính xác, ít false alarm

| Trường | Nội dung |
|---|---|
| **Statement (JTBD)** | Khi có sự kiện bất thường, tôi muốn nhận thông báo chỉ khi thực sự cần, để không bị ngập trong cảnh báo sai (false alarm). |
| **Current workaround** | Tắt thông báo vì quá nhiều false positive, mất đi giá trị giám sát |
| **Pain signal** | Người dùng vô hiệu hóa cảnh báo sau 1–2 tuần sử dụng |
| **Evidence / proxy evidence** | Nghiên cứu UX camera thông minh: >70% người dùng tắt push notification trong tháng đầu |
| **Why underserved** | Mô hình phát hiện chuyển động đơn giản không phân biệt ngã với ngồi xuống nhanh |

---

## 4. Strategy Statement

> For **gia đình Việt Nam có người cao tuổi sống bán độc lập**
> who struggle with **không thể giám sát liên tục và không nhận cảnh báo kịp thời khi sự cố xảy ra**,
> our product helps them **nhận thông báo tức thì và chính xác khi người thân bị ngã**
> through **mô hình AI nhận diện hành động tích hợp vào camera IP hiện có, không cần phần cứng mới**,
> unlike **camera thông thường hoặc wearable device khó dùng**,
> because we can leverage **mô hình ST-GCN được huấn luyện chuyên biệt trên dữ liệu người cao tuổi Việt Nam**.

---

## 5. Moat Hypothesis

**Moat mechanism:** Domain-specific data flywheel

If we deploy **500 lần** in **hộ gia đình Việt Nam**, the following improve:

1. Độ chính xác mô hình fall detection tăng nhờ dữ liệu thực tế đa dạng hơn
2. False positive rate giảm → người dùng tin tưởng và giữ thông báo bật → engagement tăng
3. Dataset độc quyền về hành vi người cao tuổi VN ngày càng lớn → barrier to entry cho đối thủ

**Why competitors cannot easily replicate this:**
> Dữ liệu skeleton hành vi người cao tuổi trong môi trường gia đình VN (ánh sáng thấp, góc camera không chuẩn, trang phục truyền thống) rất khó thu thập. Mô hình train trên dữ liệu phương Tây hoạt động kém hơn đáng kể — tạo ra lợi thế dữ liệu địa phương bền vững.

---

## 6. Initial TAM / SAM / SOM view

| Layer | Estimate | Key assumptions | Confidence |
|---|---|---|---|
| TAM | 5.000–10.000 tỷ VNĐ/năm | 11M hộ gia đình có người cao tuổi tại VN, 375.000–750.000 VNĐ/tháng | low |
| SAM | 2.000–3.750 tỷ VNĐ/năm | 500K hộ đô thị lớn (HCM, HN, ĐN) có camera IP sẵn | med |
| SOM | 25–75 tỷ VNĐ/năm | 5K–15K hộ trong 12–24 tháng, ARPU 375.000 VNĐ/tháng | med |

**Top 3 unknowns requiring further research:**

1. Mức độ sẵn sàng chi trả thực tế (125.000 VNĐ vs 375.000 VNĐ/tháng?)
2. Tỷ lệ chuyển đổi từ dùng thử miễn phí sang trả phí
3. Khả năng tích hợp với camera IP phổ biến nhất VN (Imou, Ezviz, Dahua)

**Judgment:**
- [ ] Worth pursuing now
- [x] Worth pursuing but not now (need to validate willingness-to-pay and integration feasibility first)
- [ ] Not worth pursuing as currently framed

---

## 7. Positioning Note

**What we are:**
> Một lớp AI thông minh gắn lên camera giám sát hiện có, chuyên phát hiện ngã và hành vi bất thường của người cao tuổi, gửi cảnh báo tức thì đến gia đình.

**What we are not / not yet:**
> Chúng tôi không phải thiết bị phần cứng mới, không phải dịch vụ y tế khẩn cấp, và chưa phải nền tảng chăm sóc sức khỏe toàn diện.

---

## 8. Self-assessment before Day 17

Trong 6 mắt xích (Idea / Customer / Need / Strategy / Moat / Market Size), mắt xích nào yếu nhất?

> **Customer** — Chúng tôi chưa xác nhận ai thực sự là người ra quyết định mua (con cái hay người cao tuổi?) và mức độ lo lắng có đủ để tạo hành động mua không.

Open questions chúng tôi muốn khám phá thêm ở Day 17:

1. Người cao tuổi có chấp nhận bị camera theo dõi liên tục không (privacy concern)?
2. Kênh phân phối nào hiệu quả: B2C trực tiếp hay qua đại lý camera/nhà thuốc?
3. Có nên ra mắt với viện dưỡng lão trước (B2B) để có doanh thu sớm hơn?
