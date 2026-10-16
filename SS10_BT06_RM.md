# Báo cáo: Xử lý sự cố tài liệu dự án GreenTech trên GitHub

## Phần 1: Phân tích sự cố

Dưới đây là 2 sai lầm trong tư duy của Nam khi sử dụng file Word (`.docx` - Rich Text) để lưu trữ tài liệu trên GitHub và lý do tại sao Markdown lại là giải pháp tối ưu hơn:

**1. Sai lầm về cơ chế theo dõi phiên bản (Version Control):**
*   **Vấn đề của Nam:** File `.docx` thực chất là một tệp nhị phân (binary/archive). Git không thể đọc từng dòng text bên trong nó. Do đó, khi Nam chỉ sửa một dấu phẩy, Git sẽ thấy toàn bộ cấu trúc mã hóa nhị phân của file thay đổi và ghi nhận đây là một file hoàn toàn mới. Điều này dẫn đến việc Git báo xung đột (conflict) toàn bộ file khi làm việc nhóm (merge).
*   **Ưu điểm của Markdown:** Markdown là dạng Plain Text (Văn bản thô). Git có thể theo dõi sự thay đổi trên từng dòng (line-by-line diff). Nếu bạn sửa một dấu phẩy, Git chỉ báo thay đổi đúng ở dòng đó, giúp việc gộp code (merge) diễn ra mượt mà.

**2. Sai lầm về khả năng hiển thị trên nền tảng (Rendering):**
*   **Vấn đề của Nam:** GitHub không hỗ trợ xem trước nội dung file `.docx` trực tiếp trên trình duyệt. Các thành viên khác bắt buộc phải tải file về máy, mở bằng Microsoft Word thì mới xem được, làm giảm tốc độ làm việc.
*   **Ưu điểm của Markdown:** GitHub hỗ trợ render file Markdown (`.md`) một cách tự nhiên (Native). Tài liệu sẽ hiển thị đẹp mắt với đầy đủ tiêu đề, danh sách, hình ảnh ngay trên trình duyệt mà không cần tải về.

**3. Phân tích "Bẫy dữ liệu" (Rủi ro mất mát dữ liệu):**
*   **Với file Word (.docx):** Bản chất nó là một tệp nén chứa nhiều file XML. Nếu trong quá trình tải lên bị lỗi mạng và mất đi chỉ 1 byte, cấu trúc tệp nén sẽ bị hỏng toàn bộ (Corrupted) và bạn không thể mở file đó lên được nữa.
*   **Với file Markdown (.md):** Vì là văn bản thô, nếu mất 1 byte dữ liệu do lỗi đường truyền, bạn chỉ bị mất đúng 1 ký tự ở vị trí đó (ví dụ chữ "t" biến thành khoảng trắng hoặc ký tự lạ), toàn bộ nội dung còn lại của tài liệu vẫn hiển thị và đọc được bình thường.

---

## Phần 2: Hoàn thiện (Chuyển đổi tài liệu giới thiệu)

Dưới đây là đoạn tài liệu giới thiệu dự án đã được chuyển đổi từ Word sang định dạng Markdown tối ưu cho GitHub:

# Dự án GreenTech

**GreenTech** là dự án hướng tới việc ứng dụng công nghệ để bảo vệ môi trường, giúp cuộc sống xanh và bền vững. 

### Mục tiêu dự án
* Tự động hóa quy trình chăm sóc cây trồng.
* Nâng cao ý thức cộng đồng.
* Phát triển nền tảng quản lý rác thải thông minh.

### Công nghệ sử dụng
1. **Phần cứng:** Cảm biến IoT, Vi điều khiển ESP32.
2. **Phần mềm:** Python, C++, và nền tảng Cloud.
3. **Tài liệu:** Markdown (Hiển thị trực tiếp trên GitHub).