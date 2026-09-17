# Mẫu tham khảo để điền REPORT.md

**Cách dùng:** Bản cần nộp đã có sẵn ở [`REPORT.md`](../REPORT.md) trong thư mục gốc của fork; mở file đó và điền vào chỗ `…`. File này giải thích từng mục và có ví dụ để tham khảo khi bạn bị kẹt. Giữ nguyên bốn mục và bảng để coach đọc bài nhanh; **không chép ví dụ thành câu trả lời của mình**.

- Mã học viên theo lớp: 2A202602297
- Ngày / CVAT local: 17/9/2026
- Công cụ đã dùng: Brush / Polygon / Intelligent Scissors / gợi ý tự động có sẵn / khác: mask

Mã học viên là mã lớp cấp, không cần ghi họ tên trong bản nộp nếu kênh lớp đã nhận diện bạn. Ở dòng công cụ, giữ lại những công cụ bạn thật sự dùng; không có SAM cũng hoàn toàn bình thường.

## 1. Bài đã nộp

**Bạn cần điền gì?** “File ZIP đúng tên” là tên file bạn đã tải từ CVAT rồi đặt lại, ví dụ `easy_semantic.zip`. “Hoàn thành mấy ảnh” là số ảnh bạn đã vẽ và Save, không phải số ảnh có trong task. Chưa làm hoặc export lỗi thì ghi `chưa có`, đừng ghi tên một ZIP rỗng. Cột điểm là **điểm tối đa của task**, không phải điểm tự chấm.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | easy_semantic.zip | 3 / 3 | 20 |
| medium_instance | medium_instance.zip | 3 / 3 | 32 |
| hard_panoptic | hard_panoptic.zip | 2 / 2 | 30 |
| cp1_holes | cp1_holes.zip | 1 / 1 | 3 |
| cp2_slice | cp2_slice.zip | 1 / 1 | 3 |
| cp5_occlusion | cp5_occlusion.zip | 1 / 1 | 3 |
| cp3_thin | cp3_thin.zip | 1 / 1 | 3 |
| cp4_curb | cp4_curb.zip | 1 / 1 | 3 |
| cp6_coverage | cp6_coverage | 1 / 1 | 3 |
| **Tổng tối đa** | | | **100** |

Không tự điền điểm nếu chưa có phản hồi từ người chấm. Nếu export lỗi, ghi task, trạng thái Save và thông báo đã gửi coach.

Ví dụ cách ghi lỗi export: “`cp3_thin`: đã Save 1/1 ảnh, CVAT không hiện Segmentation mask 1.1 lúc 14:10, đã báo coach”. Bạn vẫn ghi đúng tình trạng, không tự đổi format.

## 2. Một quyết định trước khi dùng gợi ý

**Mục này hỏi cách bạn tự ra quyết định.** Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi mở bất kỳ đề xuất tự động nào cho object đó. “Vị trí” chỉ cần mô tả đủ để tìm lại, chẳng hạn “xe bên trái, nửa dưới ảnh”; nếu nhớ tên file JPG thì ghi luôn. “Quy tắc biên” nghĩa là lý do bạn dừng mask ở đâu, nhất là mép ảnh hoặc vật che. Không cần ảnh chụp riêng nếu lớp không yêu cầu.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: 000000181542.jpg, người phụ nữ mặc áo dài ở chính giữa lệch sang trái 1 chút trên ảnh .
- Class và quy tắc tôi dùng để chọn biên: class person, tôi bám theo đường viền phần cơ thể nhìn thấy, chỉ phủ lên vùng thuộc người và dừng tại ranh giới với nền hoặc vật thể che khuất; không tô sang phần vật thể khác.
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: không dùng.
- Nếu không dùng gợi ý: **không dùng**; tôi tự xác định biên của `person` bằng cách quan sát đường viền cơ thể và chỉ gán phần người thực sự nhìn thấy. Ví dụ, tại các vùng bị vật thể khác che khuất, tôi dừng mask ở mép phần cơ thể quan sát được thay vì suy đoán và tô xuyên qua vật che.

