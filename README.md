# Vietkite Travel – Hướng dẫn deploy & quản lý ảnh

## Cấu trúc thư mục
```
vietkite-netlify/
├── index.html        ← Trang web chính
├── config.json       ← Danh sách URL ảnh (CMS sẽ cập nhật file này)
├── netlify.toml      ← Cấu hình Netlify
├── admin/
│   ├── index.html    ← Trang đăng nhập CMS
│   └── config.yml    ← Cấu hình CMS (danh sách các ảnh)
└── images/           ← Ảnh upload sẽ lưu vào đây (tự tạo)
```

---

## Bước 1: Tạo GitHub repo

1. Vào github.com → New repository
2. Đặt tên (ví dụ: `vietkite-web`)
3. Public hoặc Private đều được
4. Upload toàn bộ thư mục này lên repo

---

## Bước 2: Deploy lên Netlify

1. Vào **app.netlify.com** → "Add new site" → "Import an existing project"
2. Chọn GitHub → chọn repo `vietkite-web`
3. Build settings: để trống hết (không cần build command)
4. Nhấn **Deploy site**
5. Sau ~30 giây, site sẽ lên live tại URL dạng `xxx.netlify.app`
6. Gắn domain riêng: Site settings → Domain management

---

## Bước 3: Bật Netlify Identity (cho CMS đăng nhập)

1. Vào **Site settings → Identity**
2. Nhấn **Enable Identity**
3. Xuống **Git Gateway** → nhấn **Enable Git Gateway**
4. Vào **Identity → Invite users** → nhập email khách hàng
5. Khách hàng sẽ nhận email, đặt mật khẩu

---

## Cách khách hàng thay ảnh

1. Vào `yoursite.netlify.app/admin`
2. Đăng nhập bằng email đã được mời
3. Nhấn **"🖼️ Quản lý hình ảnh"**
4. Thấy danh sách 17 ảnh với tên tiếng Việt rõ ràng
5. Nhấn vào ảnh → Upload ảnh mới từ máy tính hoặc dán URL
6. Nhấn **Publish** → trang web tự cập nhật trong ~30 giây

---

## Lưu ý

- Mỗi lần khách nhấn Publish, Netlify tự rebuild và deploy lại trang
- Ảnh upload sẽ lưu vào thư mục `/images/` trong repo GitHub
- Nếu muốn dùng ảnh từ URL ngoài (imgur, unsplash...) cũng được, chỉ cần dán URL vào
- Logo công ty và footer KHÔNG nằm trong CMS (giữ nguyên)
