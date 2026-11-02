# Green Living · 3-Bin Tug of War Clash (Đã nâng cấp Real-time & Quản lý người chơi)

Trò chơi tương tác thi phân loại rác 3 ngăn kết hợp kéo co đồng đội (Green Living 3-Bin Flow).

## ✨ Cải tiến mới nhất:
1. **Tự động phát hiện và xóa người chơi khi rời phòng / mất kết nối**:
   - Khi người chơi đóng tab, đổi trang hoặc bấm nút **RỜI PHÒNG (LEAVE ROOM)**, hệ thống lập tức gửi sự kiện `PLAYER_LEAVE` để xóa ngay tên người chơi khỏi màn hình máy chủ trong tích tắc.
   - Cơ chế **Heartbeat (Nhịp tim)**: Máy chủ tự động kiểm tra định kỳ mỗi 3 giây. Nếu điện thoại học sinh tắt nguồn, mất sóng 4G/Wi-Fi hoặc bị tắt ứng dụng ngầm quá 10 giây không có tín hiệu, máy chủ sẽ tự động xóa người chơi đó để đảm bảo kiểm soát chính xác số lượng thực tế.
2. **Tính năng Quản trò Xóa Người Chơi (Admin Kick Player)**:
   - Trên màn hình máy chủ phòng chờ (Lobby) và bảng điểm trực tiếp (Stage), cạnh mỗi thẻ người chơi đều có nút đỏ **✕ (Xóa)**.
   - Quản trò chỉ cần nhấn nút **✕** và xác nhận để đưa người chơi không hợp lệ hoặc spam ra khỏi phòng.
   - Trên thiết bị của người chơi bị xóa, màn hình sẽ thông báo *"Bạn đã bị quản trò đưa ra khỏi phòng chơi!"* và tự động quay về trang nhập mã PIN.
3. **Đồng bộ thời gian thực đám mây (Cloud WebSocket MQTT)**:
   - Kết nối trực tiếp giữa máy chiếu và tất cả điện thoại/máy tính bảng của học sinh thông qua mã PIN phòng riêng biệt.

---

## Cấu trúc thư mục

- `index.html`: File trang web chính đã nâng cấp đầy đủ tính năng.
- `gemini-code-1792596339577.html`: File HTML tương đương có đầy đủ tính năng.
- `vercel.json`: Tệp cấu hình điều hướng (routing), clean URLs và các header bảo mật cho Vercel.
- `package.json`: Tệp định danh dự án.
- `.gitignore`: Loại bỏ các file tạm của Vercel khi đẩy lên Git.

---

## Cách đưa lên Vercel để tạo Website

1. **Bước 1**: Đăng nhập [GitHub](https://github.com/) và tạo Repository mới (ví dụ: `green-living-clash`).
2. **Bước 2**: Tải/kéo thả toàn bộ các file trong thư mục này lên GitHub và bấm **Commit changes**.
3. **Bước 3**: Mở [Vercel](https://vercel.com/) > chọn **Add New...** > **Project** > Bấm **Import** repository bạn vừa tạo.
4. **Bước 4**: Bấm nút **Deploy** (giữ nguyên tất cả cấu hình mặc định).