Ví dụ cách giải thích, không phải đáp án cho ảnh của bạn: “Tôi chỉ vẽ phần thân xe còn nhìn thấy; phần sau cột bị che nên không đoán đường biên phía sau.” Nếu công cụ đưa vùng tràn ra nền, hãy ghi đã xóa vùng nào và vì sao. “Gợi ý đúng” cũng cần nói bạn đã kiểm điều gì rồi mới giữ.

## 3. Một lỗi tôi tìm thấy và sửa

**Chọn một lỗi có thật trong bài của bạn**, không cần lỗi lớn nhất. Một dòng tốt có thể là: “Tại `cp2_slice`, hai xe cùng lớp bị gộp thành một mask; nhìn thấy khe giữa hai xe; tôi tách thành hai object, Save và export lại.” Nếu chưa sửa được do công cụ lỗi, nói rõ đã thử gì và cần coach hỗ trợ gì; đừng ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: `medium_instance`, ảnh `000000181542.jpg`, vùng khuỷu tay của người phụ nữ ở giữa lệch trái ảnh.
- Lỗi thuộc loại: biên / phủ vùng.
- Bằng chứng tôi nhìn thấy: Mask của instance `person` bị phủ sang một vùng ở khuỷu tay không thuộc cơ thể người, làm biên của object rộng hơn phần người thực tế.
- Quy tắc và hành động sửa: Chỉ giữ phần mask nằm trên cơ thể người và cắt bỏ phần mask thừa ở vùng khuỷu tay. Tôi kiểm tra lại đường biên để không phủ sang nền hoặc vùng không thuộc instance `person`.
- Sau sửa đã Save và export lại chưa? Chưa; tôi đã sửa, Save và export lại thành công.

**Nếu đã xem điểm tự đánh giá trên GitHub Actions hoặc chạy scorer:** ghi một kết quả liên quan lỗi bạn vừa sửa, chẳng hạn “`easy_semantic`: per-class IoU của `sidewalk` tăng sau khi tôi sửa ranh bó vỉa, Save và export lại”; nếu chưa có điểm, ghi “chưa có”. Xem [hướng dẫn xem Summary hoặc chạy dự phòng](../docs/SELF_SCORING.md). Kết quả ba tier là tổng **/82**, không tự điền PASS, top 3 hoặc bonus. Đừng đưa ground truth vào fork.

**Kết quả tự đánh giá:** `medium_instance`: self-scoring hiện tại đạt `mean matched IoU = 0.795`, `P@0.5 = 0.71`, `R@0.5 = 0.83`. Lỗi tôi đã xử lý là biên mask của `person` bị phủ sang vùng không thuộc cơ thể ở khuỷu tay; tôi đã kiểm tra và chỉnh lại biên theo phần cơ thể thực tế.

**Kết quả ba tier:** **50.3/82**

## 4. Ba ca chưa chắc hoặc đã cân nhắc

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 000000350023.jpg | 1) `sidewalk`; 2) background/unlabeled | Khu vực này nằm giữa hai phần đường, không có đặc điểm rõ của lối đi bộ; không thuộc các vùng `road`, `sidewalk`, `building`, `vegetation`, `sky` theo cách tôi hiểu từ ảnh | Tôi chọn **background/unlabeled**, không gán `sidewalk`. |
| 000000460147.jpg | 1) Gộp chiếc ô tô vào instance `truck`; 2) Tách thành một instance `car` riêng | Chiếc ô tô và xe tải là hai vật thể khác nhau, có hình dạng và ranh giới riêng; việc xe được chở bởi truck không làm chiếc ô tô trở thành một phần của truck | Tôi chọn **tách riêng thành `car`**, không tính chiếc ô tô vào instance `truck`. |
| 817bca71-00000000.jpg | 1) Gán `road`; 2) background/unlabeled vì nắp cống không phải mặt đường | Không có class riêng cho nắp cống; nắp cống nằm trên bề mặt đường và không tạo thành một class được quy định riêng | Tôi chọn **`road`**, vì nếu không có class riêng thì vùng này thuộc bề mặt đường được gán nhãn. |

