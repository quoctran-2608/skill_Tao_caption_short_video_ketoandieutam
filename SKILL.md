# KẾ TOÁN DIỆU TÂM — SHORT VIDEO WORKFLOW

Skill cũ đã được tách thành 2 bước để mỗi prompt tập trung đúng một nhiệm vụ.

## Bước 1 — Tạo nội dung

Dùng:

`CONTENT_SKILL.md`

Nhiệm vụ:

**Nguồn video → nội dung TikTok / Facebook Reels / YouTube Shorts / Zalo OA → writing block DRAFT**

Giao diện:

`index.html` — phần Bước 1

## Bước 2 — Ghi Google Sheet

Dùng:

`PUBLISH_SKILL.md`

Nhiệm vụ:

**Writing block đã duyệt → giữ nguyên nội dung → upsert VIDEO_MASTER + PUBLISH_QUEUE**

Giao diện:

`index.html` — phần Bước 2

## Workflow

**Nguồn video → index.html/Bước 1 → ChatGPT → writing block → user duyệt → index.html/Bước 2 → ChatGPT → Google Sheet**

Không dùng file này làm skill thực thi. Hãy dùng đúng skill của từng bước ở trên.
