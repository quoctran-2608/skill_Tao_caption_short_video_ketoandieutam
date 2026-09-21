# skill_Tao_caption_short_video_ketoandieutam

Bộ công cụ tạo prompt cho quy trình short video của **Kế Toán Diệu Tâm**.

## Cấu trúc

- `CONTENT_SKILL.md`: tạo nội dung TikTok, Facebook Reels, YouTube Shorts, Zalo OA và Cover Text đề xuất.
- `COVER_SKILL.md`: tạo ảnh bìa 9:16 từ Bản tổng hợp + frame video.
- `PUBLISH_SKILL.md`: ghi Bản tổng hợp đã chốt vào Google Sheet.
- `index.html`: giao diện 3 bước.

## Bước 1 — Tạo nội dung

1. Dán nguồn video.
2. Tạo prompt và gửi sang ChatGPT.
3. ChatGPT trả 4 khối copy để đăng và 1 **Bản tổng hợp**.

Bốn khối nền tảng đã gắn hashtag vào cuối caption/description để copy nhanh.

## Content Core

Bước 1 không tạo bốn bản tóm tắt độc lập.

CONTENT SKILL:

1. hiểu nguồn một lần;
2. chốt một **Content Core** gồm Chủ thể cốt lõi + Thông điệp cốt lõi;
3. tạo bốn phiên bản nền tảng từ cùng Content Core;
4. validation từng phiên bản lại với Content Core trước khi trả kết quả.

TikTok và Facebook phải tự làm rõ Chủ thể cốt lõi trong caption. YouTube được đánh giá theo Title + Description; Zalo theo Title + Trích dẫn. Hashtag không được dùng để bù cho caption thiếu chủ đề.

## Bước 2 — Tạo ảnh bìa

1. Dán **Bản tổng hợp** vào ô **Nội dung đã chốt**.
2. Nếu muốn tự chọn chữ trên ảnh, nhập **Chữ trên ảnh bìa**.
3. Để trống field này thì dùng Cover Text AI đã đề xuất trong Bản tổng hợp.
4. Tạo prompt, gửi sang ChatGPT và đính kèm một frame từ video.

Thứ tự ưu tiên chữ trên ảnh:

**user nhập → Cover Text trong Bản tổng hợp → Cover Skill tự tạo nếu thiếu cả hai.**

## Bước 3 — Ghi Sheet

Bước 3 dùng lại **Nội dung đã chốt** ở Bước 2.

Có thể bổ sung:

- `Video_File_ID`
- `Thumbnail_File_ID`
- `Schedule_At`

Sau đó tạo prompt Publish và gửi sang ChatGPT có quyền truy cập Google Sheet.

## Workflow

`Nguồn video → Content → Bản tổng hợp → Cover → Publish → Google Sheet`
