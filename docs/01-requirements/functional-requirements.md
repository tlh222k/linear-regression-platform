# Đặc tả yêu cầu chức năng – Linear Regression Platform

**Mã tài liệu:** FRD-001  
**Phiên bản:** 1.0  
**Trạng thái:** Bản nháp thiết kế  
**Phạm vi:** Phiên bản MVP

## 1. Mục đích

Tài liệu này mô tả các yêu cầu chức năng của hệ thống Linear Regression Platform. Hệ thống cho phép người dùng thực hiện quy trình Machine Learning từ quản lý dữ liệu, khám phá dữ liệu, cấu hình mô hình, huấn luyện, đánh giá đến dự đoán.

Tài liệu được sử dụng làm cơ sở cho thiết kế kiến trúc, thiết kế cơ sở dữ liệu, API, giao diện người dùng, triển khai ML Core và kiểm thử.

## 2. Mục tiêu hệ thống

Xây dựng một nền tảng full-stack giúp người dùng hiểu và thực hiện toàn bộ quy trình Linear Regression.

Hệ thống phải hỗ trợ hai mục tiêu:

- **Mục tiêu học thuật:** Giúp người dùng hiểu bản chất toán học và tự triển khai thuật toán.
- **Mục tiêu kỹ thuật:** Xây dựng một ứng dụng có kiến trúc rõ ràng, có khả năng kiểm thử, mở rộng và triển khai.

## 3. Phạm vi phiên bản MVP

Các chức năng chính:

1. Quản lý tập dữ liệu.
2. Khám phá và phân tích dữ liệu.
3. Cấu hình Feature và Target.
4. Tiền xử lý dữ liệu.
5. Cấu hình mô hình Linear Regression.
6. Huấn luyện bằng NumPy và PyTorch.
7. Đánh giá mô hình.
8. Trực quan hóa quá trình huấn luyện.
9. Dự đoán dữ liệu mới.
10. Quản lý và so sánh các experiments.

## 4. FR-01 – Quản lý tập dữ liệu

### 4.1. Mục tiêu

Cho phép người dùng tải lên, kiểm tra, khám phá và quản lý các tập dữ liệu được sử dụng trong quá trình huấn luyện Linear Regression.

### 4.2. Các chức năng con

- FR-01.1: Tải lên tập dữ liệu CSV.
- FR-01.2: Kiểm tra cấu trúc và chất lượng dữ liệu.
- FR-01.3: Khám phá dữ liệu.
- FR-01.4: Cấu hình vai trò Feature và Target.
- FR-01.5: Quản lý tập dữ liệu.
- FR-01.6: Chuẩn bị dữ liệu cho ML Core.

### 4.3. Yêu cầu chi tiết

**FR-01.1 – Tải lên tập dữ liệu**

- Cho phép tải file CSV.
- Kiểm tra định dạng và nội dung file.
- Từ chối file rỗng hoặc không thể phân tích.
- Tạo định danh duy nhất cho dataset.
- Lưu tên file, kích thước, thời gian tải lên và trạng thái xử lý.
- Thông báo kết quả tải lên.

**FR-01.2 – Kiểm tra cấu trúc dữ liệu**

- Xác định số hàng và số cột.
- Nhận diện kiểu dữ liệu từng cột.
- Phát hiện missing values.
- Thống kê duplicate rows.
- Phát hiện giá trị vô hạn.
- Phát hiện lỗi phân tích dữ liệu.
- Không tự ý thay đổi dữ liệu gốc.

**FR-01.3 – Khám phá dữ liệu**

- Hiển thị dữ liệu dưới dạng bảng.
- Hiển thị thông tin từng cột.
- Hiển thị thống kê mô tả cho cột số: Count, Mean, Std, Min, 25%, 50%, 75%, Max.
- Hiển thị số lượng missing values.
- Cảnh báo các vấn đề về chất lượng dữ liệu.

**FR-01.4 – Cấu hình Feature và Target**

- Cho phép chọn một hoặc nhiều Feature.
- Cho phép chọn một Target.
- Target không được đồng thời là Feature.
- Kiểm tra kiểu dữ liệu của các cột được chọn.
- Cảnh báo missing values.
- Tạo cấu trúc dữ liệu X và y khi cấu hình hợp lệ.
- Lưu cấu hình lựa chọn cột cùng Experiment.

**FR-01.5 – Quản lý tập dữ liệu**

