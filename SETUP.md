# Cấu hình GitHub profile

Bản này dành cho repository `vanphuoc0443/vanphuoc0443`, nhánh `main`.

## Năm repo được dùng thế nào?

| Repo | Vai trò trong profile |
| --- | --- |
| [awesome-github-profile-readme-templates](https://github.com/durgeshsamariya/awesome-github-profile-readme-templates) | Tham khảo bố cục giới thiệu, công nghệ và dự án. Không sao chép thông tin cá nhân từ mẫu. |
| [github-profile-readme-generator](https://github.com/rahuldkjain/github-profile-readme-generator) | Tham khảo các mục tên, tagline, kỹ năng và liên kết. Có bộ thông tin bên dưới để nhập vào giao diện nếu cần tạo lại. Chưa chạy generator; README hiện tại đã được biên tập riêng. |
| [skill-icons](https://github.com/tandpfun/skill-icons) | Hiển thị hai nhóm icon cho web và Android/Java, đổi nền theo chế độ sáng/tối của GitHub. |
| [readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg) | Hiển thị ba câu giới thiệu luân phiên, màu xanh `38BDF8`. |
| [snk](https://github.com/Platane/snk) | Workflow tạo snake từ contribution của `vanphuoc0443`, xuất SVG sáng và tối. |

Hai repo đầu là tài liệu và công cụ soạn README, không phải dịch vụ cần chạy cùng profile. Không cần clone hoặc cài dependency của chúng.

Phần nội dung được biên tập theo [humanizer của blader](https://github.com/blader/humanizer/blob/main/SKILL.md): giữ thông tin có căn cứ, dùng câu trực tiếp, bỏ lời quảng cáo và câu kết lặp ý. Skill được đọc từ nguồn công khai, chưa cài vào máy.

## Các file cần đưa vào repo

```text
README.md
assets/header.svg
assets/project-quiz.svg
assets/project-traceweaver.svg
.github/workflows/snake.yml
```

`SETUP.md` là hướng dẫn, có thể giữ lại trong repo. Khi đưa các file lên GitHub, giữ nguyên thư mục `.github` và `assets`.

README, icon và chữ động hoạt động sau khi các file được đưa lên nhánh dùng cho profile. Icon và chữ động phụ thuộc dịch vụ bên ngoài; phần giới thiệu và dự án vẫn đọc được nếu các dịch vụ đó tạm ngừng.

## Tạo snake lần đầu

Workflow chỉ chạy khi bạn bấm chạy thủ công. Không có lịch cron hoặc trigger khi push.

1. Workflow cần có trên nhánh mặc định `main` để GitHub hiển thị nút chạy thủ công.
2. Vào **Actions → Generate contribution snake → Run workflow**.
3. Chọn đúng nhánh bạn muốn cập nhật. Lần chạy này sẽ tạo commit và push vào chính nhánh được chọn, gồm hai SVG và phần Contributions trong README. Không tạo nhánh `output`.
4. Sau khi workflow thành công, tải lại profile. Snake xuất hiện ở mục Contributions. Trước lần chạy đầu, mục này chỉ có liên kết xem lịch sử đóng góp nên không có ảnh hỏng.

Workflow dùng `GITHUB_TOKEN` có sẵn của GitHub Actions với quyền `contents: write` trong job tạo ảnh. Không cần tạo PAT hoặc thêm secret riêng. Nếu chính sách repository hoặc branch protection chặn commit của Actions, workflow sẽ thất bại ở bước lưu ảnh; cần xem thông báo lỗi trước khi quyết định thay đổi chính sách. Không có force push.

Muốn cập nhật snake, chạy lại workflow. Lần chạy tạo ảnh mới dựa trên contribution tại thời điểm đó.

## Nội dung cho README Generator

Mở [README Generator](https://rahuldkjain.github.io/github-profile-readme-generator/) nếu muốn tạo lại bản nháp bằng giao diện:

| Mục | Nội dung |
| --- | --- |
| Name | Nguyễn Văn Phước |
| Tagline | Backend development with Node.js and Express. Android with Kotlin. |
| GitHub username | vanphuoc0443 |
| Skills | JavaScript, Node.js, Express, MongoDB, Kotlin, Android, Java, JavaFX, MySQL, HTML, CSS |
| Project links | Các liên kết ở phần Selected projects trong README |
| Email, LinkedIn, blog, vị trí | Để trống cho đến khi bạn muốn công khai thông tin này |

Generator không tự nhập được hướng dẫn này. Khi tạo lại README, giữ cặp marker `SNAKE:START` / `SNAKE:END` để workflow cập nhật đúng phần snake.

## Chỉnh màu và câu giới thiệu

- Chữ động: sửa `lines`, `color`, `duration`, `pause` trong URL `readme-typing-svg` ở README. Dùng dấu `;` để ngăn các câu.
- Icon: sửa danh sách `i=` trong cả hai URL của `skill-icons`. Hai URL dùng cùng danh sách, khác `theme=light` và `theme=dark`.
- Snake: sửa `color_snake` trong workflow, rồi chạy lại. `%23` là ký tự `#` đã mã hóa trong URL.
- Banner: chỉnh `assets/header.svg`.
- Thẻ dự án: chỉnh các file `assets/project-*.svg`. Các file này là thẻ giới thiệu, không phải ảnh chụp giao diện ứng dụng.

## Tham khảo bố cục

- [KhuongSpring](https://github.com/KhuongSpring): giới thiệu ngắn và nhóm icon công nghệ.
- [antfu](https://github.com/antfu): điều hướng gọn, dễ mở các phần liên quan.
- [DenverCoder1](https://github.com/DenverCoder1): đặt dự án nổi bật thành nhóm trực quan.

Nội dung, thông tin cá nhân và thẻ dự án được viết riêng cho `vanphuoc0443`. Không dùng tài khoản xã hội, chức danh hoặc thành tích từ các profile tham khảo. Không thêm thẻ stats vì các endpoint đã kiểm tra trả về lỗi hoặc hết thời gian chờ.
