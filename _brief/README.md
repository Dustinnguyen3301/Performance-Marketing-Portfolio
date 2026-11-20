# _brief — nơi trao đổi giữa Claude và Claude Code

Thư mục này KHÔNG xuất hiện trên website (GitHub Pages bỏ qua thư mục bắt đầu bằng `_`).
Lưu ý: repo GitHub là public thì file ở đây vẫn xem được trên github.com — đừng để thông tin nhạy cảm.

## Quy trình
1. **Claude (app):** brainstorm, viết nội dung, làm mockup → lưu vào đây:
   - `brief.md`: yêu cầu thay đổi hiện tại
   - `content/`: nội dung đã chốt (markdown)
   - `mockups/`: mockup đã chốt
2. **Claude Code:** "Đọc _brief/brief.md và làm theo, cho mình xem diff trước khi push."
3. Duyệt xong: "Merge vào main và push." → web cập nhật sau 1–2 phút.
4. Claude Code chuyển brief cũ vào `done/` và tạo lại `brief.md` trống.

## Template brief.md

```markdown
# Brief: <tên thay đổi>
Ngày: YYYY-MM-DD
Trạng thái: draft | ready | shipped

## Mục tiêu
<Thay đổi này để làm gì>

## Trang bị ảnh hưởng
- [ ] index.html (section: ...)
- [ ] <case-study>.html

## Thay đổi cụ thể
1. ...

## Nội dung / mockup đi kèm
- content/<file>.md
- mockups/<file>.html

## Không được đổi
- ...

## Ghi chú cho Claude Code
- ...
```
