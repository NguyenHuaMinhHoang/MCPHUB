MCPHub: Trung Tâm Thống Nhất cho Các Máy Chủ Giao thức Ngữ cảnh Mô hình (MCP)
Tiếng Việt | English | Français | 中文版

MCPHub giúp quản lý và mở rộng nhiều máy chủ MCP (Model Context Protocol) một cách dễ dàng bằng cách tổ chức chúng thành các điểm cuối HTTP Streamable (SSE) linh hoạt—hỗ trợ truy cập vào tất cả máy chủ, máy chủ riêng lẻ, hoặc nhóm máy chủ logic.

https://assets/dashboard.png

🌐 Demo Trực tuyến & Tài liệu
Tài liệu: docs.mcphubx.com

Môi trường Demo: demo.mcphubx.com

🚀 Tính năng
Quản lý Tập trung - Giám sát và điều khiển tất cả máy chủ MCP từ một bảng điều khiển thống nhất

Định tuyến Linh hoạt - Truy cập tất cả máy chủ, nhóm cụ thể, hoặc máy chủ riêng lẻ qua HTTP/SSE

Định tuyến Thông minh - Khám phá công cụ bằng tìm kiếm ngữ nghĩa vector hỗ trợ AI (Tìm hiểu thêm)

Cấu hình Thay nóng - Thêm, xóa hoặc cập nhật máy chủ mà không cần ngừng hoạt động

Hỗ trợ OAuth 2.0 - Cả hai chế độ client và server để xác thực bảo mật (Tìm hiểu thêm)

Chế độ Cơ sở dữ liệu - Lưu trữ cấu hình trong PostgreSQL cho môi trường sản xuất (Tìm hiểu thêm)

Sẵn sàng Docker - Triển khai ngay lập tức với thiết lập container hóa

🔧 Bắt đầu Nhanh
Cấu hình
Tạo file mcp_settings.json:

json
{
  "mcpServers": {
    "time": {
      "command": "npx",
      "args": ["-y", "time-mcp"]
    },
    "fetch": {
      "command": "uvx",
      "args": ["mcp-server-fetch"]
    }
  }
}
📖 Xem Hướng dẫn Cấu hình để biết tất cả tùy chọn bao gồm OAuth, biến môi trường, và nhiều hơn nữa.

Triển khai với Docker
bash
# Chạy với cấu hình tùy chỉnh (đề xuất)
docker run -p 3000:3000 -v ./mcp_settings.json:/app/mcp_settings.json -v ./data:/app/data samanhappy/mcphub

# Hoặc chạy với cài đặt mặc định
docker run -p 3000:3000 samanhappy/mcphub
Truy cập Bảng điều khiển
Mở http://localhost:3000 và đăng nhập với thông tin đăng nhập mặc định: admin / admin123

Kết nối AI Clients
Kết nối AI clients (Claude Desktop, Cursor, v.v.) qua:

text
http://localhost:3000/mcp           # Tất cả máy chủ
http://localhost:3000/mcp/{group}   # Nhóm cụ thể
http://localhost:3000/mcp/{server}  # Máy chủ cụ thể
http://localhost:3000/mcp/$smart    # Định tuyến thông minh
📖 Xem Tham khảo API để biết tài liệu chi tiết về các điểm cuối.

📚 Tài liệu
Chủ đề	Mô tả
Bắt đầu Nhanh	Bắt đầu trong 5 phút
Cấu hình	Tùy chọn cấu hình máy chủ MCP
Chế độ Cơ sở dữ liệu	Thiết lập PostgreSQL cho sản xuất
OAuth	Thiết lập OAuth 2.0 client và server
Định tuyến Thông minh	Khám phá công cụ hỗ trợ AI
Thiết lập Docker	Hướng dẫn triển khai Docker
🧑‍💻 Phát triển Cục bộ
bash
git clone https://github.com/samanhappy/mcphub.git
cd mcphub
pnpm install
pnpm dev
Cho người dùng Windows, khởi động backend và frontend riêng biệt: pnpm backend:dev, pnpm frontend:dev

📖 Xem Hướng dẫn Phát triển để biết hướng dẫn thiết lập chi tiết.

🔍 Công nghệ Sử dụng
Backend: Node.js, Express, TypeScript

Frontend: React, Vite, Tailwind CSS

Xác thực: JWT & bcrypt

Giao thức: Model Context Protocol SDK

👥 Đóng góp
Đóng góp được chào đón! Xem Cộng đồng Discord của chúng tôi để thảo luận và hỗ trợ.

❤️ Tài trợ
https://ko-fi.com/img/githubbutton_sm.svg

🌟 Lịch sử Sao
https://api.star-history.com/svg?repos=samanhappy/mcphub&type=Date

📄 Giấy phép
Được cấp phép theo Giấy phép Apache 2.0.