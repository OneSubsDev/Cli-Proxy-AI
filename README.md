# Cli-Proxy-AI

Hướng dẫn cài và sử dụng proxy AI, viết từ đầu nên ai cũng theo được.
Trang tĩnh, không phụ thuộc thư viện ngoài, không cần build.

**Xem trực tiếp:** https://onesubsdev.github.io/Cli-Proxy-AI/

```
huong-dan-proxy/
├── index.html          # toàn bộ nội dung + CSS inline
└── images/             # 7 ảnh WebP, tổng ~380 KB
```

## Xem thử tại máy

Mở thẳng `index.html` bằng trình duyệt là được. Hoặc:

```bash
python3 -m http.server 8080
# rồi mở http://localhost:8080
```

## Đưa lên GitHub Pages

```bash
git init
git add .
git commit -m "Hướng dẫn cài proxy AI"
git branch -M main
git remote add origin git@github.com:<tài-khoản>/<tên-repo>.git
git push -u origin main
```

Sau đó vào **Settings → Pages** của repo, mục *Source* chọn `Deploy from a branch`,
branch `main`, thư mục `/ (root)`. Đợi khoảng một phút là có link dạng
`https://<tài-khoản>.github.io/<tên-repo>/` để gửi cho người khác.

## Ghi chú về ảnh

Ảnh gốc PNG ~2400px được hạ xuống 1600px và nén WebP chất lượng 88 — từ 4,9 MB còn
380 KB, chữ vẫn sắc.

Hai chỗ đã được làm mờ có chủ đích, **đừng thay bằng ảnh gốc**:

| Ảnh | Chỗ làm mờ | Lý do |
|---|---|---|
| `oauth-sign-in.webp` | Khối link uỷ quyền trong ô Claude OAuth | Chứa `code_challenge` và `state` của phiên đăng nhập |
| `quota-lookup.webp` | Tên file credential | Chứa địa chỉ email của tài khoản |

Muốn tạo lại ảnh từ bản gốc thì dùng lệnh trong `scripts/build-images.py` (nếu có),
hoặc lặp lại: hạ về 1600px, WebP quality 88, rồi làm mờ Gaussian bán kính 20 ở hai vùng trên.

## Sửa nội dung

Toàn bộ nằm trong `index.html`. Bảng màu và phông khai báo bằng biến CSS ở đầu file;
trang tự đổi theo nền sáng/tối của máy người xem.
