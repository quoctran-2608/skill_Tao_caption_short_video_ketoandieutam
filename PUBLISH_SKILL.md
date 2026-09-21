# KẾ TOÁN DIỆU TÂM — SHORT VIDEO PUBLISH TO SHEET

## 1. Nhiệm vụ

Nhận **writing block Dữ liệu workflow đã được user duyệt** từ bước tạo content và ghi dữ liệu đó vào Google Sheet.

SKILL này không có nhiệm vụ sáng tạo caption.

Nguyên tắc quan trọng nhất:

**Giữ nguyên nội dung user đã duyệt.**

Không viết lại để “hay hơn”, không đổi hook, không đổi title, không tối ưu SEO lại, không thêm CTA, không đổi hashtag nếu user không yêu cầu.

## 2. Đầu vào

Đầu vào chuẩn là writing block **Dữ liệu workflow**, thường có cấu trúc:

- Video_ID / Ngày / Topic
- TikTok Caption + Hashtags
- Facebook Reels Caption + Hashtags
- YouTube Shorts Title + Description + Hashtags
- Zalo OA Title + Trích dẫn
- Cover
- QA
- Trạng thái

Có thể kèm thêm:

- Video_File_ID
- Thumbnail_File_ID
- Schedule_At

Nếu user dán cả dấu markdown của writing block, hãy tự đọc đúng các trường.

Bốn writing block đăng trực tiếp chỉ phục vụ copy/paste lên nền tảng. Khi có block **Dữ liệu workflow**, ưu tiên dùng block này làm nguồn ghi Sheet.

Không yêu cầu user chuyển sang JSON.

## 3. Kiểm tra trước khi ghi

Trước khi ghi Sheet, kiểm tra:

1. Có Video_ID hợp lệ hay chưa.
2. Có nội dung cần thiết của bốn nền tảng hay chưa.
3. Có trường nào đang là `CHƯA_GÁN` ảnh hưởng đến khóa dữ liệu hay không.
4. Có dữ liệu nào mâu thuẫn rõ ràng trong chính đầu vào hay không.

Nếu `Video_ID = CHƯA_GÁN` hoặc không có Video_ID:

- không ghi Sheet;
- báo ngắn rằng cần gán Video_ID trước.

Nếu nội dung nền tảng thiếu một trường không quan trọng cho việc ghi các nền tảng còn lại, vẫn ghi phần hợp lệ và báo rõ phần còn thiếu.

Không tự sáng tác dữ liệu thiếu.

## 4. Google Sheet

Workbook:

**Đăng VIDEO 30 NGÀY ĐẦU**

Spreadsheet ID:

`1RmOEywykglO1uhU3NDgDZdzlZajdpv5CCodIj9m3iCo`

Có hai tab.

### VIDEO_MASTER

Các cột:

`Video_ID`

`Day`

`Topic`

`Main_Message`

`Video_File_ID`

`Thumbnail_File_ID`

`Approval_Status`

`Script_QA`

### PUBLISH_QUEUE

Các cột:

`Publish_ID`

`Video_ID`

`Platform`

`Title`

`Caption`

`Hashtags`

`Schedule_At`

`Status`

`Post_URL`

`Error`

## 5. VIDEO_MASTER

Upsert theo `Video_ID`.

Không tạo duplicate.

Mapping:

- `Video_ID` = Video_ID đã duyệt
- `Day` = Ngày nếu có
- `Topic` = tên chủ đề ở heading
- `Main_Message` = thông điệp chính có thể rút ra ngắn gọn từ nội dung đã duyệt; không thêm ý mới
- `Video_File_ID` = giữ giá trị hiện có hoặc dùng giá trị user cung cấp
- `Thumbnail_File_ID` = giữ giá trị hiện có hoặc dùng giá trị user cung cấp
- `Approval_Status = APPROVED`
- `Script_QA` = nội dung QA nếu có; nếu QA là “Không có cảnh báo đáng chú ý.” thì có thể lưu câu đó hoặc để ngắn gọn theo cấu trúc hiện có

Không xóa `Video_File_ID` hoặc `Thumbnail_File_ID` đang có chỉ vì đầu vào mới không cung cấp.

## 6. PUBLISH_QUEUE

Upsert theo `Publish_ID`.

Không tạo duplicate.

### Publish_ID

Theo cấu trúc:

`Video_ID_PLATFORM`

Ví dụ:

- `KTD_V01_TIKTOK`
- `KTD_V01_FACEBOOK`
- `KTD_V01_YOUTUBE`
- `KTD_V01_ZALO`

### TikTok

`Platform = TIKTOK`

`Title = blank`

`Caption = caption TikTok đã duyệt`

`Hashtags = hashtag TikTok đã duyệt`

### Facebook

`Platform = FACEBOOK`

`Title = blank`

`Caption = caption Facebook đã duyệt`

`Hashtags = hashtag Facebook đã duyệt`

### YouTube

`Platform = YOUTUBE`

`Title = title YouTube đã duyệt`

`Caption = description hoàn chỉnh đã duyệt, bao gồm footer cố định`

`Hashtags = hashtag YouTube đã duyệt`

### Zalo

`Platform = ZALO`

`Title = title Zalo đã duyệt`

`Caption = trích dẫn Zalo đã duyệt`

`Hashtags = blank`

## 7. Status và Schedule

Nếu user cung cấp `Schedule_At`, dùng đúng giá trị đó.

Không tự đặt lịch nếu user chưa cung cấp.

Nếu nội dung đã APPROVED nhưng chưa có `Video_File_ID`:

`Status = DRAFT`

Nếu:

- nội dung đã APPROVED;
- có `Video_File_ID`;
- dữ liệu của nền tảng đó đầy đủ;

thì:

`Status = READY`

Nếu một dòng đã có:

`Status = PUBLISHED`

hoặc `Post_URL` đã có:

- không tạo job đăng lại;
- không ghi đè trạng thái xuất bản trừ khi user yêu cầu rõ ràng.

## 8. Nguyên tắc bảo toàn dữ liệu

Khi upsert:

- giữ `Post_URL` hiện có nếu đầu vào không cung cấp giá trị mới;
- giữ `Error` hiện có nếu không có lý do cập nhật;
- giữ media ID hiện có nếu đầu vào không cung cấp;
- không biến blank trong prompt thành lệnh xóa dữ liệu đang có;
- không sửa nội dung user đã duyệt chỉ vì model thấy có cách viết khác.

## 9. Kết quả sau khi ghi

Sau khi ghi thành công, trả lời ngắn gọn:

- Video_ID đã xử lý
- VIDEO_MASTER: đã upsert
- PUBLISH_QUEUE: các platform đã upsert
- Status hiện tại của từng platform nếu cần
- dữ liệu còn thiếu để chuyển sang READY, nếu có

Không trả lại toàn bộ caption nếu không cần.

Không tạo writing block mới trừ khi user yêu cầu.

## 10. Nguyên tắc cuối

SKILL này là bước **ghi dữ liệu**, không phải bước **sáng tạo nội dung**.

Workflow:

**Dữ liệu workflow đã duyệt → kiểm tra field → upsert VIDEO_MASTER → upsert PUBLISH_QUEUE → báo kết quả.**
