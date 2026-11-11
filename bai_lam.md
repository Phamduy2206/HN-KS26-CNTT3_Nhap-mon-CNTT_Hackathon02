# BÀI LÀM – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** PHẠM NGỌC DUY
- **Lớp:** HN-KS26-CNTT3
- **Link repository:** https://github.com/Phamduy2206/HN-KS26-CNTT3_Nhap-mon-CNTT_Hackathon02.git
- **Hệ điều hành (Windows/macOS):** WINDOWS

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
PS C:\starter-kit\spa_website> pwd
PS C:\starter-kit\spa_website> ls -Force
PS C:\starter-kit\spa_website> mv .\lich_lam_viec.txt ".\docs"
PS C:\starter-kit\spa_website> mkdir backup
PS C:\starter-kit\spa_website> cp ".\data\hoa_don_spa_thang_7.xlsx" ".\backup\"
PS C:\starter-kit\spa_website> rm .\temp_707.tmp
PS C:\starter-kit\spa_website> cd .\logs
PS C:\starter-kit\spa_website\logs> Get-Content .\service.log
PS C:\starter-kit\spa_website\logs> cd ..
PS C:\starter-kit\spa_website> Get-ChildItem -Force -Recurse

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: C:\starter-kit\spa_website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:52 AM                backup
d-----        11/11/2026  10:52 AM                data
d-----        11/11/2026  10:50 AM                docs
d-----        11/11/2026  10:46 AM                evidence
d-----        11/11/2026  10:48 AM                logs
d-----        11/11/2026  10:42 AM                web
------         11/3/2026   7:07 AM             75 .env
-a----        11/11/2026  10:49 AM           2458 bai_lam.md


    Directory: C:\starter-kit\spa_website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\starter-kit\spa_website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: C:\starter-kit\spa_website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            149 lich_lam_viec.txt


    Directory: C:\starter-kit\spa_website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            939 service.log


    Directory: C:\starter-kit\spa_website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/3/2026   7:07 AM                images
------         11/3/2026   7:07 AM            597 app.js
------         11/3/2026   7:07 AM            523 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: C:\starter-kit\spa_website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3091 logo-lotuscare.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
PS C:\starter-kit\spa_website> Get-Content .\logs\service.log | Select-String "status=500" > .\logs\loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-07-28 08:12:50 POST /api/dat-lich status=500
2026-07-28 08:19:23 POST /api/dat-lich status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
PS C:\starter-kit\spa_website> (Get-Content .\logs\service.log | Select-String "status=404").Count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
PS C:\starter-kit\spa_website> .\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-07-28 08:16:12 GET /images/phong-spa-3.jpg status=404
2026-07-28 08:39:18 GET /uu-dai-cu status=404
2026-07-28 08:46:40 GET /tin-tuc status=404
2026-07-28 08:48:51 GET /tin-tuc status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | NetWork | file:///C:/starter-kit/spa_website/web/images/logo.png | mở web index.html bằng VS code , tại dòng 10 sửa src="images/logo.png" thành đúng tên tên file ảnh trong thư mục , sau đó trở lại trang web tải lại trang để hiển thị logo |
| 2 | Console | app.js:18 Uncaught ReferenceError: hienThiGoiDichVu is not defined| Sửa lại đường dẫn trong vs code |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Tôi là sinh viên năm nhất chưa fix lỗi hiển thị dữ liệu của web bao giờ
- **Expected:** Bây giờ trang web spa của tôi muốn có đủ dữ liệu ở bảng hiển thị giao diện 
- **Actual:** Dữ liệu trên trang web spa không có gì và tôi vào tab console thấy thông báo lỗi app.js:18 Uncaught ReferenceError: hienThiGoiDichVu is not defined
- **Log:** app.js:18 Uncaught ReferenceError: hienThiGoiDichVu is not defined


### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_spa_thang_7.xlsx`, không cần ghi vào đây.
