# Đồ án tốt nghiệp – Nhận diện bệnh lúa bằng học sâu

**Sinh viên:** Nguyễn Trung Hiếu – 2022600419  
**Trường:** Trường Công nghệ Thông tin và Truyền thông - Đại học Công nghiệp Hà Nội  
**Ngành:** Công nghệ Thông tin  
**Năm bảo vệ:** 2026

---

## Đề tài

**Xây dựng ứng dụng nhận diện bệnh lúa trên thiết bị di động sử dụng học sâu**

Hệ thống kết hợp hai mô hình học sâu để nhận diện và phân loại bệnh trên lá lúa:

- **YOLOv11** – phát hiện và định vị vùng bệnh (object detection)
- **Swin Transformer** – phân loại loại bệnh từ vùng đã phát hiện (image classification)

Kết quả được trả về qua ứng dụng di động, giúp người dùng chụp ảnh và nhận kết quả ngay lập tức.

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
├── CNTT_2022600419_Nguyen_Trung_Hieu_Baocao.pdf   # Báo cáo đồ án tốt nghiệp
├── CNTT_2022600419_Nguyen_Trung_Hieu_Poster.pdf   # Poster bảo vệ đồ án
├── Slide_NguyenTrungHieu.pptx          # Slide bảo vệ đồ án
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

## Tài liệu nộp

| File | Mô tả |
|---|---|
| `CNTT_2022600419_Nguyen_Trung_Hieu_Baocao.pdf` | Báo cáo đồ án tốt nghiệp |
| `CNTT_2022600419_Nguyen_Trung_Hieu_Poster.pdf` | Poster bảo vệ |
| `Slide_NguyenTrungHieu.pptx` | Slide trình bày bảo vệ |
| `Phiếu giao đề tài - Nguyễn Trung Hiếu.pdf` | Phiếu giao đề tài |

---

*Đồ án tốt nghiệp – Đại học Công nghiệp Hà Nội, năm học 2025–2026.*
