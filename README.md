# 📋 20 ĐỀ HÓA ĐƠN THANH TOÁN - XML & GIẢI

> Soạn dữ liệu XML từ các hóa đơn mẫu + Giải thích cấu trúc

---

## 📌 ĐỀ 1: THANH TOÁN DỊCH VỤ KHÁCH SẠN

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 001
Khách hàng: Trần Minh Hùng
Ngày lập: 15/03/2024

Dịch vụ          Số lượng    Đơn giá      Thành tiền
Phòng đơn         3 đêm      500.000 đ    1.500.000 đ
Ăn sáng           3 suất      150.000 đ    450.000 đ
Dịch vụ spa       2 lần       300.000 đ    600.000 đ
                              Tổng tiền:   2.550.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>001</so_hoa_don>
    <ho_ten_khach_hang>Trần Minh Hùng</ho_ten_khach_hang>
    <ngay_lap>15/03/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Phòng đơn</ten_dich_vu>
      <so_luong>3</so_luong>
      <don_gia>500000</don_gia>
      <thanh_tien>1500000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Ăn sáng</ten_dich_vu>
      <so_luong>3</so_luong>
      <don_gia>150000</don_gia>
      <thanh_tien>450000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Dịch vụ spa</ten_dich_vu>
      <so_luong>2</so_luong>
      <don_gia>300000</don_gia>
      <thanh_tien>600000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>2550000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 2: THANH TOÁN ĐIỆN NƯỚC

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 002
Khách hàng: Lê Thị Huỳnh
Ngày lập: 20/03/2024

Dịch vụ          Số lượng    Đơn giá      Thành tiền
Điện             150 kWh     2.000 đ      300.000 đ
Nước             20 m³        45.000 đ     900.000 đ
Xử lý rác         1 tháng      25.000 đ     25.000 đ
                              Tổng tiền:   1.225.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>002</so_hoa_don>
    <ho_ten_khach_hang>Lê Thị Huỳnh</ho_ten_khach_hang>
    <ngay_lap>20/03/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Điện</ten_dich_vu>
      <so_luong>150</so_luong>
      <don_gia>2000</don_gia>
      <thanh_tien>300000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Nước</ten_dich_vu>
      <so_luong>20</so_luong>
      <don_gia>45000</don_gia>
      <thanh_tien>900000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Xử lý rác</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>25000</don_gia>
      <thanh_tien>25000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>1225000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 3: THANH TOÁN MUA HÀNG CỬA HÀNG

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 003
Khách hàng: Nguyễn Quốc Khánh
Ngày lập: 22/03/2024

Sản phẩm         Số lượng    Đơn giá      Thành tiền
Áo sơ mi         2 cái       250.000 đ    500.000 đ
Quần jean        1 cái       350.000 đ    350.000 đ
Giày thể thao    1 đôi       450.000 đ    450.000 đ
                              Tổng tiền:   1.300.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>003</so_hoa_don>
    <ho_ten_khach_hang>Nguyễn Quốc Khánh</ho_ten_khach_hang>
    <ngay_lap>22/03/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_san_pham>
    <san_pham>
      <ten_san_pham>Áo sơ mi</ten_san_pham>
      <so_luong>2</so_luong>
      <don_gia>250000</don_gia>
      <thanh_tien>500000</thanh_tien>
    </san_pham>
    <san_pham>
      <ten_san_pham>Quần jean</ten_san_pham>
      <so_luong>1</so_luong>
      <don_gia>350000</don_gia>
      <thanh_tien>350000</thanh_tien>
    </san_pham>
    <san_pham>
      <ten_san_pham>Giày thể thao</ten_san_pham>
      <so_luong>1</so_luong>
      <don_gia>450000</don_gia>
      <thanh_tien>450000</thanh_tien>
    </san_pham>
  </danh_sach_san_pham>
  <tong_tien>1300000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 4: THANH TOÁN VIỆN PHÍ

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 004
Bệnh nhân: Phan Văn Sơn
Ngày lập: 25/03/2024

