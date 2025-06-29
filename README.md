# 🐧 ubuntu-install-wsl

> Cài đặt Ubuntu 20.04 LTS trên Windows (WSL) và thiết lập môi trường Python + Git để phát triển

## 🔧 Yêu cầu trước khi cài đặt

- Windows 10/11 đã bật **WSL (Windows Subsystem for Linux)**  
  Hướng dẫn bật WSL: [Xem tại đây](https://learn.microsoft.com/en-us/windows/wsl/install)

---

## 1️⃣ Cài đặt Ubuntu 20.04 từ Microsoft Store

1. Mở **Microsoft Store**
2. Tìm kiếm **Ubuntu 20.04 LTS**
3. Click `Install`
4. Sau khi cài xong, mở Ubuntu lần đầu → hệ thống sẽ yêu cầu tạo username và password

---

## 2️⃣ Cập nhật hệ thống và cài Python

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install python3 python3-pip python3-venv -y
```

---

## 3️⃣ Tạo môi trường ảo Python

```bash
python3 -m venv venv
source venv/bin/activate
```

> ✅ Lúc này bạn đã vào môi trường `venv` (dấu `(venv)` sẽ hiển thị ở đầu dòng terminal)

---

## 4️⃣ Cài đặt Git và cấu hình SSH

### 🔹 Cài Git

```bash
sudo apt install git -y
```

### 🔹 Thiết lập tên và email Git (dùng để commit)

```bash
git config --global user.name "Tên của bạn"
git config --global user.email "email@example.com"
```

### 🔹 Tạo SSH key để kết nối GitHub

```bash
ssh-keygen -t ed25519 -C "email@example.com"
```

Ấn Enter liên tục để sử dụng cấu hình mặc định. Sau đó chạy:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy kết quả và thêm vào GitHub tại:  
**GitHub → Settings → SSH and GPG keys → New SSH key**

---

## 5️⃣ Cài đặt VS Code (tuỳ chọn nhưng khuyến nghị)

> Bạn nên cài [Visual Studio Code](https://code.visualstudio.com/) bản Windows. Sau khi mở VS Code, cài extension `Remote - WSL` để làm việc trực tiếp với Ubuntu.

---

## 🎉 Hoàn tất!

Giờ bạn đã có một môi trường Ubuntu + Python + Git đầy đủ để phát triển các project cá nhân 🎯

---

## 📁 Thư mục này để làm gì?

Bạn có thể dùng repo này làm nơi chứa các script khởi tạo, hướng dẫn hoặc cấu hình mở rộng (như Docker, NodeJS, DBT...) trong quá trình học và làm việc với Ubuntu trên WSL.
