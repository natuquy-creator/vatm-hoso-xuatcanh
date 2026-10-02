# VATM — Hệ thống theo dõi tờ trình, giấy phép và báo cáo xuất cảnh Đảng viên

Ứng dụng **PWA** (Progressive Web App): **cùng một mã nguồn** cho **điện thoại** và **máy tính**.

## Liên kết

| Mục | URL |
|-----|-----|
| **Repository** | https://github.com/natuquy-creator/vatm-hoso-xuatcanh |
| **Ứng dụng (sau khi bật Pages)** | https://natuquy-creator.github.io/vatm-hoso-xuatcanh/ |

## Bước 1 — Đầy file ứng dụng đầy đủ (`app.html`)

1. Mở https://github.com/natuquy-creator/vatm-hoso-xuatcanh
2. Nút **Add file** → **Upload files**
3. Kéo thả file **`app.html`** (từ gói mã nguồn đã nhận) vào thư mục gốc
4. Commit: `Add full application app.html`

Hoặc clone và push:

```bash
git clone https://github.com/natuquy-creator/vatm-hoso-xuatcanh.git
cd vatm-hoso-xuatcanh
# Sao chép app.html vào thư mục này
git add app.html
git commit -m "Add full application"
git push
```

Sau đó sửa `index.html` để chuyển hướng sang `app.html` (hoặc đổi tên `app.html` thành `index.html`).

## Bước 2 — Bật GitHub Pages

1. Vào **Settings** → **Pages**
2. **Source:** Deploy from a branch
3. Branch: **main**, folder: **/ (root)**
4. Save — đợi 1–2 phút rồi mở:
   **https://natuquy-creator.github.io/vatm-hoso-xuatcanh/**

## Cài như app điện thoại

### Android (Chrome)
1. Mở link Pages trên Chrome
2. Menu **⋮** → **Thêm vào màn hình chính** / **Cài đặt ứng dụng**
3. Xác nhận — icon **VATM Hồ sơ** xuất hiện như app

### iPhone (Safari)
1. Mở link trên Safari
2. Nút **Chia sẻ** → **Thêm vào Màn hình chính**
3. Thêm — mở app toàn màn hình

### PC (Chrome / Edge)
1. Mở link Pages
2. Biểu tượng **Cài đặt** trên thanh địa chỉ (hoặc menu → Cài đặt ứng dụng)
3. Ứng dụng chạy cửa sổ riêng, cùng mã nguồn với mobile

## Tài khoản demo

| Vai trò | Đăng nhập | Mật khẩu |
|---------|-----------|----------|
| Quản trị | `admin` | `123` |
| Đảng viên | `01.0029381` | `123` |

## Cấu trúc

```
index.html / app.html   # Ứng dụng đầy đủ
manifest.json           # PWA
sw.js                   # Service Worker
icons/                  # Icon đỏ Đảng
README.md
```

## Tính năng

- Theo dõi tờ trình, giấy phép, báo cáo xuất cảnh
- Admin / Đảng viên
- Thống kê đơn vị, chi bộ
- Xuất Excel, Word, in
- Đồng bộ Firebase (nếu cấu hình)
- Giao diện responsive + tông đỏ Đảng

## Bảo mật

Đổi mật khẩu mặc định khi dùng thật; cấu hình Firebase Rules chặt; không mở public read/write database.
