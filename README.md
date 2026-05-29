# Chấm trắc nghiệm tự động

Web app chấm bài trắc nghiệm bằng ảnh chụp — không cần cài đặt, chạy trên trình duyệt.

**Trường CĐ Công Nghệ Cao Hà Nội** · v3.1 · Giao diện Glassmorphism, font Times New Roman, thân thiện với mọi lứa tuổi

## Tính năng chính

- Auto-detect lưới phiếu bằng OCR số câu (per-cell, robust với ảnh cong/nghiêng)
- Phân biệt dấu X (chọn) và ô tô đen (huỷ chọn)
- Lọc mực xanh + OCR tên SV viết tay, fuzzy match với danh sách lớp
- Quét đáp án từ ảnh bảng in (cũng bằng OCR)
- Sửa tay từng câu, điểm cập nhật real-time
- Xuất file Excel/CSV hoặc copy-paste vào Google Sheet

## Sử dụng online

Truy cập: **`https://[username].github.io/cham-trac-nghiem/`**
(thay `[username]` bằng tên GitHub của bạn)

## Sử dụng offline

Tải file `cham-trac-nghiem.html` về máy → mở bằng Chrome/Edge.
Lần đầu cần internet để tải module OCR tiếng Việt (~6MB), sau đó dùng offline được.

## Cấu trúc repo

```
cham-trac-nghiem.html    ← App chính
index.html               ← Redirect (cho GitHub Pages)
README.md                ← File này
```

## Quy trình dùng

1. Tab **01 Cài đặt**: đặt số câu, thang điểm
2. Tab **02 Danh sách lớp**: upload file Excel/CSV
3. Tab **03 Đáp án**: tick A/B/C/D từng câu hoặc upload ảnh đáp án
4. Tab **04 Chấm bài**: upload nhiều ảnh phiếu cùng lúc
5. Tab **05 Kết quả**: tải file điểm về

## Lưu ý

- Phiếu cần chụp/scan thẳng, đủ sáng
- SV nên viết tên bằng **mực xanh** (filter blue ink sẽ chính xác nhất)
- Dữ liệu chỉ lưu trên trình duyệt, không gửi đi đâu

## License

Mã nguồn mở cho mục đích giáo dục.
