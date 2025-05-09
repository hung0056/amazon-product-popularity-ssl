# Ứng dụng học bán giám sát trong dự báo nhu cầu sản phẩm mới trên Amazon.

> Đồ án 2 – Nhóm 1 – ĐH Kinh tế Kĩ thuật Công nghiệp, Tháng 5/2025  
> Dữ liệu: *amazon_sales.csv*  
> Mục tiêu: Dự báo `rating_count` (số lượt đánh giá – đại diện cho nhu cầu) của sản phẩm mới trên Amazon bằng kỹ thuật **Học bán giám sát (SSL)**.

---

## Tổng quan đề tài
Dự án này sử dụng phương pháp học bán giám sát để cải thiện việc dự báo nhu cầu khi dữ liệu có nhãn rất ít.  
Các bước thực hiện:
-   Phân tích dữ liệu khám phá (EDA)
-   Làm sạch dữ liệu và trích xuất đặc trưng
-   Mô hình baseline (Random Forest, XGBoost)
-   SSL:
  - **Pseudo-Labeling**
  - **Label Spreading** (dựa trên đồ thị)

---

## Cấu trúc thư mục

```bash
amazon-product-popularity-ssl/
├── data/
│   ├── raw/               # Dữ liệu gốc (.csv)
│   ├── processed/         # Dữ liệu đã xử lý: train / test / unlabeled
├── notebooks/             # Notebook EDA, mô hình, biểu đồ
├── src/                   # Mã nguồn chính
│   ├── data/              # Xử lý dữ liệu
│   ├── features/          # Đặc trưng văn bản / số / phân loại
│   ├── models/            # Huấn luyện baseline + SSL
├── outputs/
│   ├── models/            # Mô hình huấn luyện
│   ├── figures/           # Biểu đồ
│   └── metrics/           # Kết quả đánh giá
├── experiments/           # File config .yaml
├── reports/
│   ├── pdf/               # Báo cáo cuối cùng
│   └── slides/            # Slide bảo vệ
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Cài đặt & thiết lập môi trường

```bash
# Clone repo
git clone https://github.com/hung0056/amazon-product-popularity-ssl.git
cd amazon-product-popularity-ssl

# Tạo môi trường ảo
python3 -m venv .venv
source .venv/bin/activate

# Cài đặt thư viện
pip install -r requirements.txt
```

---
## Chạy trên Google Colab

[![Mở trên Colab](https://colab.research.google.com/drive/11sGiDqws4oU6OUcIEhGyCVaHYgY14Egg?usp=sharing)]

---

## Thành viên thực hiện

- **Nhóm 1 – Đồ án 2 – ĐH Kinh tế Kĩ thuật Công nghiệp**  
  Nguyễn Văn Duy, Trần Mạnh Hùng, Ninh Hữu Duy, Nguyễn Bá Duy Anh  
  Giảng viên hướng dẫn: Lê Hằng Anh
