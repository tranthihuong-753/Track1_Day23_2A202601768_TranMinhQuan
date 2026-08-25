# Track 1 · Day 23 — Product Metrics Lab

**Họ tên:** Trần Minh Quân  
**MHV:** 2A202601768  
**Repo:** `Track1_Day23_2A202601768_TranMinhQuan-`

## Dự án chọn làm

**VinTrip — trợ lý lịch trình trong xe VinFast (EV).** User nói ý định đa ràng buộc (đi A, ăn sáng 5a.m, rồi tới B); hệ thống tự ghép giờ, điểm dừng, sạc pin.

Use case phân tích sâu: **lập và chốt một lịch trình đa điểm khả thi** — không phân tích toàn bộ infotainment trên xe.

## Metrics Pack (đã cấp quyền xem)

- **[metrics-pack.html](./metrics-pack.html)** — mở trên GitHub hoặc tải về mở bằng trình duyệt.

Nếu GitHub không render HTML:

- https://htmlpreview.github.io/?https://github.com/tranthihuong-753/Track1_Day23_2A202601768_TranMinhQuan-/blob/main/metrics-pack.html

Chuỗi quyết định:

`core action (itinerary_confirmed) → cadence theo tuần/chuyến → NSM / retention / counter → project loop → 7 events + 2 AC`

## Điều tôi mang về áp dụng cho dự án thật

1. **Đo lịch khả thi được xác nhận và bắt đầu chạy**, không đo lượt nói với AI hay số lần đánh thức trợ lý. AI vẽ map chưa phải value.
2. **Nhịp theo tuần / theo chuyến**, không DAU — ngồi vào xe mỗi ngày không có nghĩa phải lập lịch mỗi ngày.
3. **Feasibility pin + cửa sổ giờ ăn** là quality threshold của NSM; thiếu thì dễ game bằng confirm bừa.
4. **Counter:** hủy lịch ngay, regenerate ≥3 lần, lệch giờ ăn / SoC lúc tới B dưới ngưỡng.
5. Event confirm chỉ bắn khi draft → active; redraw màn hình xe không nhân bản.

Khai báo dùng AI: xem [ai-support-log.md](./ai-support-log.md).
