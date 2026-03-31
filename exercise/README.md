# Image Classification on CIFAR Dataset

## 1. Dataset

Project này sử dụng **CIFAR dataset** (CIFAR-10), là một tập dữ liệu phổ biến trong bài toán phân loại ảnh.

### Thông tin cơ bản:
- Số lượng ảnh: 60,000
  - 50,000 ảnh train
  - 10,000 ảnh test
- Kích thước ảnh: 32x32 pixels
- Số kênh màu: 3 (RGB)
- Số lớp: 10 classes
  - airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

### Đặc điểm:
- Ảnh nhỏ, đa dạng
- Phù hợp để thử nghiệm các mô hình deep learning cơ bản → nâng cao
- Được load trực tiếp từ thư viện (PyTorch / TensorFlow)

---

## 2. Mô tả các file

### 📌 `part123_basic_classification_models.ipynb`

**Mục đích:**
- Xây dựng các mô hình phân loại cơ bản trên CIFAR
- Làm baseline cho các phần sau

**Nội dung chính:**
- Tiền xử lý dữ liệu
- Xây dựng các mô hình:
  - Softmax Regression
  - Multi-Layer Perceptron (MLP) 
  - Convolutional Neural Network (CNN)
  - Vision Transformer (ViT)
- Training & evaluation
- So sánh kết quả giữa các mô hình
- Ngoài ra phần này còn viết lại mô hình ViT và so sánh với mô hình built-in của Pytorch

---

### 📌 `part4_different_architectural_combinations_and_image_embedding_methods.ipynb`

**Mục đích:**
- Thử nghiệm các kiến trúc khác nhau
- Khai thác các phương pháp embedding ảnh

**Nội dung chính:**
Notebook này triển khai **4 mô hình** (vượt mức tối thiểu 2-3 mô hình):
1. **Hybrid CNN -> Transformer (Spatial Tokens)**  
   CNN backbone trích xuất feature map, sau đó mỗi vị trí không gian là một token.
2. **ViT với patch embedding không overlap**  
   Ảnh được chia patch 4x4, stride = 4.
3. **ViT với patch embedding có overlap**  
   Ảnh được chia patch 4x4, stride = 2.
4. **Hybrid CNN -> Transformer (Channel Tokens)**  
   CNN backbone trích xuất feature map, sau đó mỗi kênh là một token.

---

### 📌 `part5_LSTM_for_image_classification.ipynb`

**Mục đích:**
- Áp dụng **LSTM** cho bài toán phân loại ảnh (một hướng tiếp cận không truyền thống)

**Ý tưởng chính:**
- Biến ảnh thành chuỗi (sequence)
  - Ví dụ: flatten theo hàng/cột
- Đưa vào LSTM để học quan hệ tuần tự

**Nội dung:**
- Chuyển đổi image → sequence
- Xây dựng hai mô hình chính Row-wise và Patch-wise LSTM
- Training và đánh giá
- So sánh

---

## 3. Cách chạy

- Cài đặt các thư viện cần thiết
- Chạy các file từ đầu đến cuối
