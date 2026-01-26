#  Heart Disease Prediction – Data Science Project

##  Giới thiệu
Dự án này xây dựng mô hình **Machine Learning** nhằm dự đoán nguy cơ mắc **bệnh tim** dựa trên các yếu tố sức khỏe và lối sống như tuổi tác, BMI, hút thuốc, tiểu đường, tập thể dục,…

Dự án được thực hiện theo **quy trình Data Science chuẩn**, phù hợp cho:
- Sinh viên Khoa học Dữ liệu
- Báo cáo môn học
- Ứng tuyển **Intern Data / Machine Learning**

---

##  Dataset
- File: `heart.csv`
- Biến mục tiêu: **Heart_Disease**
  - `1`: Có bệnh tim
  - `0`: Không có bệnh tim

### Các biến trong dataset
| Nhóm | Biến |
|----|----|
| Nhân khẩu học | Sex, Age_Category |
| Sức khỏe | BMI, Weight_(kg), General_Health |
| Lối sống | Exercise, Smoking_History, Alcohol_Consumption |
| Bệnh lý | Diabetes, Depression |
| Target | Heart_Disease |

---

##  Mục tiêu
- Giải bài toán **phân lớp nhị phân**
- Dự đoán khả năng mắc bệnh tim
- Phân tích các yếu tố ảnh hưởng đến bệnh tim

---

##  Exploratory Data Analysis (EDA)

### Phân phối biến mục tiêu
- Dữ liệu có phân bố tương đối cân bằng giữa hai lớp
- Phù hợp để huấn luyện mô hình phân lớp

### Nhận xét
- Tuổi, BMI, tiền sử hút thuốc và tiểu đường có ảnh hưởng rõ rệt
- Dataset chứa nhiều biến **categorical** → cần encoding

---

##  Tiền xử lý dữ liệu

- One-Hot Encoding cho biến phân loại (`get_dummies`)
- Chuẩn hóa dữ liệu bằng `StandardScaler`
- Chia dữ liệu Train/Test theo tỷ lệ **80/20**
- Sử dụng `stratify` để giữ nguyên tỷ lệ nhãn

---

##  Mô hình sử dụng

### Logistic Regression
- Mô hình baseline
- Dễ giải thích
- Hiệu quả khá tốt

### Random Forest Classifier
- Mô hình chính
- Bắt được quan hệ phi tuyến
- Ít overfitting
- Cho kết quả tốt và ổn định

---

##  Kết quả & Phân tích Output

### Accuracy
- Random Forest đạt độ chính xác cao hơn Logistic Regression
- Phù hợp với bài toán dự đoán y tế

### Classification Report
- Precision và Recall đều ở mức tốt
- Recall của lớp `Heart_Disease = 1` cao  
→ Mô hình phát hiện tốt người có nguy cơ mắc bệnh tim

### Confusion Matrix
- Số lượng **False Negative thấp**
- Giảm nguy cơ bỏ sót bệnh nhân
- Phù hợp cho hệ thống sàng lọc ban đầu

---

##  Feature Importance (Random Forest)

Các yếu tố quan trọng nhất:
1. Age_Category
2. BMI
3. Smoking_History
4. Diabetes
5. General_Health
6. Exercise

 Kết quả phù hợp với kiến thức y khoa thực tế.

---

##  Kết luận
- Random Forest là mô hình phù hợp nhất
- Mô hình dự đoán hiệu quả nguy cơ bệnh tim
- Có thể ứng dụng cho phân tích sức khỏe cộng đồng

---

##  Hướng phát triển
- Hyperparameter Tuning (GridSearchCV)
- Cross Validation
- Xử lý mất cân bằng dữ liệu (SMOTE)
- Triển khai Web App với Streamlit
- So sánh thêm XGBoost / LightGBM

---

##  Tác giả
**Nguyễn Quốc Thuận**  
 Data Science Student  
 Quan tâm: Machine Learning, Analytics
