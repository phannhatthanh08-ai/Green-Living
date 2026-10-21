# Green Living · 3-Bin Tug of War Clash (Đã nâng cấp Real-time Đa Thiết Bị)

Trò chơi tương tác thi phân loại rác 3 ngăn kết hợp kéo co đồng đội (Green Living 3-Bin Flow).

## ✨ Cải tiến quan trọng: Đồng bộ thời gian thực đa thiết bị (Cross-Device Cloud Sync)
- **Đã khắc phục lỗi không đồng bộ giữa các máy khác nhau**: Trước đây game sử dụng `BroadcastChannel` và `localStorage` (chỉ chạy nội bộ giữa các tab trên cùng 1 máy tính).
- **Hệ thống Real-time mới**: Tích hợp tầng truyền tin **MQTT WebSocket Cloud Broker** (EMQX & HiveMQ) hoàn toàn miễn phí, không cần tài khoản hay cấu hình phức tạp:
  - Máy chủ (Laptop/Máy chiếu của trọng tài) và Điện thoại/iPad của người chơi quét QR code sẽ kết nối trực tiếp với nhau qua kênh phòng riêng theo mã PIN (ví dụ: `ECO-2878`).
  - Khi người chơi trên điện thoại chọn tên, avatar, đội và bấm **READY**, màn hình máy chủ sẽ lập tức hiển thị avatar và tăng số lượng người sẵn sàng trong tích tắc!
  - Khi máy chủ bấm **START MATCH**, toàn bộ điện thoại của người chơi sẽ đồng loạt bắt đầu vào trận kéo co.
  - Mỗi khi học sinh phân loại rác đúng/sai, dây kéo co và điểm số trên máy chiếu chuyển động trực tiếp theo thời gian thực.
  - Vẫn giữ nguyên cơ chế fallback `BroadcastChannel` cục bộ cho trường hợp test nhiều tab trên cùng 1 máy.

---

## Cấu trúc thư mục

- `index.html`: File trang web chính đã nâng cấp Cloud Real-time.
- `gemini-code-1792596339577.html`: File HTML tương đương (đã tích hợp fix đồng bộ).
- `vercel.json`: Tệp cấu hình điều hướng (routing), clean URLs và các header bảo mật cho Vercel.
- `package.json`: Tệp định danh dự án.
- `.gitignore`: Loại bỏ các file tạm của Vercel khi đẩy lên Git.

---

## Cách đưa lên Vercel để tạo Website chơi nhiều máy

1. **Bước 1**: Đăng nhập [GitHub](https://github.com/) và tạo một Repository mới (ví dụ đặt tên: `green-living-clash`).
2. **Bước 2**: Tải/kéo thả các file trong thư mục này lên repository GitHub đó và bấm **Commit changes**.
3. **Bước 3**: Truy cập [Vercel](https://vercel.com/) > chọn **Add New...** > **Project** > Bấm **Import** repository bạn vừa tạo.
4. **Bước 4**: Bấm nút **Deploy** (giữ nguyên tất cả cấu hình mặc định).
5. Sau khi Vercel cấp đường link web (ví dụ `https://green-living-clash.vercel.app`):
   - **Trên máy chủ (Laptop/máy chiếu)**: Bấm 3 lần vào biểu tượng chiếc lá ở góc trên bên trái, nhập mật khẩu quản trò `ADMIN888` để mở phòng chiếu (Lobby).
   - **Trên điện thoại/thiết bị người chơi**: Dùng camera quét mã QR hiển thị trên màn hình máy chủ, chọn tên, đội và bấm **I AM READY**.
   - Màn hình máy chủ sẽ lập tức cập nhật danh sách người tham gia!
