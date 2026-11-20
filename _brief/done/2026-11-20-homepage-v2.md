# Brief: Homepage v2 — trust signals, services, process
Ngày: 2026-11-20
Trạng thái: ready

## Mục tiêu
Khách/nhà tuyển dụng thấy ngay kết quả + cách liên hệ mà không cần cuộn nhiều;
phần "What I do" đọc như gói dịch vụ có bằng chứng; thêm quy trình làm việc.

## Mockup tham chiếu
- `_brief/mockups/index-v2.html` — mở bằng trình duyệt để xem (dùng chung style.css thật).
- Ảnh chụp: `_brief/mockups/v2-hero-desktop.png`, `v2-full-desktop.png`, `v2-full-mobile.png`
- Toàn bộ CSS mới nằm trong khối `<style>` "NEW in v2" của mockup → chuyển vào `style.css`.

## Trang bị ảnh hưởng
- [x] index.html
- [x] style.css (bump `style.css?v=16` → `v=17` trên MỌI trang)

## Thay đổi cụ thể
1. **Hero CTA:** thay nút "Explore Expertise" bằng 3 nút: `Connect now ↗` (primary, mở `#contact-dialog`),
   `View My Work →` (secondary), `Download CV ↓` (ghost, link `cv.pdf`).
   JS: đổi `querySelector('.contact-trigger')` thành `querySelectorAll` để mọi nút `.contact-trigger` mở dialog.
0. **Ảnh đại diện trong hero:** ảnh tròn 64px (`portrait.jpg`) + 2 dòng giới thiệu
   "Hi, I’m Dustin Nguyen" / "Based in Vietnam, I specialize in helping you with ↓"
   (câu này nối thẳng xuống tiêu đề "Turning Data Into Business Growth."), đặt trên tiêu đề (`.hero-intro`).
   BỎ badge "Open to opportunities" (xoá khỏi hero, không giữ ở chỗ khác). Ảnh lớn ở About giữ nguyên.
2. **Headline results** trong panel "Experience at a glance": khối 3 ô theo thứ tự +41% Contracts · Home Credit,
   22.1x ROAS · Logitech, +160% Revenue · Avène; mỗi ô link sang case study tương ứng.
3. **Hiệu ứng:** count-up cho các số có `data-count` (5B, 20+, 5+, 22.1x, +160%, +41%) và
   chạy ~1.6s rồi dừng đúng ở giá trị cuối; số nhỏ (5B, 5+) chạy theo số thập phân (0.0 → 5.0) rồi chốt "5"
   cho mượt, xem JS trong mockup. Và reveal-on-scroll cho `.reveal` (thẻ dịch vụ, bước quy trình, project rows).
   Bắt buộc: tắt hoàn toàn khi `prefers-reduced-motion: reduce`; không JS thì nội dung vẫn hiện đủ.
4. **What I do:** mỗi thẻ thêm "What you get" (3 gạch đầu dòng), "Measured by" (KPI), và khối "Proven"
   = kết quả thật + tên project (KHÔNG hiển thị ngân sách khách hàng), link sang case study. Dùng đúng nội dung trong mockup:
   - Awareness: +125% total user reach · Home Credit · Brand Awareness → homecredit-brand-awareness.html
   - Consideration: Brand search impression share 78% → 90% · Home Credit · Brand Awareness → homecredit-brand-awareness.html
   - Conversion: +41% cash loan contracts · Home Credit · Cash Loan Acquisition → homecredit-customer-acquisition.html
   - Retention: +25% monthly active users · Home Credit · App Retention → homecredit-app-retention.html
5. **How I work:** section mới `#process` giữa What I do và Selected Work, 5 bước Audit → Plan → Launch → Optimize → Report.
   Thêm "Process" vào nav.
6. **Dải nền tảng** chạy ngang ngay dưới hero (kênh + công cụ đo lường), dừng khi hover,
   đứng yên và xuống dòng khi reduced-motion.
8. **Download CV:** nút ở hero + trong contact dialog, link `cv.pdf` ở thư mục gốc.

9. **Thống nhất nhãn CTA = "Connect now ↗"** ở MỌI chỗ: nút header (`.header-cta`, hiện là "Let’s Connect"),
   nút hero, nút cuối trang (hiện là "Contact now"), và nút header trên 5 trang case study.
   Grep `Let’s Connect` và `Contact now` để không sót.

## Không được đổi
- Không đưa ngân sách theo project/khách hàng lên site.
- Nội dung các trang case study, số liệu hiện có, màu/typography hiện tại.
- KHÔNG đưa `.mockup-badge` và đường dẫn `../../` của mockup vào site thật.

## Đang chờ
- `cv.pdf`: Dustin sẽ bỏ file vào thư mục gốc. Nếu chưa có khi làm → ẩn 2 nút Download CV (comment lại), đừng để link hỏng.
- Mục 7 (testimonials) để đợt sau.

## Ghi chú cho Claude Code
- Làm trên nhánh `claude/homepage-v2`, kiểm tra desktop + mobile (390px), cho Dustin xem diff,
  chỉ merge vào `main` và push khi được đồng ý.
- Xong thì chuyển brief này vào `_brief/done/2026-11-20-homepage-v2.md`.
