# skill_Tao_caption_short_video_ketoandieutam

Bộ công cụ tạo prompt cho quy trình short video của **Kế Toán Diệu Tâm**.

Người dùng thao tác toàn bộ trên **một trang duy nhất**, còn logic được tách thành 3 skill để ChatGPT tập trung đúng nhiệm vụ.

## Cấu trúc

- `CONTENT_SKILL.md`: Bước 1 — tạo nội dung đa kênh và Cover Text.
- `COVER_SKILL.md`: Bước 2 — dùng nội dung đã duyệt + frame video để tạo ảnh bìa 9:16.
- `PUBLISH_SKILL.md`: Bước 3 — ghi nội dung đã duyệt vào Google Sheet.
- `index.html`: giao diện duy nhất cho cả 3 bước.
- `publish.html`: file chuyển hướng cũ về Bước 3 trong `index.html`.
- `SKILL.md`: hướng dẫn cấu trúc workflow, không dùng làm skill thực thi.

## Bước 1 — Tạo nội dung

1. Mở `index.html`.
2. Dán nguồn video: kịch bản, transcript, subtitle, production script hoặc nội dung hỗn hợp.
3. Bấm **Tạo prompt Bước 1**.
4. Copy prompt sang ChatGPT.
5. ChatGPT trả toàn bộ nội dung TikTok / Facebook / YouTube / Zalo và Cover Text trong **một writing block**.
6. Kiểm tra và duyệt.

## Kết quả đã duyệt

Sau khi chốt Bước 1:

1. Copy nguyên writing block từ ChatGPT.
2. Dán **một lần duy nhất** vào ô **Kết quả đã duyệt từ ChatGPT** trong `index.html`.

Bước 2 và Bước 3 cùng dùng lại ô này. Không cần dán lại kịch bản gốc.

## Bước 2 — Tạo ảnh bìa

1. Bấm **Tạo prompt ảnh bìa**.
2. Copy prompt sang ChatGPT.
3. Đính kèm một ảnh chụp khung hình đẹp từ chính video.
4. Gửi prompt.
5. ChatGPT dùng Cover Text đã duyệt + frame thật để tạo một ảnh bìa dọc 9:16.

Nếu chưa có frame đính kèm, Cover Skill không tự tưởng tượng bối cảnh thay thế.

## Bước 3 — Ghi Sheet

1. Nội dung đã duyệt được lấy tự động từ ô dùng chung.
2. Nếu có, điền thêm `Video_File_ID`, `Thumbnail_File_ID` hoặc `Schedule_At`.
3. Bấm **Tạo prompt Bước 3**.
4. Copy prompt sang ChatGPT có quyền truy cập Google Sheet.
5. ChatGPT giữ nguyên nội dung đã duyệt và upsert dữ liệu vào `VIDEO_MASTER` + `PUBLISH_QUEUE`.

## Nguyên tắc thiết kế

- Một trang giao diện, ba bước tuần tự từ trên xuống.
- Writing block đã duyệt chỉ dán một lần.
- Bước 1 quyết định nội dung và Cover Text.
- Bước 2 quyết định cách trình bày hình ảnh; không tự đổi Cover Text.
- Bước 3 ghi dữ liệu; không viết lại caption nếu user không yêu cầu.
- HTML chỉ ghép skill + dữ liệu thành prompt.
- Không gọi API AI.
- Không cần API key.
- Không lưu nội dung vào backend riêng.

## Workflow

`Nguồn video → Content → writing block đã duyệt → Cover → Publish → Google Sheet`
