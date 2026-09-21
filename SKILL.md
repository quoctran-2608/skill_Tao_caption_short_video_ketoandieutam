# KẾ TOÁN DIỆU TÂM — SHORT VIDEO WORKFLOW

Workflow có 3 bước trên `index.html`.

## Bước 1 — Content

Dùng `CONTENT_SKILL.md`.

Kết quả:

1. TikTok
2. Facebook Reels
3. YouTube Shorts
4. Zalo OA
5. **Bản tổng hợp**

Bốn khối đầu dùng để copy/paste trực tiếp. **Bản tổng hợp** là khối dùng cho các bước sau.

CONTENT SKILL dùng một **Content Core duy nhất** làm nguồn nghĩa cho cả bốn nền tảng:

- Chủ thể cốt lõi: video thực sự nói về cái gì;
- Thông điệp cốt lõi: video muốn người xem hiểu gì về chủ thể đó.

Không tạo bốn bản tóm tắt độc lập. TikTok/Facebook phải tự làm rõ chủ thể trong caption; YouTube và Zalo được đánh giá theo cụm Title + phần mô tả.

## Bước 2 — Cover

Dùng `COVER_SKILL.md`.

Đầu vào:

- **Bản tổng hợp** đã chốt;
- một frame từ video;
- **Chữ trên ảnh bìa** nếu user muốn tự nhập.

Ưu tiên chữ trên ảnh:

**user nhập → Cover Text trong Bản tổng hợp → tự tạo nếu thiếu.**

Kết quả: một ảnh bìa dọc 9:16.

## Bước 3 — Publish

Dùng `PUBLISH_SKILL.md`.

Đầu vào: **Bản tổng hợp** đã chốt.

Có thể bổ sung `Video_File_ID`, `Thumbnail_File_ID`, `Schedule_At`.

PUBLISH SKILL giữ nguyên nội dung và upsert `VIDEO_MASTER` + `PUBLISH_QUEUE`.

## Workflow

**Nguồn video → Content → Bản tổng hợp → Cover → Publish → Google Sheet**

Không dùng file này làm skill thực thi.
