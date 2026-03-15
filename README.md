# Server Key Admin - Phiên bản Việt Nam

Hệ thống quản lý key và thiết bị cực đẹp với giao diện hiện đại, tương tự Web-Server-Key

## Tính năng

- 🔑 **Normal Key**: Key ngẫu nhiên (SP-XXXX-XXXX-XXXX), dùng 1 lần rồi hết
- 👑 **Custom Key**: Tên tự đặt, tái sử dụng được
- 🌐 **Global Key**: Nhiều thiết bị dùng chung 1 key
- 📱 Quản lý thiết bị đang sử dụng
- ⚙️ Cấu hình hệ thống đầy đủ
- 🔧 Chế độ bảo trì
- 🎨 Giao diện cực đẹp, hiện đại với animation

## Cách cấu hình Firebase

### Bước 1: Tạo Firebase Project

1. Truy cập [Firebase Console](https://console.firebase.google.com/)
2. Tạo project mới hoặc chọn project có sẵn
3. Vào **Build** > **Realtime Database** > **Create Database**
4. Chọn location **asia-southeast1** (Singapore)
5. Chọn **Start in test mode** (cho phép đọc/ghi)

### Bước 2: Lấy Firebase Config

1. Vào **Project Settings** (biểu tượng ⚙️)
2. Kéo xuống **Your apps** > Chọn **</>** (web)
3. Đặt tên app và đăng ký
4. Copy firebaseConfig được hiển thị

### Bước 3: Cấu hình trong index.html

Mở file `index.html` và tìm phần **FIREBASE CONFIGURATION**:

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT-default-rtdb.asia-southeast1.firebasedatabase.app",
    projectId: "YOUR_PROJECT",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

Thay thế bằng thông tin Firebase của bạn.

## Cách Deploy lên GitHub Pages

### Bước 1: Tạo GitHub Repository

1. Truy cập [GitHub](https://github.com/)
2. Tạo repository mới (public)
3. Đặt tên repository, ví dụ: `server-key-admin`

### Bước 2: Upload code lên GitHub

Cách 1: Sử dụng Git Commands
```bash
# Clone repository
git clone https://github.com/YOUR_USERNAME/server-key-admin.git
cd server-key-admin

# Copy các file cần thiết
# (Đảm bảo đã cấu hình Firebase trong index.html)

# Commit và push
git add .
git commit -m "Initial commit"
git push origin main
```

Cách 2: Upload trực tiếp
1. Vào repository trên GitHub
2. Chọn **uploading an existing file**
3. Kéo thả các file: `index.html`, `package.json`, `README.md`
4. Commit changes

### Bước 3: Kích hoạt GitHub Pages

1. Vào **Settings** của repository
2. Chọn **Pages** ở menu bên trái
3. Under **Source**, chọn **Deploy from a branch**
4. Branch: **main** (hoặc master)
5. Folder: **/(root)**
6. Nhấn **Save**
7. Đợi vài phút, bạn sẽ có link: `https://YOUR_USERNAME.github.io/server-key-admin/`

## Cách sử dụng

### Truy cập Admin Panel

1. Mở link GitHub Pages của bạn
2. Click **"Tạo Key Mới"**
3. Chọn loại key:
   - **Normal Key**: Tự động tạo key ngẫu nhiên, dùng 1 lần
   - **Custom Key**: Nhập tên key tùy chọn, tái sử dụng
   - **Global Key**: Nhập tên key, giới hạn số thiết bị
4. Nhập thời hạn (giờ)
5. Click **"Tạo Key"**

### Tính năng quản lý

- **Xem danh sách keys**: Lọc theo loại, xem trạng thái
- **Sửa key**: Thay đổi thời hạn, giới hạn thiết bị
- **Xóa key**: Xóa key không cần thiết
- **Xem thiết bị**: Xem các thiết đang sử dụng key
- **Cấu hình**: Thay đổi tiêu đề, tin nhắn bảo trì,...

## Cấu trúc Project

```
server-key-admin/
├── index.html          # Frontend chính (đã bao gồm Firebase SDK)
├── package.json        # Dependencies (cho local dev)
├── server.js          # Backend server (tùy chọn)
├── firebase-config.js  # Firebase config (backend)
├── README.md          # File này
└── DEPLOY.md          # Hướng dẫn deploy chi tiết
```

## Lưu ý quan trọng

⚠️ **Bảo mật Firebase Rules**

Để bảo mật database, vào Firebase Console > Realtime Database > **Rules**:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

**Lưu ý**: Rules trên cho phép mọi người đọc/ghi. Để bảo mật hơn, bạn cần thêm authentication hoặc rules phức tạp hơn.

## Hỗ trợ

Nếu có câu hỏi hoặc cần hỗ trợ, vui lòng tạo issue trên GitHub!

---

Developed with ❤️ by Server Key Admin
