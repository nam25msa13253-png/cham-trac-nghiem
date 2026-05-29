# Hướng dẫn đưa app lên GitHub Pages (cho người không biết lập trình)

App sẽ có link công khai dạng: `https://YOUR_USERNAME.github.io/cham-trac-nghiem/` — ai cũng truy cập được.

**Hoàn toàn miễn phí. Không cần cài đặt gì. Chỉ làm 1 lần.**

---

## Bước 1: Tạo tài khoản GitHub (nếu chưa có)

1. Vào https://github.com/signup
2. Đăng ký bằng email (chọn username dễ nhớ, ví dụ: `nam-hht` → link sẽ là `nam-hht.github.io/cham-trac-nghiem`)
3. Verify email

## Bước 2: Tạo repository mới

1. Sau khi đăng nhập, click nút **"+"** góc trên-phải → **"New repository"**
2. Đặt:
   - **Repository name**: `cham-trac-nghiem` (dùng dấu gạch ngang, không dấu, không khoảng trắng)
   - **Description**: `Chấm trắc nghiệm tự động`
   - Chọn **Public** (bắt buộc để dùng GitHub Pages miễn phí)
   - Tick **"Add a README file"**
3. Click **"Create repository"**

## Bước 3: Upload 3 file của app

Trong repository vừa tạo:

1. Click nút **"Add file"** → **"Upload files"**
2. Kéo thả 3 file này vào:
   - `cham-trac-nghiem.html` (app chính)
   - `index.html` (file redirect)
   - `README.md` (ghi đè file README mặc định nếu hỏi)
3. Cuộn xuống dưới, mục **"Commit changes"**, click nút xanh **"Commit changes"**

## Bước 4: Bật GitHub Pages

1. Trong repository, click tab **"Settings"** (ở phía trên)
2. Cột menu trái, kéo xuống tìm **"Pages"** → click
3. Mục **"Source"**: chọn **"Deploy from a branch"**
4. Mục **"Branch"**:
   - Chọn **`main`**
   - Folder để **`/ (root)`**
   - Click **"Save"**
5. Đợi 1-2 phút.

## Bước 5: Lấy link

1. Refresh trang Settings → Pages
2. Sẽ thấy dòng: **"Your site is live at https://YOUR_USERNAME.github.io/cham-trac-nghiem/"**
3. Click vào link → mở app
4. **Copy link này → gửi cho đồng nghiệp / SV / bất kỳ ai** đều dùng được

---

## Khi muốn cập nhật app (sửa code, thêm tính năng)

1. Vào repository GitHub
2. Click file `cham-trac-nghiem.html` → click icon **bút chì** (Edit)
3. Sửa nội dung → cuộn xuống → **"Commit changes"**
4. Đợi 1-2 phút → link tự cập nhật

Hoặc upload lại file mới (Add file → Upload files → ghi đè).

---

## Một số lưu ý quan trọng

### Về bảo mật
- Tất cả ai có link đều dùng được app
- **Dữ liệu của thầy (điểm, danh sách lớp) KHÔNG bị gửi đi đâu** — chỉ lưu trong trình duyệt của người đang dùng
- App KHÔNG có server backend, không có database

### Về Excel + OCR (đã cấu hình sẵn)
- Bộ thư viện Excel (SheetJS) và OCR (Tesseract.js) được tải từ CDN bên ngoài
- Lần đầu mở app sau khi deploy: cần internet để tải các thư viện này (~6MB)
- Sau đó browser cache lại → dùng offline được

### Về tốc độ
- App chạy hoàn toàn ở phía trình duyệt (client-side)
- GitHub Pages chỉ host file tĩnh, không tốn tài nguyên server
- Nhiều người dùng cùng lúc không ảnh hưởng tốc độ

### Khi muốn dùng tên miền riêng (ví dụ `chamdiem.hht.edu.vn`)
1. Mua tên miền (Tenten / Pavietnam / Namecheap / GoDaddy...)
2. Trong DNS settings của tên miền, trỏ CNAME đến `YOUR_USERNAME.github.io`
3. Trong GitHub Settings → Pages → Custom domain: nhập tên miền
4. Tick "Enforce HTTPS"

---

## Troubleshooting

**Q: Sau khi commit, link vẫn lỗi 404?**
A: Đợi 5-10 phút lần đầu. Vào Actions tab xem deployment progress. Nếu vẫn lỗi, kiểm tra Settings → Pages → Branch đã chọn đúng `main` và folder `/ (root)`.

**Q: App load chậm lần đầu?**
A: Bình thường — tải Tesseract.js (~5MB). Các lần sau browser cache rồi sẽ nhanh.

**Q: SV bảo không mở được trên điện thoại?**
A: Chrome/Safari mobile đều OK. Nhưng giao diện tối ưu cho desktop. Có thể thêm meta viewport responsive nếu cần.

**Q: Muốn tắt public, chỉ cho 1 nhóm dùng?**
A: GitHub Pages public yêu cầu repo public. Nếu muốn private, cần GitHub Pro (4 USD/tháng) → cho phép private repo + Pages.
