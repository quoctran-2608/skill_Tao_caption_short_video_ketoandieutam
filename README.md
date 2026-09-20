# skill_Tao_caption_short_video_ketoandieutam

Bộ công cụ tạo prompt cho quy trình short video của **Kế Toán Diệu Tâm**.

Workflow được tách thành 2 bước đơn giản để ChatGPT tập trung đúng nhiệm vụ ở từng lần chạy.

## Cấu trúc

- `CONTENT_SKILL.md`: skill Bước 1 — tạo nội dung đa kênh.
- `PUBLISH_SKILL.md`: skill Bước 2 — ghi nội dung đã duyệt vào Google Sheet.
- `index.html`: Prompt Builder cho Bước 1.
- `publish.html`: Prompt Builder cho Bước 2.
- `SKILL.md`: file hướng dẫn cấu trúc mới, không dùng làm skill thực thi.

## Bước 1 — Tạo nội dung

1. Mở `index.html`.
2. Dán nguồn video: kịch bản, transcript, subtitle, production script hoặc nội dung hỗn hợp.
3. Bấm **Tạo prompt**.
4. Bấm **Copy prompt**.
5. Dán prompt vào ChatGPT.
6. ChatGPT trả toàn bộ nội dung TikTok / Facebook / YouTube / Zalo trong **một writing block**.
7. Kiểm tra và duyệt nội dung.

Bước 1 không ghi Google Sheet.

## Bước 2 — Ghi Sheet

1. Copy nguyên writing block đã duyệt.
2. Mở `publish.html`.
3. Dán writing block vào ô đầu vào.
4. Nếu có thể, thêm `Video_File_ID`, `Thumbnail_File_ID` hoặc `Schedule_At` bên dưới.
5. Bấm **Tạo prompt ghi Sheet**.
6. Copy prompt sang ChatGPT có quyền truy cập Google Sheet.
7. ChatGPT giữ nguyên nội dung đã duyệt và upsert dữ liệu vào `VIDEO_MASTER` + `PUBLISH_QUEUE`.

Bước 2 không viết lại caption nếu user không yêu cầu.

## Nguyên tắc thiết kế

- Hai HTML chỉ ghép skill + dữ liệu đầu vào thành prompt.
- Không gọi API AI.
- Không cần API key.
- Không lưu nội dung vào backend riêng.
- Skill được tải trực tiếp từ file Markdown tương ứng trong repo để tránh lệch phiên bản.

## Workflow

`Nguồn video → index.html → ChatGPT → writing block → duyệt → publish.html → ChatGPT → Google Sheet`
