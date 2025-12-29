# 📋 20 ĐỀ HÓA ĐƠN - XML + DTD

> Mỗi đề có XML + DTD (Document Type Definition) tương ứng

---

## 📌 ĐỀ 1: DTD CƠ BẢN VỚI ATTRIBUTE

### DTD:
```dtd
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (dich_vu+, tong_tien)>
  <!ATTLIST hoa_don 
    so CDATA #REQUIRED
    khach CDATA #REQUIRED
    ngay CDATA #REQUIRED>
  
  <!ELEMENT dich_vu (#PCDATA)>
  <!ATTLIST dich_vu
    ten CDATA #REQUIRED
    so_luong CDATA #REQUIRED
    don_gia CDATA #REQUIRED
    thanh_tien CDATA #REQUIRED>
  
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (dich_vu+, tong_tien)>
  <!ATTLIST hoa_don so CDATA #REQUIRED khach CDATA #REQUIRED ngay CDATA #REQUIRED>
  <!ELEMENT dich_vu (#PCDATA)>
  <!ATTLIST dich_vu ten CDATA #REQUIRED so_luong CDATA #REQUIRED don_gia CDATA #REQUIRED thanh_tien CDATA #REQUIRED>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don so="001" khach="Trần Minh Hùng" ngay="15/03/2024">
  <dich_vu ten="Phòng đơn" so_luong="3" don_gia="500000" thanh_tien="1500000"/>
  <dich_vu ten="Ăn sáng" so_luong="3" don_gia="150000" thanh_tien="450000"/>
  <tong_tien>1950000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 2: DTD VỚI NESTED ELEMENT

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thong_tin, chi_tiet, tong_tien)>
  
  <!ELEMENT thong_tin (so_hoa_don, khach_hang, ngay_lap)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT khach_hang (ten, loai)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT loai (#PCDATA)>
  <!ELEMENT ngay_lap (#PCDATA)>
  
  <!ELEMENT chi_tiet (dich_vu+)>
  <!ELEMENT dich_vu (ten, chi_tiet_san_pham)>
  <!ELEMENT chi_tiet_san_pham (so_luong, don_vi, don_gia, thanh_tien)>
  <!ELEMENT so_luong (#PCDATA)>
  <!ELEMENT don_vi (#PCDATA)>
  <!ELEMENT don_gia (#PCDATA)>
  <!ELEMENT thanh_tien (#PCDATA)>
  
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thong_tin, chi_tiet, tong_tien)>
  <!ELEMENT thong_tin (so_hoa_don, khach_hang, ngay_lap)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT khach_hang (ten, loai)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT loai (#PCDATA)>
  <!ELEMENT ngay_lap (#PCDATA)>
  <!ELEMENT chi_tiet (dich_vu+)>
  <!ELEMENT dich_vu (ten, chi_tiet_san_pham)>
  <!ELEMENT chi_tiet_san_pham (so_luong, don_vi, don_gia, thanh_tien)>
  <!ELEMENT so_luong (#PCDATA)>
  <!ELEMENT don_vi (#PCDATA)>
  <!ELEMENT don_gia (#PCDATA)>
  <!ELEMENT thanh_tien (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <thong_tin>
    <so_hoa_don>002</so_hoa_don>
    <khach_hang>
      <ten>Lê Thị Huỳnh</ten>
      <loai>Cá nhân</loai>
    </khach_hang>
    <ngay_lap>20/03/2024</ngay_lap>
  </thong_tin>
  <chi_tiet>
    <dich_vu>
      <ten>Điện</ten>
      <chi_tiet_san_pham>
        <so_luong>150</so_luong>
        <don_vi>kWh</don_vi>
        <don_gia>2000</don_gia>
        <thanh_tien>300000</thanh_tien>
      </chi_tiet_san_pham>
    </dich_vu>
    <dich_vu>
      <ten>Nước</ten>
      <chi_tiet_san_pham>
        <so_luong>20</so_luong>
        <don_vi>m³</don_vi>
        <don_gia>45000</don_gia>
        <thanh_tien>900000</thanh_tien>
      </chi_tiet_san_pham>
    </dich_vu>
  </chi_tiet>
  <tong_tien>1200000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 3: DTD VỚI MIXED CONTENT

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (so_hoa_don, mo_ta, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT mo_ta (#PCDATA | chi_tiet)*>
  <!ELEMENT chi_tiet (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (so_hoa_don, mo_ta, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT mo_ta (#PCDATA | chi_tiet)*>
  <!ELEMENT chi_tiet (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <so_hoa_don>003</so_hoa_don>
  <mo_ta>
    Bộ quần áo gồm:
    <chi_tiet>Áo sơ mi: 2 cái x 250.000 = 500.000</chi_tiet>
    <chi_tiet>Quần jean: 1 cái x 350.000 = 350.000</chi_tiet>
    <chi_tiet>Giày thể thao: 1 đôi x 450.000 = 450.000</chi_tiet>
  </mo_ta>
  <tong_tien>1300000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 4: DTD VỚI CHOICE (LỰA CHỌN)

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thong_tin, (chi_phi | dich_vu)+, tong_tien)>
  <!ELEMENT thong_tin (so_hoa_don, benh_nhan, ngay_lap)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT benh_nhan (#PCDATA)>
  <!ELEMENT ngay_lap (#PCDATA)>
  
  <!ELEMENT chi_phi (ten, so_luong, don_gia, thanh_tien)>
  <!ELEMENT dich_vu (ten, so_luong, don_gia, thanh_tien)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT so_luong (#PCDATA)>
  <!ELEMENT don_gia (#PCDATA)>
  <!ELEMENT thanh_tien (#PCDATA)>
  
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thong_tin, (chi_phi | dich_vu)+, tong_tien)>
  <!ELEMENT thong_tin (so_hoa_don, benh_nhan, ngay_lap)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT benh_nhan (#PCDATA)>
  <!ELEMENT ngay_lap (#PCDATA)>
  <!ELEMENT chi_phi (ten, so_luong, don_gia, thanh_tien)>
  <!ELEMENT dich_vu (ten, so_luong, don_gia, thanh_tien)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT so_luong (#PCDATA)>
  <!ELEMENT don_gia (#PCDATA)>
  <!ELEMENT thanh_tien (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <thong_tin>
    <so_hoa_don>004</so_hoa_don>
    <benh_nhan>Phan Văn Sơn</benh_nhan>
    <ngay_lap>25/03/2024</ngay_lap>
  </thong_tin>
  <chi_phi>
    <ten>Khám tổng quát</ten>
    <so_luong>1</so_luong>
    <don_gia>200000</don_gia>
    <thanh_tien>200000</thanh_tien>
  </chi_phi>
  <chi_phi>
    <ten>Xét nghiệm máu</ten>
    <so_luong>1</so_luong>
    <don_gia>150000</don_gia>
    <thanh_tien>150000</thanh_tien>
  </chi_phi>
  <tong_tien>350000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 5: DTD VỚI EMPTY ELEMENT

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (info, dich_vu*, tong_tien)>
  <!ELEMENT info EMPTY>
  <!ATTLIST info 
    so CDATA #REQUIRED
    khach CDATA #REQUIRED
    ngay CDATA #REQUIRED>
  
  <!ELEMENT dich_vu EMPTY>
  <!ATTLIST dich_vu
    ten CDATA #REQUIRED
    so_luong CDATA #REQUIRED
    gia CDATA #REQUIRED
    tt CDATA #REQUIRED>
  
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (info, dich_vu*, tong_tien)>
  <!ELEMENT info EMPTY>
  <!ATTLIST info so CDATA #REQUIRED khach CDATA #REQUIRED ngay CDATA #REQUIRED>
  <!ELEMENT dich_vu EMPTY>
  <!ATTLIST dich_vu ten CDATA #REQUIRED so_luong CDATA #REQUIRED gia CDATA #REQUIRED tt CDATA #REQUIRED>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <info so="005" khach="Hồ Bảo Anh" ngay="28/03/2024"/>
  <dich_vu ten="Vận chuyển nội tp" so_luong="2" gia="100000" tt="200000"/>
  <dich_vu ten="Vận chuyển ngoài tp" so_luong="1" gia="500000" tt="500000"/>
  <dich_vu ten="Bảo hiểm hàng" so_luong="1" gia="150000" tt="150000"/>
  <tong_tien>850000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 6: DTD VỚI NAMESPACE

### DTD:
```dtd
<!DOCTYPE dv:hoa_don [
  <!ELEMENT dv:hoa_don (kh:thong_tin, dv:dich_vu+, dv:tong)>
  
  <!ELEMENT kh:thong_tin (kh:so_hoa_don, kh:ho_ten)>
  <!ELEMENT kh:so_hoa_don (#PCDATA)>
  <!ELEMENT kh:ho_ten (#PCDATA)>
  
  <!ELEMENT dv:dich_vu (dv:ten, dv:gia)>
  <!ELEMENT dv:ten (#PCDATA)>
  <!ELEMENT dv:gia (#PCDATA)>
  
  <!ELEMENT dv:tong (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE dv:hoa_don [
  <!ELEMENT dv:hoa_don (kh:thong_tin, dv:dich_vu+, dv:tong)>
  <!ELEMENT kh:thong_tin (kh:so_hoa_don, kh:ho_ten)>
  <!ELEMENT kh:so_hoa_don (#PCDATA)>
  <!ELEMENT kh:ho_ten (#PCDATA)>
  <!ELEMENT dv:dich_vu (dv:ten, dv:gia)>
  <!ELEMENT dv:ten (#PCDATA)>
  <!ELEMENT dv:gia (#PCDATA)>
  <!ELEMENT dv:tong (#PCDATA)>
]>
<dv:hoa_don xmlns:dv="http://dichvu.vn" xmlns:kh="http://khachhang.vn">
  <kh:thong_tin>
    <kh:so_hoa_don>006</kh:so_hoa_don>
    <kh:ho_ten>Võ Minh Tâm</kh:ho_ten>
  </kh:thong_tin>
  <dv:dich_vu>
    <dv:ten>Internet 100Mbps</dv:ten>
    <dv:gia>350000</dv:gia>
  </dv:dich_vu>
  <dv:dich_vu>
    <dv:ten>Điện thoại</dv:ten>
    <dv:gia>80000</dv:gia>
  </dv:dich_vu>
  <dv:tong>550000</dv:tong>
</dv:hoa_don>
```

---

## 📌 ĐỀ 7: DTD VỚI CARDINALITY (?, *, +)

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (so_hoa_don, khach_hang?, dia_chi*, item+, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT khach_hang (#PCDATA)>
  <!ELEMENT dia_chi (#PCDATA)>
  <!ELEMENT item (ten, sl, gia, tt)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT sl (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tt (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (so_hoa_don, khach_hang?, dia_chi*, item+, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT khach_hang (#PCDATA)>
  <!ELEMENT dia_chi (#PCDATA)>
  <!ELEMENT item (ten, sl, gia, tt)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT sl (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tt (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <so_hoa_don>007</so_hoa_don>
  <khach_hang>Tô Văn Cảnh</khach_hang>
  <dia_chi>Hà Nội</dia_chi>
  <dia_chi>Quốc lộ 1A</dia_chi>
  <item>
    <ten>Quãng đường 15km</ten>
    <sl>1</sl>
    <gia>180000</gia>
    <tt>180000</tt>
  </item>
  <item>
    <ten>Phí dịch vụ</ten>
    <sl>1</sl>
    <gia>20000</gia>
    <tt>20000</tt>
  </item>
  <tong_tien>200000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 8: DTD VỚI ID & IDREF

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (order+, summary)>
  <!ELEMENT order (item+)>
  <!ATTLIST order id ID #REQUIRED khach IDREF #REQUIRED>
  
  <!ELEMENT item (ten, qty, price, total)>
  <!ATTLIST item id ID #REQUIRED>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT qty (#PCDATA)>
  <!ELEMENT price (#PCDATA)>
  <!ELEMENT total (#PCDATA)>
  
  <!ELEMENT summary (grand_total)>
  <!ELEMENT grand_total (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (order+, summary)>
  <!ELEMENT order (item+)>
  <!ATTLIST order id ID #REQUIRED khach IDREF #REQUIRED>
  <!ELEMENT item (ten, qty, price, total)>
  <!ATTLIST item id ID #REQUIRED>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT qty (#PCDATA)>
  <!ELEMENT price (#PCDATA)>
  <!ELEMENT total (#PCDATA)>
  <!ELEMENT summary (grand_total)>
  <!ELEMENT grand_total (#PCDATA)>
]>
<hoa_don>
  <order id="O001" khach="C008">
    <item id="I001">
      <ten>Cơm chiên</ten>
      <qty>2</qty>
      <price>85000</price>
      <total>170000</total>
    </item>
    <item id="I002">
      <ten>Canh chua cá</ten>
      <qty>1</qty>
      <price>120000</price>
      <total>120000</total>
    </item>
  </order>
  <summary>
    <grand_total>290000</grand_total>
  </summary>
</hoa_don>
```

---

## 📌 ĐỀ 9: DTD VỚI NOTATION

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!NOTATION PNG SYSTEM "image/png">
  <!NOTATION PDF SYSTEM "application/pdf">
  
  <!ELEMENT hoa_don (so_hoa_don, dv+, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT dv (ten, gia)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!NOTATION PNG SYSTEM "image/png">
  <!NOTATION PDF SYSTEM "application/pdf">
  <!ELEMENT hoa_don (so_hoa_don, dv+, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT dv (ten, gia)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <so_hoa_don>009</so_hoa_don>
  <dv>
    <ten>Cắt tóc</ten>
    <gia>80000</gia>
  </dv>
  <dv>
    <ten>Gội đầu</ten>
    <gia>50000</gia>
  </dv>
  <tong_tien>130000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 10: DTD VỚI DEFAULT ATTRIBUTE

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thuoc+, tong)>
  <!ELEMENT thuoc (ten, sl, gia, tong_tt)>
  <!ATTLIST thuoc 
    id ID #REQUIRED
    trang_thai (con|het) "con"
    cap_do_uu_tien (cao|trung_binh|thap) #DEFAULT "trung_binh">
  
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT sl (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tong_tt (#PCDATA)>
  <!ELEMENT tong (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thuoc+, tong)>
  <!ELEMENT thuoc (ten, sl, gia, tong_tt)>
  <!ATTLIST thuoc id ID #REQUIRED trang_thai (con|het) "con" cap_do_uu_tien (cao|trung_binh|thap) #DEFAULT "trung_binh">
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT sl (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tong_tt (#PCDATA)>
  <!ELEMENT tong (#PCDATA)>
]>
<hoa_don>
  <thuoc id="T001" trang_thai="con" cap_do_uu_tien="cao">
    <ten>Aspirin 500mg</ten>
    <sl>2</sl>
    <gia>45000</gia>
    <tong_tt>90000</tong_tt>
  </thuoc>
  <thuoc id="T002" trang_thai="het">
    <ten>Vitamin C</ten>
    <sl>1</sl>
    <gia>120000</gia>
    <tong_tt>120000</tong_tt>
  </thuoc>
  <tong>210000</tong>
</hoa_don>
```

---

## 📌 ĐỀ 11: DTD VỚI ENTITY DECLARATION

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ENTITY company_name "Công ty ABC">
  <!ENTITY currency "VND">
  <!ENTITY contact_email "info@abc.com">
  
  <!ELEMENT hoa_don (so_hoa_don, sach+, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT sach (ten, sl, gia, tong_tt)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT sl (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tong_tt (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ENTITY company_name "Công ty ABC">
  <!ENTITY currency "VND">
  <!ENTITY contact_email "info@abc.com">
  <!ELEMENT hoa_don (so_hoa_don, sach+, tong_tien)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT sach (ten, sl, gia, tong_tt)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT sl (#PCDATA)>
  <!ELEMENT gia (#PCDATA)>
  <!ELEMENT tong_tt (#PCDATA)>
  <!ELEMENT tong_tien (#PCDATA)>
]>
<hoa_don>
  <so_hoa_don>011</so_hoa_don>
  <sach>
    <ten>Lập trình Python</ten>
    <sl>1</sl>
    <gia>250000</gia>
    <tong_tt>250000</tong_tt>
  </sach>
  <sach>
    <ten>SQL cơ bản</ten>
    <sl>2</sl>
    <gia>180000</gia>
    <tong_tt>360000</tong_tt>
  </sach>
  <tong_tien>610000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 12: DTD VỚI COMPLEX TYPE

### DTD:
```dtd
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thong_tin_chung, danh_sach_dich_vu, tong_cong)>
  
  <!ELEMENT thong_tin_chung (so_hoa_don, ngay_lap, khach_hang, nhan_vien?)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT ngay_lap (#PCDATA)>
  <!ELEMENT khach_hang (ten, phone, email?)>
  <!ELEMENT nhan_vien (ten, id)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT phone (#PCDATA)>
  <!ELEMENT email (#PCDATA)>
  <!ELEMENT id (#PCDATA)>
  
  <!ELEMENT danh_sach_dich_vu (dich_vu+)>
  <!ELEMENT dich_vu (ma_dv, ten_dv, so_luong, don_gia, thanh_tien)>
  <!ELEMENT ma_dv (#PCDATA)>
  <!ELEMENT ten_dv (#PCDATA)>
  <!ELEMENT so_luong (#PCDATA)>
  <!ELEMENT don_gia (#PCDATA)>
  <!ELEMENT thanh_tien (#PCDATA)>
  
  <!ELEMENT tong_cong (tien_hang, thue, tien_giam, tong_thanh_toan)>
  <!ELEMENT tien_hang (#PCDATA)>
  <!ELEMENT thue (#PCDATA)>
  <!ELEMENT tien_giam (#PCDATA)>
  <!ELEMENT tong_thanh_toan (#PCDATA)>
]>
```

### XML:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ELEMENT hoa_don (thong_tin_chung, danh_sach_dich_vu, tong_cong)>
  <!ELEMENT thong_tin_chung (so_hoa_don, ngay_lap, khach_hang, nhan_vien?)>
  <!ELEMENT so_hoa_don (#PCDATA)>
  <!ELEMENT ngay_lap (#PCDATA)>
  <!ELEMENT khach_hang (ten, phone, email?)>
  <!ELEMENT nhan_vien (ten, id)>
  <!ELEMENT ten (#PCDATA)>
  <!ELEMENT phone (#PCDATA)>
  <!ELEMENT email (#PCDATA)>
  <!ELEMENT id (#PCDATA)>
  <!ELEMENT danh_sach_dich_vu (dich_vu+)>
  <!ELEMENT dich_vu (ma_dv, ten_dv, so_luong, don_gia, thanh_tien)>
  <!ELEMENT ma_dv (#PCDATA)>
  <!ELEMENT ten_dv (#PCDATA)>
  <!ELEMENT so_luong (#PCDATA)>
  <!ELEMENT don_gia (#PCDATA)>
  <!ELEMENT thanh_tien (#PCDATA)>
  <!ELEMENT tong_cong (tien_hang, thue, tien_giam, tong_thanh_toan)>
  <!ELEMENT tien_hang (#PCDATA)>
  <!ELEMENT thue (#PCDATA)>
  <!ELEMENT tien_giam (#PCDATA)>
  <!ELEMENT tong_thanh_toan (#PCDATA)>
]>
<hoa_don>
  <thong_tin_chung>
    <so_hoa_don>012</so_
