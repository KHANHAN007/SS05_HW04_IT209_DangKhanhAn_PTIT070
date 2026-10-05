# Bài 4 - Hotfix và Gitflow

## Bối cảnh

Nhánh main đang chạy phiên bản v1.0.0 nhưng có lỗi làm lộ dữ
liệu người dùng. Nhánh develop đang chứa tính năng dashboard chưa
hoàn thành nên không thể deploy trực tiếp.

## Quy trình xử lý

1. Tạo `hotfix/v1.0.1` trực tiếp từ `main`.
2. Sửa lỗi bảo mật trên nhánh hotfix.
3. Merge hotfix vào `main` bằng `--no-ff`.
4. Tạo tag `v1.0.1` trên commit mới của main.
5. Merge hotfix vào `develop` để phiên bản tương lai cũng có bản vá.

## Các lệnh chính

```bash
git switch main
git switch -c hotfix/v1.0.1

git switch main
git merge --no-ff hotfix/v1.0.1
git tag -a v1.0.1 -m "Release Hotfix 1.0.1"

git switch develop
git merge --no-ff hotfix/v1.0.1
