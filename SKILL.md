# KẾ TOÁN DIỆU TÂM — SHORT VIDEO WORKFLOW

Skill cũ đã được tách thành 2 bước để mỗi prompt tập trung đúng một nhiệm vụ.

## Bước 1 — Tạo nội dung

Dùng:

`CONTENT_SKILL.md`

Nhiệm vụ:

**Nguồn video → nội dung TikTok / Facebook Reels / YouTube Shorts / Zalo OA → writing block DRAFT**

Prompt Builder:

`index.html`

## Bước 2 — Ghi Google Sheet

Dùng:

`PUBLISH_SKILL.md`

Nhiệm vụ:

**Writing block đã duyệt → giữ nguyên nội dung → upsert VIDEO_MASTER + PUBLISH_QUEUE**

Prompt Builder:

`publish.html`

## Workflow

**Nguồn video → index.html → ChatGPT → writing block → user duyệt → publish.html → ChatGPT → Google Sheet**

Không dùng file này làm skill thực thi. Hãy dùng đúng skill của từng bước ở trên.
