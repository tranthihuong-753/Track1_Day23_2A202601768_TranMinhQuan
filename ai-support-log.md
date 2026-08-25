# AI Support Log — Day 23

**Người nộp:** Trần Minh Quân · MHV 2A202601768  
**Dự án:** VinTrip — trợ lý lịch trình trên xe VinFast EV

## AI đã giúp tôi ở đâu?

- Brainstorm ứng viên core action từ use case «đi A, ăn sáng 5h, rồi B»: nói với trợ lý, AI sinh lịch, confirm lịch, tới được B.
- Gợi ý tên event `object_action` (`trip_request_submitted`, `itinerary_confirmed`, `constraint_missed`) và AC: không bắn khi ASR dở câu; không trùng khi HUD redraw.
- Phản biện: DAU vì «ngồi xe mỗi ngày» có phải nature không; số lượt hỏi AI có phải NSM không; hoàn thành tới B có quan sát/tác động được không.
- Dựng khung HTML đủ mục 00–07 theo brief.

## AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?

- Dễ lấy **DAU / số utterance** vì xe được mở mỗi ngày — sai nature: lập lịch đa ràng buộc không xảy ra mỗi lần nổ máy.
- Dễ lấy **«hỏi AI trên xe»** làm core action — đó là thao tác giao diện / trigger, trái brief.
- Dễ lấy **tới được điểm B** làm NSM — gần value đời thật nhưng phụ thuộc kẹt xe, quán đóng; team tác động yếu, khó lặp sạch.
- Dễ đo **D7 daily habit** như app consumer — không khớp dạng theo chuyến.

## Tôi đã tự sửa hoặc quyết định lại điều gì?

- **Chọn core action:** xác nhận lịch trình đa điểm khả thi (`itinerary_confirmed` + bắt đầu chạy), không phải hỏi AI hay generate plan.
- **Chốt cadence** theo template: vài lần mỗi tuần vì ngày đa ràng buộc, không vì mỗi lần ngồi vào xe; đo theo tuần ở cấp user.
- **Viết metric hypothesis:** NSM (lịch khả thi confirmed và start / user / tuần) tăng trong 4 tuần vì preference (giờ ăn, trạm sạc, điểm quen) làm đề xuất lần sau khả thi ngay.
- **Siết quality:** feasibility pin + cửa sổ giờ; counter abandon / regenerate / constraint_missed.
- **Không bịa** số retention tham khảo không nguồn.
