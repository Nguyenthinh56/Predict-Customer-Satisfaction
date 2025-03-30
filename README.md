## Customer Satisfaction Prediction Analysis

### Mô tả
Tệp notebook `predict_customer_satisfaction.ipynb` chứa mã nguồn phân tích và dự đoán mức độ hài lòng của khách hàng dựa trên tập dữ liệu **Customer Support Ticket Dataset** từ Kaggle. Bộ dữ liệu bao gồm các phiếu hỗ trợ khách hàng cho nhiều sản phẩm công nghệ khác nhau. Bao gồm các yêu cầu của khách hàng liên quan đến sự cố phần cứng, lỗi phần mềm, sự cố mạng, quyền truy cập tài khoản, mất dữ liệu và các chủ đề hỗ trợ khác. Bộ dữ liệu cung cấp thông tin về khách hàng, sản phẩm đã mua, loại phiếu, kênh phiếu, trạng thái phiếu và các chi tiết liên quan khác.

Phân tích này nhằm mục đích tìm hiểu các yếu tố quan trọng tác động đến mức độ hài lòng của khách hàng, từ đó xây dựng mô hình Machine Learning có khả năng dự đoán mức độ hài lòng dựa trên các đặc trưng đầu vào. Việc này giúp doanh nghiệp cải thiện dịch vụ, tối ưu hóa quy trình xử lý khiếu nại và nâng cao trải nghiệm khách hàng.

### Nội dung chính của Notebook
- **Tiền xử lý dữ liệu:**
  - Kiểm tra và xử lý các giá trị bị thiếu trong tập dữ liệu.
  - Chuyển đổi và chuẩn hóa các biến số để phù hợp với mô hình Machine Learning.
  - Mã hóa các biến phân loại để có thể đưa vào mô hình dự đoán.

- **Phân tích dữ liệu:**
  - Tạo các thống kê mô tả để hiểu rõ hơn về tập dữ liệu.
  - Trực quan hóa phân bố của các biến quan trọng bằng biểu đồ histogram, boxplot và heatmap.

- **Phân tích mối quan hệ:**
  - Sử dụng ma trận tương quan để xác định mức độ liên kết giữa các đặc trưng và mức độ hài lòng của khách hàng.
  - Sử dụng boxplot để xem xét sự ảnh hưởng của một số yếu tố như **thời gian xử lý khiếu nại** đến sự hài lòng của khách hàng.

- **Huấn luyện và tối ưu hóa mô hình dự đoán:**
  - Xây dựng và so sánh hai mô hình Machine Learning: **Logistic Regression** và **Random Forest**.
  - Điều chỉnh tham số mô hình bằng **Grid Search và Randomized Search** để tìm cấu hình tốt nhất.
  - Sử dụng **Feature Importance** để chọn ra các đặc trưng quan trọng nhất giúp cải thiện độ chính xác của mô hình.

- **Đánh giá mô hình:**
  - Sử dụng các chỉ số như Accuracy, Precision, Recall, F1-score để đo lường hiệu suất mô hình.
  - Trực quan hóa kết quả dự đoán bằng ma trận nhầm lẫn (Confusion Matrix).
  - So sánh đường cong ROC của các mô hình để đánh giá khả năng phân loại chính xác.

### Kết quả đạt được & Insight
1. **Phân tích dữ liệu**
   - Một số cột như **Resolution** và **Time to Resolution** có nhiều giá trị bị thiếu, có thể gây ảnh hưởng đến mô hình nếu không được xử lý đúng cách.
   - Phân phối điểm **Customer Satisfaction Rating** có xu hướng lệch về phía các đánh giá tích cực, cho thấy phần lớn khách hàng hài lòng với dịch vụ.

2. **Mối quan hệ giữa các đặc trưng và sự hài lòng của khách hàng**
   - Một số đặc trưng có mức tương quan thấp với sự hài lòng của khách hàng, nhưng vẫn có thể đóng vai trò hỗ trợ trong việc dự đoán.
   - Phân tích boxplot cho thấy **thời gian xử lý khiếu nại dài có thể liên quan đến mức độ hài lòng thấp hơn**, gợi ý rằng việc cải thiện tốc độ phản hồi có thể giúp nâng cao trải nghiệm khách hàng.

3. **Đánh giá mô hình dự đoán sự hài lòng**
   - Mô hình **Random Forest** đạt độ chính xác cao hơn so với Logistic Regression, đặc biệt với các chỉ số Precision và Recall cao hơn.
   - **Random Forest có chỉ số Recall và F1-score cao hơn**, giúp dự đoán chính xác hơn các trường hợp khách hàng không hài lòng, giúp doanh nghiệp nhận diện và giải quyết vấn đề kịp thời.
   - **Biểu đồ ROC Curve** cho thấy mô hình Random Forest có diện tích dưới đường cong lớn hơn, chứng minh mô hình này hoạt động hiệu quả hơn trong việc phân loại khách hàng hài lòng và không hài lòng.
   - Việc **tối ưu hóa tham số** bằng **Grid Search và Randomized Search** đã giúp cải thiện đáng kể độ chính xác và khả năng tổng quát của mô hình.

