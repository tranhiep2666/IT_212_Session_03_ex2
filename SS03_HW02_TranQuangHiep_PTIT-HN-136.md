Để tối ưu cho Antigravity sinh ra Functional Requirements có độ chi tiết cao, giảm thiếu sót nghiệp vụ và ép AI xử lý Edge Cases, prompt nên được thiết kế theo cấu trúc 5 thành phần: Vai trò → Mục tiêu → Ngữ cảnh → Ràng buộc → Định dạng như sau:

# VAI TRÒ (Role)

Bạn là Senior Business Analyst (BA) và Solution Architect với hơn 15 năm kinh nghiệm trong việc xây dựng tài liệu Software Requirements Specification (SRS) và Functional Requirements (FRD) cho các hệ thống thương mại điện tử quy mô lớn. Bạn có trách nhiệm đặc tả đầy đủ luồng nghiệp vụ, quy tắc xử lý dữ liệu, điều kiện kiểm tra, phân quyền và các tình huống ngoại lệ (Edge Cases).

# MỤC TIÊU (Objective)

Hãy xây dựng tài liệu Functional Requirements cho chức năng Đăng nhập (Login) thuộc module Authentication của hệ thống Shop AI.

Mục tiêu là tạo ra tài liệu đủ chi tiết để:

* Business Analyst xác nhận nghiệp vụ.
* Developer triển khai mà không cần suy diễn thêm.
* QA/QC viết Test Case và Test Scenario đầy đủ.
* Security Team đánh giá các rủi ro xác thực và phân quyền.

# NGỮ CẢNH (Context)

Thông tin hệ thống:

* Dự án: Shop AI.
* Module: Authentication.
* Cơ chế xác thực: JWT (JSON Web Token).
* Cơ chế phân quyền: RBAC (Role-Based Access Control).
* Người dùng đăng nhập bằng Email và Password.
* Sau khi xác thực thành công, hệ thống cấp JWT Access Token và Refresh Token.
* Người dùng chỉ được truy cập các chức năng tương ứng với Role được gán.
* Hệ thống lưu trạng thái tài khoản gồm:

    * Active
    * Inactive (Locked/Disabled)

# RÀNG BUỘC (Constraints)

Bắt buộc mô tả chi tiết:

1. Luồng nghiệp vụ chính (Main Flow)

    * Điều kiện tiên quyết.
    * Các bước xử lý.
    * Dữ liệu đầu vào.
    * Kiểm tra hợp lệ dữ liệu.
    * Kết quả đầu ra.
    * Điều kiện thành công.

2. Business Rules

    * Quy tắc xác thực Email và Password.
    * Quy tắc sinh JWT.
    * Quy tắc Refresh Token.
    * Quy tắc RBAC sau khi đăng nhập.

3. Security Requirements

    * Không tiết lộ thông tin nhạy cảm.
    * Ghi log đăng nhập.
    * Chính sách timeout.
    * Chính sách khóa tài khoản.

4. Edge Cases (BẮT BUỘC PHÂN TÍCH CHI TIẾT)

### Edge Case 1:

Người dùng nhập sai mật khẩu quá 5 lần liên tiếp.

Yêu cầu mô tả:

* Điều kiện kích hoạt.
* Cách hệ thống đếm số lần thất bại.
* Thời gian khóa tài khoản.
* Thông báo trả về.
* Cách mở khóa.
* Dữ liệu cần ghi log.
* Ảnh hưởng tới JWT và Session.

### Edge Case 2:

JWT Access Token hết hạn trong khi phiên làm việc đang diễn ra.

Yêu cầu mô tả:

* Hệ thống phát hiện token hết hạn như thế nào.
* Điều kiện sử dụng Refresh Token.
* Trường hợp Refresh Token còn hiệu lực.
* Trường hợp Refresh Token hết hạn.
* Response trả về.
* Hành vi trên giao diện người dùng.
* Các yêu cầu bảo mật liên quan.

### Edge Case 3:

Tài khoản ở trạng thái Inactive nhưng vẫn cố gắng đăng nhập.

Yêu cầu mô tả:

* Điều kiện kiểm tra trạng thái tài khoản.
* Luồng xử lý.
* Mã lỗi trả về.
* Thông báo cho người dùng.
* Dữ liệu ghi log.
* Các rủi ro bảo mật cần ngăn chặn.

5. Không được bỏ qua:

* Alternative Flows.
* Exception Flows.
* Validation Rules.
* Error Codes.
* API Responses.
* Audit Logs.
* Permission Matrix theo RBAC.

6. Nếu phát hiện bất kỳ điểm mơ hồ nào trong yêu cầu, AI phải:

* Chủ động nêu giả định.
* Đề xuất phương án xử lý.
* Giải thích lý do lựa chọn.

# ĐỊNH DẠNG ĐẦU RA (Output Format)

Xuất kết quả dưới dạng tài liệu Functional Requirements chuyên nghiệp với các mục:

1. Overview
2. Scope
3. Actors
4. Preconditions
5. Functional Requirements
6. Main Flow
7. Alternative Flows
8. Exception Flows
9. Business Rules
10. Validation Rules
11. Security Requirements
12. RBAC Permission Matrix
13. Edge Cases Analysis
14. Error Codes Table
15. API Request/Response Examples
16. Audit Log Requirements
17. Assumptions
18. Acceptance Criteria

Mỗi yêu cầu chức năng phải có:

* Requirement ID (FR-xxx)
* Description
* Priority
* Preconditions
* Trigger
* Processing Logic
* Success Result
* Failure Result
* Related Business Rules


