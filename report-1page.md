# Report 1 page - Lab 5 AES-128

## Mục tiêu

Bài thực hành giúp sinh viên hiểu quy trình mã hóa và giải mã AES-128 ở mức cơ bản, bao gồm xử lý block 128-bit, mở rộng khóa (Key Expansion), các phép biến đổi trong từng vòng AES và cơ chế padding dữ liệu.

## Cách làm / Method

Repo sử dụng các file mã nguồn chính gồm: `encrypt.cpp`, `decrypt.cpp` và `structures.h`.

- `encrypt.cpp` thực hiện mã hóa plaintext và ghi ciphertext vào file `message.aes`.
- `decrypt.cpp` đọc file `message.aes` để giải mã và khôi phục plaintext.
- `structures.h` chứa S-box, inverse S-box, bảng tra cứu MixColumns, RCon và các hàm hỗ trợ KeyExpansion.

Project được tổ chức theo cấu trúc chuẩn của FIT4012:
- `Makefile`
- `CMakeLists.txt`
- thư mục `tests/`
- thư mục `logs/`
- GitHub Actions CI

Trong quá trình hoàn thiện, chương trình được sửa để hỗ trợ đọc/ghi file nhị phân đúng cách bằng `ifstream` và `outfile.write()` thay vì xử lý ciphertext như chuỗi ký tự thông thường.

## Kết quả / Result

Chương trình có thể compile bằng Makefile hoặc CMake và chạy thành công trên môi trường Linux.

Khi mã hóa plaintext mẫu như:

```text
hello FIT4012 AES