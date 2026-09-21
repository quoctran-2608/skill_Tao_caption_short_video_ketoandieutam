# skill_Tao_caption_short_video_ketoandieutam

Bộ công cụ tạo prompt cho quy trình short video của **Kế Toán Diệu Tâm**.

Người dùng thao tác trên **một trang duy nhất**, còn logic được tách thành 3 skill.

## Cấu trúc

- `CONTENT_SKILL.md`: Bước 1 — tạo nội dung đa kênh, Cover Text và Dữ liệu workflow.
- `COVER_SKILL.md`: Bước 2 — dùng Dữ liệu workflow + frame video để tạo ảnh bìa 9:16.
- `PUBLISH_SKILL.md`: Bước 3 — ghi Dữ liệu workflow đã duyệt vào Google Sheet.
- `index.html`: giao diện duy nhất cho cả 3 bước.
- `publish.html`: file chuyển hướng cũ về Bước 3.
- `SKILL.md`: hướng dẫn cấu trúc workflow.

## Bước 1 — Tạo nội dung

1. Dán nguồn video vào `index.html`.
2. Tạo prompt và copy sang ChatGPT.
3. ChatGPT trả **5 writing block**:
   - TikTok
   - Facebook Reels
   - YouTube Shorts
   - Zalo OA
   - Dữ liệu workflow
4. Bốn block nền tảng được tối ưu để copy/paste nhanh. Hashtag nằm ngay cuối caption/description, không tách thành một mục riêng.
5. Block **Dữ liệu workflow** giữ các field có cấu trúc để dùng cho Cover và Publish.

## Độ dài và hình thức

- TikTok: 1–3 câu; thường khoảng 100–250 ký tự phần caption chính; 3–5 hashtag.
- Facebook Reels: 1–3 câu; thường khoảng 100–220 ký tự phần caption chính; 2–4 hashtag.
- YouTube Shorts: description động 1–2 câu; thường khoảng 100–180 ký tự; footer cố định; 3–5 hashtag.
- Zalo OA: trích dẫn 1–2 câu; thường khoảng 120–240 ký tự; tối đa 300; không hashtag.
- Emoji mặc định không dùng; chỉ dùng 0–1 khi thực sự có ích và tự nhiên.
- Các vùng độ dài là khuyến nghị, không phải quota.

## Kết quả đã duyệt

Sau khi duyệt Bước 1:

1. Copy **chỉ writing block Dữ liệu workflow**.
2. Dán một lần vào ô **Kết quả đã duyệt từ ChatGPT** trong `index.html`.

Bước 2 và Bước 3 cùng dùng lại block này. Không cần dán lại kịch bản hoặc 4 block nền tảng.

## Bước 2 — Tạo ảnh bìa

1. Bấm **Tạo prompt ảnh bìa**.
2. Copy prompt sang ChatGPT.
3. Đính kèm một frame đẹp từ chính video.
4. ChatGPT dùng Cover Text đã duyệt + frame thật để tạo cover dọc 9:16.

## Bước 3 — Ghi Sheet

1. Dữ liệu workflow được lấy từ ô dùng chung.
2. Có thể bổ sung `Video_File_ID`, `Thumbnail_File_ID`, `Schedule_At`.
3. Tạo prompt Bước 3 và copy sang ChatGPT có quyền truy cập Google Sheet.
4. PUBLISH SKILL tách Caption và Hashtags từ Dữ liệu workflow để ghi đúng cột.

## Workflow

`Nguồn video → 4 block đăng trực tiếp + Dữ liệu workflow → Cover → Publish → Google Sheet`
