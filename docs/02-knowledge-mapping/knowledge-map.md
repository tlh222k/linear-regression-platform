# Bản đồ kiến thức – Linear Regression Platform

**Mã tài liệu:** KM-001  
**Phiên bản:** 1.0  
**Trạng thái:** Bản nháp thiết kế  
**Ngôn ngữ:** Tiếng Việt

## 1. Mục đích

Tài liệu này xác định các kiến thức cần thiết để nghiên cứu, triển khai và xây dựng Linear Regression Platform.

Knowledge Map liên kết ba thành phần:

- Kiến thức toán học và Machine Learning.
- Phương pháp triển khai bằng Python, NumPy và PyTorch.
- Các module và tính năng tương ứng trong hệ thống.

Mục tiêu là đảm bảo mỗi kiến thức được học đều có khả năng ứng dụng vào một phần cụ thể của sản phẩm.

## 2. Nguyên tắc học tập và triển khai

1. Hiểu trực giác trước khi tiếp cận công thức.
2. Hiểu công thức trước khi sử dụng thư viện.
3. Tự triển khai thuật toán bằng NumPy.
4. Đối chiếu kết quả với PyTorch.
5. Viết unit tests để xác minh tính đúng đắn.
6. Tích hợp thuật toán vào ML Core.
7. Đưa chức năng lên Backend và Frontend.
8. Đánh giá bằng thực nghiệm và trực quan hóa.

## 3. Nhóm kiến thức 01 – Mathematical Foundations

### 3.1. Linear Algebra

- Scalar, Vector, Matrix.
- Vector Operations.
- Dot Product.
- Matrix Multiplication.
- Transpose.
- Matrix Shape và Dimensions.
- Linear Systems.
- Norms.

Ứng dụng:

- Biểu diễn Feature Matrix X.
- Biểu diễn Target y.
- Tính Prediction bằng phép nhân ma trận.
- Tính Gradient cho nhiều Features.

### 3.2. Calculus

- Functions và Graphs.
- Limits.
- Derivatives.
- Partial Derivatives.
- Chain Rule.
- Gradient.
- Second-order Derivatives.
- Convexity.

Ứng dụng:

- Tính đạo hàm của Loss Function.
- Xác định hướng cập nhật Parameters.
- Hiểu Gradient Descent.
- Phân tích bề mặt Loss Function.

### 3.3. Probability và Statistics

- Random Variables.
- Probability Distributions.
- Expectation.
- Mean và Median.
- Variance và Standard Deviation.
- Covariance và Correlation.
- Sampling.

Ứng dụng:

- Khám phá dữ liệu.
- Phân tích phân phối.
- Hiểu sai số dự đoán.
- Đánh giá mô hình.

## 4. Nhóm kiến thức 02 – Machine Learning Foundations

### 4.1. Dataset và Data Representation

- Samples.
- Features.
- Target.
- Feature Matrix.
- Target Vector.
- Training Set.
- Validation Set.
- Test Set.

### 4.2. Linear Regression

- Simple Linear Regression.
- Multiple Linear Regression.
- Hypothesis Function.
- Weights và Bias.
- Prediction.
- Residuals.

### 4.3. Loss Functions

- Mean Squared Error.
- Mean Absolute Error.
- Residual Sum of Squares.

### 4.4. Optimization

- Parameters Optimization.
- Gradient Descent.
- Stochastic Gradient Descent.
- Mini-batch Gradient Descent.
- Learning Rate.
- Epoch.
- Batch Size.
- Convergence.

### 4.5. Model Generalization

- Train/Test Split.
- Underfitting.
- Overfitting.
- Bias và Variance.
- Data Leakage.

## 5. Nhóm kiến thức 03 – Python, NumPy và PyTorch

### 5.1. Python

- Functions.
- Classes và Objects.
- Type Hints.
- Dataclasses.
- Exception Handling.
- Modules và Packages.
- Virtual Environments.

### 5.2. NumPy

