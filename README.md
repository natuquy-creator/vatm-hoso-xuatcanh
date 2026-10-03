# VATM Hồ sơ — ứng dụng Android & iOS

Mã nguồn web giữ nguyên (`www/index.html`). Có 2 cách dùng, **cách 1 nhanh nhất và chạy được cho cả Android lẫn iPhone**.

## Cách 1 — Cài như ứng dụng (PWA), không cần APK
1. Đưa thư mục `www/` lên một địa chỉ **HTTPS** (Firebase Hosting, GitHub Pages, Netlify, máy chủ của đơn vị…).
2. **Android (Chrome):** mở địa chỉ → menu ⋮ → *Cài đặt ứng dụng* / *Thêm vào màn hình chính*.
3. **iPhone (Safari):** mở địa chỉ → nút Chia sẻ → *Thêm vào MH chính*.

## Cách 2 — File APK (Android)
### Tự động trên GitHub (không cần cài gì)
1. Tạo kho GitHub, đẩy toàn bộ thư mục này lên nhánh `main`.
2. Vào tab **Actions → Build VATM apps → Run workflow**.
3. Khi xong, tải **VATM-HoSo-android-apk** → giải nén được `app-debug.apk`.
4. Chép vào điện thoại Android, cho phép *Cài đặt từ nguồn không xác định*, mở file để cài.

### Hoặc dựng trên máy tính (cần Node 20, JDK 17, Android Studio)
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
# APK: android/app/build/outputs/apk/debug/app-debug.apk
```
Phát hành lên Google Play cần ký bằng keystore riêng và dựng bản `bundleRelease`.

## iOS (file .ipa)
Apple **không có file APK**; ứng dụng iOS chỉ dựng được trên máy Mac có Xcode:
```
npm install
npx cap add ios
npx cap sync ios
npx cap open ios   # chọn Team (Apple ID) → Run lên iPhone, hoặc Product → Archive
```
Cài lên iPhone thật cần tài khoản Apple Developer (99 USD/năm) để phân phối qua TestFlight/App Store, hoặc Apple ID miễn phí (hết hạn sau 7 ngày). Nếu không có, dùng Cách 1.

## Lưu ý
- Ứng dụng tải Tailwind, Font Awesome, Firebase từ Internet nên cần có mạng khi mở.
- Biểu tượng gốc: `icon-source-1024.png`.
