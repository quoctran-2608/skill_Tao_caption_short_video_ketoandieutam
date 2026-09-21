# KẾ TOÁN DIỆU TÂM — SHORT VIDEO WORKFLOW

Workflow được tách thành 3 skill nhưng dùng chung trên `index.html`.

## Bước 1 — Content

Dùng `CONTENT_SKILL.md`.

Kết quả gồm **4 khối copy nền tảng + 1 writing block Dữ liệu workflow**:

1. TikTok
2. Facebook Reels
3. YouTube Shorts
4. Zalo OA
5. Dữ liệu workflow

Bốn khối đầu phục vụ copy/paste trực tiếp lên nền tảng. Hashtag nằm ngay cuối caption/description.

Block **Dữ liệu workflow** giữ field có cấu trúc và là block duy nhất cần copy sang bước tiếp theo.

## Bước 2 — Cover

Dùng `COVER_SKILL.md`.

Đầu vào:

**Dữ liệu workflow đã duyệt + một frame chụp từ video**

Kết quả:

**một ảnh bìa dọc 9:16**

Cover Skill dùng nguyên văn Cover Text đã duyệt.

## Bước 3 — Publish

Dùng `PUBLISH_SKILL.md`.

Đầu vào:

**Dữ liệu workflow đã duyệt**

Có thể bổ sung:

- `Video_File_ID`
- `Thumbnail_File_ID`
- `Schedule_At`

PUBLISH SKILL giữ nguyên nội dung, tách Caption và Hashtags theo field trong Dữ liệu workflow rồi upsert `VIDEO_MASTER` + `PUBLISH_QUEUE`.

## Workflow

**Nguồn video → 4 block đăng trực tiếp + Dữ liệu workflow → Cover → Publish → Google Sheet**

Không dùng file này làm skill thực thi.
