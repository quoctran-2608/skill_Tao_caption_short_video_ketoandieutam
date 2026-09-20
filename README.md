# skill_Tao_caption_short_video_ketoandieutam

Công cụ tạo prompt để viết nội dung đăng short video cho **Kế Toán Diệu Tâm**.

## Cấu trúc

- `SKILL.md`: nguồn chuẩn duy nhất của skill.
- `index.html`: giao diện dán kịch bản / transcript / subtitle / production script → tạo prompt → copy prompt.

## Cách dùng

1. Mở `index.html` bằng trình duyệt hoặc host repo bằng GitHub Pages.
2. Dán nguyên nguồn nội dung video vào ô **Nguồn nội dung video**. Có thể là kịch bản, transcript, subtitle hoặc production script.
3. Bấm **Tạo prompt**.
4. Bấm **Copy prompt**.
5. Dán nguyên prompt vào AI.

`index.html` không chứa một bản skill riêng. Trang sẽ tải trực tiếp `SKILL.md`, vì vậy khi cập nhật skill chỉ cần sửa một file.

## Nguyên tắc thiết kế

- Không gọi API AI.
- Không cần API key.
- Không lưu kịch bản vào backend.
- Không tự đăng bài.
- HTML chỉ làm nhiệm vụ ghép `SKILL.md` + nguồn nội dung video thành prompt hoàn chỉnh.

## Workflow

`Nguồn video → Prompt Builder → AI → Duyệt → Google Sheet → Publishing Agent`
