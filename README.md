# 📋 XML - 20 Đề HÓA ĐƠN THANH TOÁN + Giải

> Dạng bài tập thực tế: Tạo file XML từ hóa đơn và query dữ liệu

---

## 📌 TEMPLATE XML HÓA ĐƠN CƠ BẢN

```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>12345</so_hoa_don>
    <ho_ten_khach_hang>Nguyễn Văn A</ho_ten_khach_hang>
    <ngay_lap>01/06/2020</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
      <so_luong>4</so_luong>
      <don_gia>600000</don_gia>
      <thanh_tien>2400000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
      <so_luong>5</so_luong>
      <don_gia>150000</don_gia>
      <thanh_tien>750000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
      <so_luong>10</so_luong>
      <don_gia>50000</don_gia>
      <thanh_tien>500000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>3650000</tong_tien>
</hoa_don>
```

---

## 📝 ĐỀ 1: Lấy số hóa đơn

### XML Data:
```xml
<hoa_don>
  <so_hoa_don>12345</so_hoa_don>
  <ho_ten_khach_hang>Nguyễn Văn A</ho_ten_khach_hang>
</hoa_don>
```

### XPath:
```xpath
//so_hoa_don
```

### Kết quả:
```
12345
```

---

## 📝 ĐỀ 2: Lấy tên khách hàng

### XML Data:
```xml
<hoa_don>
  <so_hoa_don>12345</so_hoa_don>
  <ho_ten_khach_hang>Nguyễn Văn A</ho_ten_khach_hang>
</hoa_don>
```

### XPath:
```xpath
//ho_ten_khach_hang
```

### Kết quả:
```
Nguyễn Văn A
```

---

## 📝 ĐỀ 3: Lấy ngày lập hóa đơn

### XML Data:
```xml
<hoa_don>
  <thong_tin_chung>
    <ngay_lap>01/06/2020</ngay_lap>
  </thong_tin_chung>
</hoa_don>
```

### XPath:
```xpath
//ngay_lap
```

### Kết quả:
```
01/06/2020
```

---

## 📝 ĐỀ 4: Lấy tất cả tên dịch vụ

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu/ten_dich_vu
```

### Kết quả:
```
Thuê phòng (loại A)
Thuê xe (loại 4 chỗ)
Điện thoại (loại 1)
```

---

## 📝 ĐỀ 5: Lấy tất cả đơn giá

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <don_gia>600000</don_gia>
  </dich_vu>
  <dich_vu>
    <don_gia>150000</don_gia>
  </dich_vu>
  <dich_vu>
    <don_gia>50000</don_gia>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu/don_gia
```

### Kết quả:
```
600000
150000
50000
```

---

## 📝 ĐỀ 6: Lấy dịch vụ đầu tiên

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
    <so_luong>4</so_luong>
    <don_gia>600000</don_gia>
    <thanh_tien>2400000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[1]/ten_dich_vu
```

### Kết quả:
```
Thuê phòng (loại A)
```

---

## 📝 ĐỀ 7: Lấy dịch vụ cuối cùng

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[last()]/ten_dich_vu
```

### Kết quả:
```
Điện thoại (loại 1)
```

---

## 📝 ĐỀ 8: Tính tổng thành tiền

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><thanh_tien>2400000</thanh_tien></dich_vu>
  <dich_vu><thanh_tien>750000</thanh_tien></dich_vu>
  <dich_vu><thanh_tien>500000</thanh_tien></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
