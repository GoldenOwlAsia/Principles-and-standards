### 🚀 Quy Trình GitFlow Chi Tiết

---

#### 1. Phát Triển Tính Năng & Sửa Lỗi

- **Khởi tạo công việc mới**
  - Luôn *checkout* từ nhánh `main` để bắt đầu.
  - Đặt tên nhánh theo quy tắc:
    - 🌟 `feat/xxx`: Cho tính năng mới
    - 🐛 `bugfix/xxx`: Cho việc sửa lỗi
    - 🔧 `chore/xxx`: Cho các thay đổi nhỏ (cập nhật văn bản, sửa lỗi chính tả...)
    - 🔥 `hotfix/xxx`: Sửa lỗi khẩn cấp

- **Deploy Production**
  - Tạo Merge Request (MR) vào nhánh `main`.
  - Sau khi merge thành công:
    - Tạo tag phiên bản theo chuẩn *semantic versioning* (tùy chọn).
    - Viết *release notes* chi tiết (danh sách PR, ảnh chụp màn hình, video demo).
    - Tiến hành deploy lên Production (tự động hoặc thủ công).
    - Thông báo cho các bên liên quan (QC/PC) để kiểm tra tính năng mới triển khai.

- **Deploy Staging**
  - Merge nhánh vào `develop`.
  - Push code lên `develop`.
  - Tiến hành deploy nhánh `develop` (tự động hoặc thủ công).
  - Thông báo cho các bên liên quan (QC/PC) để kiểm tra tính năng mới triển khai.

---

#### 2. Quy Tắc Đánh Semantic Versioning (tùy chọn)

- Sử dụng chuẩn: `MAJOR.MINOR.PATCH`
  - **MAJOR**: Thay đổi lớn, không tương thích với phiên bản cũ  
    *Ví dụ*: `1.2.3` -> `2.0.0`
  - **MINOR**: Thêm tính năng mới, tương thích với phiên bản cũ  
    *Ví dụ*: `1.2.3` -> `1.3.0`
  - **PATCH**: Sửa lỗi nhỏ, hotfix  
    *Ví dụ*: `1.2.3` -> `1.2.4`

---

#### 3. Lưu ý

- ❌ **Không** được push trực tiếp vào nhánh `main`.
- ❌ **Không** sử dụng `git push --force` với các nhánh chính.
- ✅ Luôn fetch và pull code mới nhất trước khi bắt đầu.
