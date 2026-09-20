# skill_Tao_caption_short_video_ketoandieutam

Bộ công cụ tạo prompt cho quy trình short video của **Kế Toán Diệu Tâm**.

Hai skill vẫn tách riêng về logic, nhưng người dùng thao tác toàn bộ trên **một trang duy nhất**.

## Cấu trúc

- `CONTENT_SKILL.md`: Skill Bước 1 — tạo nội dung đa kênh.
- `PUBLISH_SKILL.md`: Skill Bước 2 — ghi nội dung đã duyệt vào Google Sheet.
- `index.html`: giao diện duy nhất cho cả hai bước.
- `publish.html`: file chuyển hướng cũ về Bước 2 trong `index.html`.
- `SKILL.md`: hướng dẫn cấu trúc workflow, không dùng làm skill thực thi.

## Cách dùng

### Bước 1 — Tạo nội dung

1. Mở `index.html`.
2. Dán nguồn video: kịch bản, transcript, subtitle, production script hoặc nội dung hỗn hợp.
3. Bấm **Tạo prompt Bước 1**.
4. Bấm **Copy prompt Bước 1**.
5. Dán prompt vào ChatGPT.
6. ChatGPT trả toàn bộ nội dung TikTok / Facebook / YouTube / Zalo trong **một writing block**.
7. Kiểm tra và duyệt nội dung.

### Bước 2 — Ghi Sheet

1. Quay lại cùng trang `index.html` và cuộn xuống Bước 2.
2. Copy nguyên writing block đã duyệt từ ChatGPT và dán vào ô **Writing block đã duyệt**.
3. Nếu có, thêm `Video_File_ID`, `Thumbnail_File_ID` hoặc `Schedule_At` bên dưới.
4. Bấm **Tạo prompt Bước 2**.
5. Bấm **Copy prompt Bước 2**.
6. Dán prompt vào ChatGPT có quyền truy cập Google Sheet.
7. ChatGPT giữ nguyên nội dung đã duyệt và upsert dữ liệu vào `VIDEO_MASTER` + `PUBLISH_QUEUE`.

## Nguyên tắc thiết kế

- Một trang giao diện, hai bước tuần tự từ trên xuống.
- Hai skill vẫn tách riêng để AI tập trung đúng nhiệm vụ.
- Bước 1 không ghi Sheet.
- Bước 2 không viết lại caption nếu user không yêu cầu.
- HTML chỉ ghép skill + dữ liệu đầu vào thành prompt.
- Không gọi API AI.
- Không cần API key.
- Không lưu nội dung vào backend riêng.

## Workflow

`Nguồn video → Prompt Bước 1 → ChatGPT → writing block → duyệt → Prompt Bước 2 → ChatGPT → Google Sheet`