sum(//dich_vu/thanh_tien)
```

### Kết quả:
```
3650000
```

---

## 📝 ĐỀ 9: Lấy dịch vụ có thành tiền cao nhất

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
    <thanh_tien>2400000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
    <thanh_tien>750000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
    <thanh_tien>500000</thanh_tien>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[thanh_tien = max(//dich_vu/thanh_tien)]/ten_dich_vu
```

### Kết quả:
```
Thuê phòng (loại A)
```

---

## 📝 ĐỀ 10: Đếm số dịch vụ

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
count(//dich_vu)
```

### Kết quả:
```
3
```

---

## 📝 ĐỀ 11: Lấy dịch vụ có đơn giá > 100.000

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
    <don_gia>600000</don_gia>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
    <don_gia>150000</don_gia>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
    <don_gia>50000</don_gia>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[don_gia > 100000]/ten_dich_vu
```

### Kết quả:
```
Thuê phòng (loại A)
Thuê xe (loại 4 chỗ)
```

---

## 📝 ĐỀ 12: Lấy dịch vụ có số lượng >= 5

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
    <so_luong>4</so_luong>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
    <so_luong>5</so_luong>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
    <so_luong>10</so_luong>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[so_luong >= 5]/ten_dich_vu
```

### Kết quả:
```
Thuê xe (loại 4 chỗ)
Điện thoại (loại 1)
```

---

## 📝 ĐỀ 13: Tính tổng số lượng

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><so_luong>4</so_luong></dich_vu>
  <dich_vu><so_luong>5</so_luong></dich_vu>
  <dich_vu><so_luong>10</so_luong></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
sum(//dich_vu/so_luong)
```

### Kết quả:
```
19
```

---

## 📝 ĐỀ 14: Tính giá trung bình

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><don_gia>600000</don_gia></dich_vu>
  <dich_vu><don_gia>150000</don_gia></dich_vu>
  <dich_vu><don_gia>50000</don_gia></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
sum(//dich_vu/don_gia) div count(//dich_vu)
```

### Kết quả:
```
266666.666...
```

---

## 📝 ĐỀ 15: Lấy dịch vụ chứa từ "phòng"

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[contains(ten_dich_vu, 'phòng')]/ten_dich_vu
```

### Kết quả:
```
Thuê phòng (loại A)
```

---

## 📝 ĐỀ 16: Lấy dịch vụ bắt đầu với "Thuê"

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu></dich_vu>
  <dich_vu><ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[starts-with(ten_dich_vu, 'Thuê')]/ten_dich_vu
```

### Kết quả:
```
Thuê phòng (loại A)
Thuê xe (loại 4 chỗ)
```

---

## 📝 ĐỀ 17: Lấy dịch vụ có thanh tiền từ 500.000 đến 2.000.000

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
    <thanh_tien>2400000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
    <thanh_tien>750000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
    <thanh_tien>500000</thanh_tien>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[thanh_tien >= 500000 and thanh_tien <= 2000000]/ten_dich_vu
```

### Kết quả:
```
Thuê xe (loại 4 chỗ)
Điện thoại (loại 1)
```

---

## 📝 ĐỀ 18: Đếm dịch vụ có đơn giá > 100.000

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu><don_gia>600000</don_gia></dich_vu>
  <dich_vu><don_gia>150000</don_gia></dich_vu>
  <dich_vu><don_gia>50000</don_gia></dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
count(//dich_vu[don_gia > 100000])
```

### Kết quả:
```
2
```

---

## 📝 ĐỀ 19: Lấy thông tin đầy đủ dịch vụ thứ 2

### XML Data:
```xml
<danh_sach_dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
    <so_luong>4</so_luong>
    <don_gia>600000</don_gia>
    <thanh_tien>2400000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
    <so_luong>5</so_luong>
    <don_gia>150000</don_gia>
    <thanh_tien>750000</thanh_tien>
  </dich_vu>
  <dich_vu>
    <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
    <so_luong>10</so_luong>
    <don_gia>50000</don_gia>
    <thanh_tien>500000</thanh_tien>
  </dich_vu>
</danh_sach_dich_vu>
```

### XPath:
```xpath
//dich_vu[2]/*
```

### Kết quả:
```
Thuê xe (loại 4 chỗ)
5
150000
750000
```

---

## 📝 ĐỀ 20: Lấy tổng tiền từ XML hoàn chỉnh

### XML Data:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>12345</so_hoa_don>
    <ho_ten_khach_hang>Nguyễn Văn A</ho_ten_khach_hang>
    <ngay_lap>01/06/2020</ngay_lap>
  </thong_tin_chung>
  <danh_sach_dich_vu>
    <dich_vu>
      <ten_dich_vu>Thuê phòng (loại A)</ten_dich_vu>
      <so_luong>4</so_luong>
      <don_gia>600000</don_gia>
      <thanh_tien>2400000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Thuê xe (loại 4 chỗ)</ten_dich_vu>
      <so_luong>5</so_luong>
      <don_gia>150000</don_gia>
      <thanh_tien>750000</thanh_tien>
    </dich_vu>
    <dich_vu>
      <ten_dich_vu>Điện thoại (loại 1)</ten_dich_vu>
      <so_luong>10</so_luong>
      <don_gia>50000</don_gia>
      <thanh_tien>500000</thanh_tien>
    </dich_vu>
  </danh_sach_dich_vu>
  <tong_tien>3650000</tong_tien>
</hoa_don>
```

### XPath (Cách 1 - Lấy từ node):
```xpath
//tong_tien
```

### XPath (Cách 2 - Tính từ dịch vụ):
```xpath
sum(//danh_sach_dich_vu/dich_vu/thanh_tien)
```

### Kết quả:
```
3650000
```

---

## 📊 BẢNG TỔNG HỢP 20 ĐỀ

| Đề | Mô tả | XPath |
|----|-------|-------|
| 1 | Lấy số hóa đơn | `//so_hoa_don` |
| 2 | Lấy tên khách hàng | `//ho_ten_khach_hang` |
| 3 | Lấy ngày lập | `//ngay_lap` |
| 4 | Tất cả tên dịch vụ | `//dich_vu/ten_dich_vu` |
| 5 | Tất cả đơn giá | `//dich_vu/don_gia` |
| 6 | Dịch vụ đầu tiên | `//dich_vu[1]/ten_dich_vu` |
| 7 | Dịch vụ cuối cùng | `//dich_vu[last()]/ten_dich_vu` |
| 8 | Tổng thành tiền | `sum(//dich_vu/thanh_tien)` |
| 9 | Dịch vụ đắt nhất | `//dich_vu[thanh_tien = max(//dich_vu/thanh_tien)]/ten_dich_vu` |
| 10 | Đếm dịch vụ | `count(//dich_vu)` |
| 11 | Dịch vụ giá > 100k | `//dich_vu[don_gia > 100000]/ten_dich_vu` |
| 12 | Dịch vụ SL >= 5 | `//dich_vu[so_luong >= 5]/ten_dich_vu` |
| 13 | Tổng số lượng | `sum(//dich_vu/so_luong)` |
| 14 | Giá trung bình | `sum(//dich_vu/don_gia) div count(//dich_vu)` |
| 15 | Dịch vụ chứa "phòng" | `//dich_vu[contains(ten_dich_vu, 'phòng')]/ten_dich_vu` |
| 16 | Dịch vụ bắt đầu "Thuê" | `//dich_vu[starts-with(ten_dich_vu, 'Thuê')]/ten_dich_vu` |
| 17 | Thanh tiền 500k-2M | `//dich_vu[thanh_tien >= 500000 and thanh_tien <= 2000000]/ten_dich_vu` |
| 18 | Đếm dịch vụ > 100k | `count(//dich_vu[don_gia > 100000])` |
| 19 | Thông tin dịch vụ thứ 2 | `//dich_vu[2]/*` |
| 20 | Tổng tiền hóa đơn | `sum(//dich_vu/thanh_tien)` |

---

**💡 Hướng dẫn sử dụng:**
- Copy XML data vào file `.xml`
- Test XPath bằng các công cụ: XMLSpy, Oxygen XML, hoặc Online XPath Tester
- Thay đổi giá trị để tạo thêm bài tập
- Kết hợp nhiều điều kiện `and/or` để làm khó hơn