- Hiển thị danh sách dataset.
- Xem thông tin chi tiết.
- Tìm kiếm theo tên.
- Xóa dataset.
- Xử lý an toàn các tham chiếu từ experiments liên quan.

**FR-01.6 – Chuẩn bị dữ liệu cho ML Core**

- Chuyển Feature thành ma trận số X.
- Chuyển Target thành vector hoặc ma trận y.
- Đảm bảo số samples của X và y bằng nhau.
- Kiểm tra kiểu dữ liệu số.
- Thông báo lỗi nếu không thể chuyển đổi.
- Không thực hiện preprocessing ngầm.

### 4.4. Quy tắc nghiệp vụ

- Chỉ hỗ trợ CSV trong MVP.
- Chỉ hỗ trợ một Target cho Linear Regression cơ bản.
- Feature và Target phải có thể chuyển đổi thành dữ liệu số trước khi huấn luyện.
- Missing values được phát hiện nhưng không tự động loại bỏ.
- Không tự động chuẩn hóa dữ liệu.
- Không tự động loại bỏ outliers.
- Dữ liệu gốc phải được bảo toàn.
- Giới hạn file và số hàng phải được cấu hình tập trung.

### 4.5. Acceptance Criteria

| Mã    | Tiêu chí                    | Kết quả                         |
| ----- | --------------------------- | ------------------------------- |
| AC-01 | Upload CSV hợp lệ           | Thành công                      |
| AC-02 | Upload file không phải CSV  | Bị từ chối                      |
| AC-03 | Upload file rỗng            | Bị từ chối                      |
| AC-04 | CSV có missing values       | Upload được và cảnh báo         |
| AC-05 | CSV có duplicate rows       | Thống kê được                   |
| AC-06 | Xem trước dữ liệu           | Hiển thị chính xác              |
| AC-07 | Chọn Feature và Target      | Chấp nhận cấu hình hợp lệ       |
| AC-08 | Target đồng thời là Feature | Bị từ chối                      |
| AC-09 | Chuyển đổi X và y           | Đúng kích thước và kiểu dữ liệu |
| AC-10 | Xóa dataset                 | Xử lý theo quy tắc an toàn      |

### 4.6. Kiến thức liên quan

- Dataset và Sample.
- Feature và Target.
- Feature Matrix X.
- Target Vector y.
- Missing Values.
- Data Types.
- Descriptive Statistics.
- Data Leakage.
- Numerical Representation.

### 4.7. Thành phần hệ thống liên quan

| Thành phần         | Trách nhiệm                            |
| ------------------ | -------------------------------------- |
| React + TypeScript | Upload, preview và cấu hình cột        |
| FastAPI            | Tiếp nhận request và điều phối         |
| Pandas             | Đọc CSV và khám phá dữ liệu            |
| NumPy              | Chuyển dữ liệu thành ma trận và vector |
| PostgreSQL         | Lưu metadata                           |
| File Storage       | Lưu file gốc                           |
| ML Core            | Tiếp nhận X và y                       |

## 5. Các chức năng dự kiến tiếp theo

| Mã    | Chức năng           | Mô tả                                         |
| ----- | ------------------- | --------------------------------------------- |
| FR-02 | Data Preprocessing  | Xử lý missing values, encoding, scaling       |
| FR-03 | Model Configuration | Cấu hình Linear Regression và hyperparameters |
| FR-04 | Model Training      | Huấn luyện bằng NumPy và PyTorch              |
| FR-05 | Model Evaluation    | MAE, MSE, RMSE, R²                            |
| FR-06 | Visualization       | Loss Curve, Regression Line, Residual Plot    |
| FR-07 | Prediction          | Dự đoán dữ liệu mới                           |
| FR-08 | Experiment Tracking | Lưu và so sánh experiments                    |

## 6. Nguyên tắc kiến trúc

ML Core phải độc lập với FastAPI, React và PostgreSQL.

Các thành phần giao tiếp với ML Core thông qua dữ liệu đầu vào và kết quả được định nghĩa rõ ràng. Không để logic toán học và thuật toán Machine Learning phụ thuộc vào tầng giao tiếp hoặc lưu trữ.

## 7. Trạng thái tài liệu

Tài liệu này là bản đặc tả ban đầu. Các giới hạn kỹ thuật như kích thước file, số hàng tối đa, chính sách lưu trữ và thời gian xử lý sẽ được xác định trong giai đoạn thiết kế kỹ thuật.
