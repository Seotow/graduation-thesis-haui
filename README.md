# Khóa luận tốt nghiệp – Nhận diện bệnh cây trồng bằng học sâu

**Sinh viên:** Nguyễn Trung Hiếu – 2022600419  
**Trường:** Đại học Công nghiệp Hà Nội  
**Ngành:** Công nghệ Thông tin  
**Năm hoàn thành:** 2026

---

## Đề tài

Xây dựng hệ thống nhận diện bệnh lúa theo thời gian thực, kết hợp hai mô hình học sâu:

- **YOLOv11** – phát hiện và định vị vùng bệnh trên lá lúa (object detection)
- **Swin Transformer** – phân loại bệnh chính xác cao (image classification)

Hệ thống hoạt động qua ứng dụng di động, cho phép nông dân chụp ảnh và nhận kết quả chẩn đoán ngay lập tức.

---

## Công nghệ sử dụng

| Thành phần | Công nghệ |
|---|---|
| Mô hình phát hiện | YOLOv11 (Ultralytics) |
| Mô hình phân loại | Swin Transformer |
| Trích xuất đặc trưng | ArcFace embedding |
| Backend API | FastAPI + PostgreSQL |
| Ứng dụng di động | Expo React Native |
| Triển khai | Docker + Docker Compose |
| Lưu trữ model | Git LFS |

---

## Cấu trúc repository

```
GraduationThesis/
├── notebooks/                          # Notebook huấn luyện mô hình
│   ├── 01_train_yolo.ipynb             # Huấn luyện YOLOv11
│   ├── 02_train_transformer.ipynb      # Huấn luyện Swin Transformer
│   ├── 04_pipeline.ipynb               # Pipeline tích hợp hai mô hình
│   └── 05_arcface.ipynb                # Thực nghiệm ArcFace embedding
├── references/                         # Tài liệu nghiên cứu tham khảo (18 papers)
│   ├── Attention Is All You Need in NeurIPS 2017.pdf
│   ├── Swin Transformer Hierarchical Vision Transformer...pdf
│   ├── Deep Learning in Agriculture A Survey.pdf
│   └── ...
├── plant-care/                         # Ứng dụng hoàn chỉnh (submodule)
├── CNTT_2022600419_Nguyen_Trung_Hieu_Baocao.pdf   # Báo cáo khóa luận
├── CNTT_2022600419_Nguyen_Trung_Hieu_Poster.pdf   # Poster bảo vệ
├── Slide_NguyenTrungHieu.pptx          # Slide bảo vệ
└── README.md
```

---

## Dự án ứng dụng

📦 **[plant-care](https://github.com/Seotow/plant-care)** – Hệ thống nhận diện bệnh cây trồng hoàn chỉnh

Bao gồm:
- `backend/` – FastAPI REST API, xử lý ảnh và dự đoán
- `frontend-mobile/` – Ứng dụng Expo React Native cho iOS/Android
- `models/` – File model YOLOv11 và Swin Transformer (Git LFS)
- `docker/` – Cấu hình Docker cho deploy

---

## Tài liệu nghiên cứu

Các paper tham khảo được lưu trong thư mục `references/`:

| Tài liệu | Nội dung |
|---|---|
| YOLOv8/v11 papers | Real-time object detection |
| Swin Transformer | Hierarchical vision transformer |
| Attention Is All You Need | Kiến trúc Transformer gốc |
| Deep Residual Learning | ResNet – học sâu với skip connections |
| EfficientNet | Model scaling cho CNN |
| Deep Learning in Agriculture | Ứng dụng AI trong nông nghiệp |

---

## Hướng dẫn chạy

Xem chi tiết trong repository **plant-care**:

```bash
# Clone kèm submodule plant-care
git clone --recursive https://github.com/Seotow/graduation-thesis-haui.git

# Hoặc sau khi clone:
git submodule update --init --recursive
```

Cài Git LFS trước khi tải model:

```bash
git lfs install
git lfs pull
```

---

## Kết quả

- Độ chính xác phát hiện (mAP50): đạt kết quả tốt trên tập dữ liệu bệnh lúa
- Pipeline kết hợp YOLO + Swin Transformer cải thiện độ chính xác phân loại
- Ứng dụng di động hoạt động ổn định, cho kết quả thời gian thực

---

*Đây là sản phẩm khóa luận tốt nghiệp năm 2026, được thực hiện dưới sự hướng dẫn của giảng viên Đại học Công nghiệp Hà Nội.*