- ndarray.
- Array Creation.
- Indexing và Slicing.
- Broadcasting.
- Vectorization.
- Matrix Operations.
- Random Number Generation.
- Numerical Stability.

### 5.3. PyTorch

- Tensor.
- Tensor Operations.
- nn.Module.
- nn.Linear.
- nn.MSELoss.
- Computation Graph.
- Autograd.
- backward().
- torch.optim.SGD.
- Training Loop.

## 6. Nhóm kiến thức 04 – ML Core Engineering

Các module dự kiến:

| Module        | Trách nhiệm                  |
| ------------- | ---------------------------- |
| Data          | Quản lý dữ liệu đầu vào      |
| Preprocessing | Xử lý và biến đổi dữ liệu    |
| Model         | Định nghĩa Linear Regression |
| Loss          | Tính toán Loss               |
| Optimizer     | Cập nhật Parameters          |
| Trainer       | Điều phối Training Loop      |
| Evaluator     | Tính toán Metrics            |
| Predictor     | Thực hiện Prediction         |
| Experiment    | Lưu cấu hình và kết quả      |

Yêu cầu:

- Tách biệt thuật toán khỏi API.
- Có interface rõ ràng.
- Hỗ trợ NumPy và PyTorch.
- Có unit tests.
- Kiểm soát Input và Output.
- Có khả năng mở rộng sang thuật toán khác.

## 7. Nhóm kiến thức 05 – Full-stack Engineering

### 7.1. Frontend

- React.
- TypeScript.
- Component Architecture.
- React Hooks.
- State Management.
- API Integration.
- Form Validation.
- Plotly.js.

### 7.2. Backend

- Python và FastAPI.
- REST API.
- Pydantic.
- Dependency Injection.
- Request Validation.
- Error Handling.
- Logging.

### 7.3. Database

- PostgreSQL.
- SQL.
- SQLAlchemy.
- Database Schema.
- Relationships.
- Transactions.
- Migrations.

### 7.4. Testing và Infrastructure

- Pytest.
- Unit Testing.
- Integration Testing.
- Docker.
- Docker Compose.
- GitHub Actions.
- CI/CD.
- Environment Configuration.

## 8. Mapping kiến thức với repository

| Repository Path        | Nội dung                       |
| ---------------------- | ------------------------------ |
| packages/ml-core/      | ML algorithms và core modules  |
| apps/backend/          | Backend API                    |
| apps/frontend/         | Frontend application           |
| experiments/notebooks/ | Mathematical và ML experiments |
| experiments/results/   | Experimental results           |
| tests/                 | Automated tests                |
| docs/04-mathematics/   | Mathematical documentation     |
| docs/05-engineering/   | Engineering documentation      |

## 9. Thứ tự triển khai

1. Mathematical Foundations.
2. Linear Regression từ đầu bằng NumPy.
3. Linear Regression bằng PyTorch.
4. ML Core Engineering.
5. Backend và Database.
6. Frontend và Visualization.
7. Integration và Production Engineering.

Mỗi giai đoạn cần có kiến thức đầu vào, bài thực hành, sản phẩm triển khai và tiêu chí kiểm thử.

## 10. Nguyên tắc đánh giá tiến độ

Một chủ đề chỉ được đánh dấu hoàn thành khi:

- Giải thích được bản chất.
- Hiểu và tự diễn giải được công thức.
- Tự triển khai được bằng Python.
- Có thể giải thích các thành phần code.
- Có kiểm thử xác nhận kết quả.
- Biết kiến thức đó được sử dụng ở đâu trong hệ thống.

## 11. Phạm vi mở rộng

Sau khi hoàn thành phiên bản Linear Regression, kiến trúc có thể được mở rộng để hỗ trợ:

- Polynomial Regression.
- Regularization: Ridge và Lasso.
- Logistic Regression.
- Các mô hình Machine Learning khác.
- Experiment Comparison.
- Model Versioning.
- Model Serving.

Các nội dung mở rộng không thuộc phạm vi triển khai MVP ban đầu.
