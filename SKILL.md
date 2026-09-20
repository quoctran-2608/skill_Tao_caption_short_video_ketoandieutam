# KẾ TOÁN DIỆU TÂM — SHORT VIDEO WORKFLOW

Workflow được tách thành 3 skill nhưng dùng chung trên một giao diện `index.html`.

## Bước 1 — Tạo nội dung

Dùng:

`CONTENT_SKILL.md`

Nhiệm vụ:

**Nguồn video → nội dung TikTok / Facebook Reels / YouTube Shorts / Zalo OA + Cover Text → writing block DRAFT**

Giao diện:

`index.html` — Bước 1

## Kết quả đã duyệt

Sau khi ChatGPT trả writing block:

- user kiểm tra;
- user chốt;
- copy nguyên writing block;
- dán một lần vào ô **Kết quả đã duyệt từ ChatGPT**.

Dữ liệu này được dùng chung cho Bước 2 và Bước 3.

## Bước 2 — Tạo ảnh bìa

Dùng:

`COVER_SKILL.md`

Nhiệm vụ:

**Writing block đã duyệt + một frame chụp từ video → một ảnh bìa dọc 9:16**

Giao diện:

`index.html` — Bước 2

User copy prompt cover sang ChatGPT và đính kèm một frame thật từ video.

Cover Skill dùng đúng Cover Text đã duyệt và không tự tạo bối cảnh thay thế nếu chưa có frame.

## Bước 3 — Ghi Google Sheet

Dùng:

`PUBLISH_SKILL.md`

Nhiệm vụ:

**Writing block đã duyệt → giữ nguyên nội dung → upsert VIDEO_MASTER + PUBLISH_QUEUE**

Giao diện:

`index.html` — Bước 3

Có thể bổ sung:

- `Video_File_ID`
- `Thumbnail_File_ID`
- `Schedule_At`

nếu đã có.

## Workflow

**Nguồn video → index.html/Bước 1 → ChatGPT → writing block → user duyệt → dán một lần vào kết quả đã duyệt → Bước 2 tạo cover → Bước 3 ghi Sheet**

Không dùng file này làm skill thực thi. Hãy dùng đúng skill của từng bước ở trên.
