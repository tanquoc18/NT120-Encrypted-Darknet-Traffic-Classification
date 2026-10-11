# NT120: Phân loại ứng dụng và nhận diện lưu lượng Darknet trên mạng mã hóa bằng Machine Learning

**Trường Đại học Công nghệ Thông tin — ĐHQG-HCM (UIT)**  
**Khoa Mạng máy tính và Truyền thông**  
**Môn học:** NT120 — Nhập môn Trí tuệ nhân tạo cho Mạng máy tính và An toàn thông tin  
**Lớp:** NT120.R12  
**Nhóm số:** 16  
**Giảng viên hướng dẫn:** TS. Huỳnh Văn Đáng, ThS. Nguyễn Khánh Thuật  

---

## 📌 Giới thiệu Đồ án

Đồ án tập trung nghiên cứu và xây dựng giải pháp **Machine Learning (ML)** nhằm giải quyết **Bài toán kép (Dual-Task)**:
1. **Bài toán 1 (Môi trường mạng):** Nhận diện người dùng đang dùng mạng gì (`Non-VPN`, `VPN`, hay `Tor/Darknet`).
2. **Bài toán 2 (Hành vi ứng dụng):** Nhận diện người dùng đang làm gì (`Browsing`, `Audio-Streaming`, `Video-Streaming`, `Chat`, `File-Transfer`, `VoIP`, `P2P`).

Toàn bộ quá trình phân loại được thực hiện dựa trên các đặc trưng thống kê luồng gói tin (Packet length, Flow duration, Inter-arrival time - IAT) mà **không cần giải mã nội dung gói tin (Payload)**, đảm bảo tôn trọng tính riêng tư và bảo mật đường truyền.

---

## 👥 Danh sách Thành viên Nhóm 16

| STT | MSSV | Họ và tên | Vai trò / Phần đóng góp chính | Email |
|:---:|:---:|:---|:---|:---|
| 1 | **23521306** | **Nguyễn Tấn Quốc** | Trưởng nhóm — Tiền xử lý dữ liệu & Huấn luyện mô hình ML | `23521306@gm.uit.edu.vn` |
| 2 | **23521342** | **Lê Cao Sang** | Thành viên — Khám phá dữ liệu (EDA), Biến đổi đặc trưng & Trực quan hóa | `23521342@gm.uit.edu.vn` |
| 3 | **23520714** | **Bùi Nhật Khánh** | Thành viên — Đánh giá mô hình, Phân tích Privacy & Viết báo cáo | `23520714@gm.uit.edu.vn` |

---

## 📂 Cấu trúc Thư mục

```text
├── NT120_DoAn_Nhom16_PhanLoaiDarknetVPN.ipynb   # File Notebook báo cáo & mã nguồn hoàn chỉnh của Nhóm 16
├── .gitignore                                   # File cấu hình chặn đẩy file dữ liệu nặng lên GitHub
└── README.md                                    # Tài liệu tổng quan dự án
```

---

## 📊 Bộ dữ liệu (Dataset)

- **Bộ dữ liệu chính thức:** `CIC-Darknet2020`
- **Nguồn thu thập:** [Canadian Institute for Cybersecurity (CIC) — University of New Brunswick (UNB)](https://www.unb.ca/cic/datasets/darknet2020.html)
- **Tập tin sử dụng:** `Darknet.csv` (chứa các thuộc tính thống kê luồng mạng cho các lưu lượng Non-Tor, VPN và Tor).

---

## 🛠️ Hướng dẫn Chạy trên Google Colab

1. Tải file `NT120_DoAn_Nhom16_PhanLoaiDarknetVPN.ipynb` về máy.
2. Mở [Google Colab](https://colab.research.google.com) và tải file notebook lên.
3. Tải file `Darknet.csv` (thu thập từ nguồn CIC-Darknet2020 của UNB) lên thư mục làm việc của Google Colab.
4. Chọn menu **Runtime → Run all** để thực thi toàn bộ pipeline từ nạp dữ liệu, tiền xử lý, huấn luyện 3 mô hình cho đến xuất 2 ma trận nhầm lẫn và demo dự đoán kép.