Chi phí              Số lượng    Đơn giá      Thành tiền
Khám tổng quát      1 lần       200.000 đ    200.000 đ
Xét nghiệm máu      1 lần       150.000 đ    150.000 đ
Siêu âm tim         1 lần       300.000 đ    300.000 đ
Nằm viện            3 ngày      800.000 đ    2.400.000 đ
                                  Tổng tiền:   3.050.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>004</so_hoa_don>
    <benh_nhan>Phan Văn Sơn</benh_nhan>
    <ngay_lap>25/03/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_chi_phi>
    <chi_phi>
      <ten_chi_phi>Khám tổng quát</ten_chi_phi>
      <so_luong>1</so_luong>
      <don_gia>200000</don_gia>
      <thanh_tien>200000</thanh_tien>
    </chi_phi>
    <chi_phi>
      <ten_chi_phi>Xét nghiệm máu</ten_chi_phi>
      <so_luong>1</so_luong>
      <don_gia>150000</don_gia>
      <thanh_tien>150000</thanh_tien>
    </chi_phi>
    <chi_phi>
      <ten_chi_phi>Siêu âm tim</ten_chi_phi>
      <so_luong>1</so_luong>
      <don_gia>300000</don_gia>
      <thanh_tien>300000</thanh_tien>
    </chi_phi>
    <chi_phi>
      <ten_chi_phi>Nằm viện</ten_chi_phi>
      <so_luong>3</so_luong>
      <don_gia>800000</don_gia>
      <thanh_tien>2400000</thanh_tien>
    </chi_phi>
  </danh_sach_chi_phi>
  <tong_tien>3050000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 5: THANH TOÁN VẬN CHUYỂN HÀNG

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 005
Khách hàng: Hồ Bảo Anh
Ngày lập: 28/03/2024

Dịch vụ          Số lượng    Đơn giá      Thành tiền
Vận chuyển nội tp  2 lần     100.000 đ    200.000 đ
Vận chuyển ngoài tp 1 lần    500.000 đ    500.000 đ
Bảo hiểm hàng      1 lần     150.000 đ    150.000 đ
                              Tổng tiền:   850.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>005</so_hoa_don>
    <ho_ten_khach_hang>Hồ Bảo Anh</ho_ten_khach_hang>
    <ngay_lap>28/03/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Vận chuyển nội tp</ten_dich_vu>
      <so_luong>2</so_luong>
      <don_gia>100000</don_gia>
      <thanh_tien>200000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Vận chuyển ngoài tp</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>500000</don_gia>
      <thanh_tien>500000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Bảo hiểm hàng</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>150000</don_gia>
      <thanh_tien>150000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>850000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 6: THANH TOÁN INTERNET & ĐIỆN THOẠI

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 006
Khách hàng: Võ Minh Tâm
Ngày lập: 01/04/2024

Dịch vụ          Số lượng    Đơn giá      Thành tiền
Internet 100Mbps   1 tháng    350.000 đ    350.000 đ
Điện thoại        1 tháng     80.000 đ     80.000 đ
Truyền hình       1 tháng     120.000 đ    120.000 đ
                              Tổng tiền:   550.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>006</so_hoa_don>
    <ho_ten_khach_hang>Võ Minh Tâm</ho_ten_khach_hang>
    <ngay_lap>01/04/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Internet 100Mbps</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>350000</don_gia>
      <thanh_tien>350000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Điện thoại</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>80000</don_gia>
      <thanh_tien>80000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Truyền hình</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>120000</don_gia>
      <thanh_tien>120000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>550000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 7: THANH TOÁN TAXI

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 007
Khách hàng: Tô Văn Cảnh
Ngày lập: 05/04/2024

Dịch vụ          Số lượng    Đơn giá      Thành tiền
Quãng đường       15 km       12.000 đ     180.000 đ
Chờ xe           2 giờ        5.000 đ      10.000 đ
Phí dịch vụ      1 lần       10.000 đ     10.000 đ
                              Tổng tiền:   200.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>007</so_hoa_don>
    <ho_ten_khach_hang>Tô Văn Cảnh</ho_ten_khach_hang>
    <ngay_lap>05/04/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Quãng đường</ten_dich_vu>
      <so_luong>15</so_luong>
      <don_gia>12000</don_gia>
      <thanh_tien>180000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Chờ xe</ten_dich_vu>
      <so_luong>2</so_luong>
      <don_gia>5000</don_gia>
      <thanh_tien>10000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Phí dịch vụ</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>10000</don_gia>
      <thanh_tien>10000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>200000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 8: THANH TOÁN NHÀ HÀNG

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 008
Khách hàng: Đặng Huy Hoàng
Ngày lập: 08/04/2024

Mặt hàng          Số lượng    Đơn giá      Thành tiền
Cơm chiên         2 suất      85.000 đ     170.000 đ
Canh chua cá      1 tô        120.000 đ    120.000 đ
Rau luộc          1 đĩa       60.000 đ     60.000 đ
Nước ép trái cây  3 li        35.000 đ     105.000 đ
                              Tổng tiền:   455.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>008</so_hoa_don>
    <ho_ten_khach_hang>Đặng Huy Hoàng</ho_ten_khach_hang>
    <ngay_lap>08/04/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_mon_an>
    <mon_an>
      <ten_mon_an>Cơm chiên</ten_mon_an>
      <so_luong>2</so_luong>
      <don_gia>85000</don_gia>
      <thanh_tien>170000</thanh_tien>
    </mon_an>
    <mon_an>
      <ten_mon_an>Canh chua cá</ten_mon_an>
      <so_luong>1</so_luong>
      <don_gia>120000</don_gia>
      <thanh_tien>120000</thanh_tien>
    </mon_an>
    <mon_an>
      <ten_mon_an>Rau luộc</ten_mon_an>
      <so_luong>1</so_luong>
      <don_gia>60000</don_gia>
      <thanh_tien>60000</thanh_tien>
    </mon_an>
    <mon_an>
      <ten_mon_an>Nước ép trái cây</ten_mon_an>
      <so_luong>3</so_luong>
      <don_gia>35000</don_gia>
      <thanh_tien>105000</thanh_tien>
    </mon_an>
  </danh_sach_mon_an>
  <tong_tien>455000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 9: THANH TOÁN TIỆM CẮT TÓC

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 009
Khách hàng: Bùi Văn Thắng
Ngày lập: 10/04/2024

