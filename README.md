# Karaoke Online

Frontend (index.html) chạy trên Vercel, backend (apps-script/Code.gs) chạy trên Google Apps Script, Google Sheets làm database.

## Bước 1: Backend (Apps Script)
1. Tạo Google Sheet mới, vào Extensions > Apps Script.
2. Xóa code mặc định, dán toàn bộ `apps-script/Code.gs`.
3. Chọn hàm `setup`, bấm Run, cấp quyền (tạo 4 sheet và 5 phòng).
4. Deploy > New deployment > Web app: Execute as = Me, Who has access = Anyone > Deploy.
5. Copy URL dạng `https://script.google.com/macros/s/.../exec`.
6. Mở URL đó trên trình duyệt, thấy `Karaoke API đang chạy` là đúng.
Mỗi lần sửa Code.gs: Deploy > Manage deployments > Edit > Version: New version > Deploy (URL giữ nguyên).

## Bước 2: Gắn URL vào frontend
Mở `index.html`, thay `DÁN_URL_WEB_APP_VÀO_ĐÂY` bằng URL ở bước 1.

## Bước 3: Đưa lên GitHub
Tạo repo mới trên github.com, rồi:
```
git init
git add index.html README.md apps-script
git commit -m "Karaoke Online"
git branch -M main
git remote add origin https://github.com/TEN_BAN/karaoke-online.git
git push -u origin main
```
Hoặc dùng nút "uploading an existing file" trên trang repo rồi kéo thả các file.

## Bước 4: Chạy trên Vercel
1. Vào vercel.com, đăng nhập bằng GitHub.
2. Add New > Project > chọn repo `karaoke-online` > Import.
3. Framework Preset: Other, không cần Build Command. Bấm Deploy.
4. Nhận link `https://ten-du-an.vercel.app`.
