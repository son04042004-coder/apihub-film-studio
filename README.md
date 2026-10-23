# ApiHub247 Film Studio

Nơi phát hành bộ cài và bản cập nhật của **ApiHub247 Film Studio**.

- Tải bộ cài mới nhất ở mục **Releases**: tệp `Setup-<phiên bản>.exe`.
- `latest.json`: thông tin bản mới nhất, có chữ ký số; app tự kiểm tra và tải bản cập nhật.
- `licenses/`: key bản quyền đã cấp, mỗi tệp ứng với mã băm của một máy (không có thông tin cá nhân).

Repo này không chứa mã nguồn.

## Hướng dẫn cài đặt cho người mua

1. Tải tệp `Setup-<phiên bản>.exe` ở mục **Releases** (bản mới nhất), rồi bấm đúp để chạy.
2. Nếu Windows SmartScreen báo "Windows đã bảo vệ máy tính của bạn": bấm **More info / Thông tin thêm**, rồi
   **Run anyway / Vẫn chạy**.
3. Lần đầu cài và mở app, Windows Defender có thể quét khoảng một phút: cứ chờ, đừng tắt.
4. Máy cần có **Google Chrome** (dùng để đăng nhập tài khoản Google Flow).
5. Mở ApiHub247 Film Studio, vào mục **Bản quyền**: **Mã máy** của bạn hiện ở đó (gửi mã này khi cần hỗ trợ).
6. Chọn gói, rồi mở app ngân hàng quét **mã QR** để chuyển khoản; giữ nguyên số tiền và nội dung chuyển khoản.
7. Cứ để app mở: bản quyền thường tự kích hoạt sau **1–2 phút** kể từ khi chuyển khoản.
8. Cần hỗ trợ: **Zalo 0914998354**.

## Lưu ý cho người quản trị

- **Không xoá các bản phát hành (Releases) cũ.** Khi phần runtime không đổi, `latest.json` của bản mới vẫn trỏ tới tệp
  `runtime-<rv>.zip` nằm trong một release cũ; xoá release đó thì máy khách không cập nhật được.
- Bản cài chạy ở `http://127.0.0.1:8131` (bản chạy từ mã nguồn dùng 8101, nên hai bản chạy chung một máy được). Đặt
  `FILMSTUDIO_PORT` để đổi cổng thì MCP `film-studio` cũng cần cùng biến đó (hoặc `FILM_STUDIO_URL`).
- Bản cài chạy bằng `runtime\<rv>\python\pythonw.exe`; `python.exe` cạnh nó chỉ dành cho gflow-cli (thư viện khác
  phiên bản). Muốn đăng ký MCP `film-studio` với bản cài thì dùng pythonw.exe:
  lệnh `<thư mục cài>\runtime\<rv>\python\pythonw.exe`, tham số `-m agent.studio.mcp_server`,
  biến môi trường `PYTHONPATH=<thư mục cài>\app\<phiên bản>`.