Dịch vụ          Số lượng    Đơn giá      Thành tiền
Cắt tóc          1 lần       80.000 đ     80.000 đ
Gội đầu          1 lần       50.000 đ     50.000 đ
Sấy tóc          1 lần       40.000 đ     40.000 đ
Chăm sóc tóc     1 lần       100.000 đ    100.000 đ
                              Tổng tiền:   270.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>009</so_hoa_don>
    <ho_ten_khach_hang>Bùi Văn Thắng</ho_ten_khach_hang>
    <ngay_lap>10/04/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Cắt tóc</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>80000</don_gia>
      <thanh_tien>80000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Gội đầu</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>50000</don_gia>
      <thanh_tien>50000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Sấy tóc</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>40000</don_gia>
      <thanh_tien>40000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Chăm sóc tóc</ten_dich_vu>
      <so_luong>1</so_luong>
      <don_gia>100000</don_gia>
      <thanh_tien>100000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>270000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 10: THANH TOÁN TIỆM THUỐC

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 010
Khách hàng: Phạm Thị Loan
Ngày lập: 12/04/2024

Thuốc             Số lượng    Đơn giá      Thành tiền
Aspirin 500mg     2 vỉ       45.000 đ     90.000 đ
Vitamin C         1 hộp      120.000 đ    120.000 đ
Kháng sinh        1 lọ       200.000 đ    200.000 đ
Kem mỡ            1 tuýp     85.000 đ     85.000 đ
                              Tổng tiền:   495.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>010</so_hoa_don>
    <ho_ten_khach_hang>Phạm Thị Loan</ho_ten_khach_hang>
    <ngay_lap>12/04/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_thuoc>
    <thuoc>
      <ten_thuoc>Aspirin 500mg</ten_thuoc>
      <so_luong>2</so_luong>
      <don_gia>45000</don_gia>
      <thanh_tien>90000</thanh_tien>
    </thuoc>
    <thuoc>
      <ten_thuoc>Vitamin C</ten_thuoc>
      <so_luong>1</so_luong>
      <don_gia>120000</don_gia>
      <thanh_tien>120000</thanh_tien>
    </thuoc>
    <thuoc>
      <ten_thuoc>Kháng sinh</ten_thuoc>
      <so_luong>1</so_luong>
      <don_gia>200000</don_gia>
      <thanh_tien>200000</thanh_tien>
    </thuoc>
    <thuoc>
      <ten_thuoc>Kem mỡ</ten_thuoc>
      <so_luong>1</so_luong>
      <don_gia>85000</don_gia>
      <thanh_tien>85000</thanh_tien>
    </thuoc>
  </danh_sach_thuoc>
  <tong_tien>495000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 11: THANH TOÁN CỬA HÀNG SÁCH

### Đề bài mẫu:
```
HÓA ĐƠN THANH TOÁN
Số hóa đơn: 011
Khách hàng: Lương Hồng Sơn
Ngày lập: 15/04/2024

Sách              Số lượng    Đơn giá      Thành tiền
Lập trình Python  1 cuốn     250.000 đ    250.000 đ
SQL cơ bản        2 cuốn     180.000 đ    360.000 đ
Web design        1 cuốn     220.000 đ    220.000 đ
                              Tổng tiền:   830.000 đ
```

### Giải - Tạo file XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>011</so_hoa_don>
    <ho_ten_khach_hang>Lương Hồng Sơn</ho_ten_khach_hang>
    <ngay_lap>15/04/2024</ngay_lap>
  </thong_tin_chung>
  <danh_sach_sach>
    <sach>
      <ten_sach>Lập trình Python</ten_sach>
      <so_luong>1</so_luong>
      <don_gia>250000</don_gia>
      <thanh_tien>250000</thanh_tien>
    </sach>
    <sach>
      <ten_sach>SQL cơ bản</ten_sach>
      <so_luong>2</so_luong>
      <don_gia>180000</don_gia>
      <thanh_tien>360000</thanh_tien>
    </sach>
    <sach>
      <ten_sach>Web design</ten_sach>
      <so_luong>1</so_luong>
      <don_gia>220000</don_gia>
      <thanh_tien>220000</thanh_tien>
    </sach>
