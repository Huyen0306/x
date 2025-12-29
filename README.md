# 📋 20 ĐỀ HÓA ĐƠN - XML CẤU TRÚC ĐA DẠNG

> Mỗi đề dùng cách gõ XML khác nhau - từ đơn giản đến phức tạp

---

## 📌 ĐỀ 1: CẤU TRÚC ATTRIBUTE (Thuộc tính)

### Đề bài mẫu:
```
HÓA ĐƠN
Số: 001 | Khách: Trần Minh Hùng | Ngày: 15/03/2024
Phòng đơn (3 đêm) - 500.000 = 1.500.000
Ăn sáng (3 suất) - 150.000 = 450.000
Tổng: 1.950.000
```

### Giải - XML dùng ATTRIBUTE:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don so="001" khach="Trần Minh Hùng" ngay="15/03/2024">
  <dich_vu ten="Phòng đơn" so_luong="3" don_gia="500000" thanh_tien="1500000"/>
  <dich_vu ten="Ăn sáng" so_luong="3" don_gia="150000" thanh_tien="450000"/>
  <tong_tien>1950000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 2: CẤU TRÚC NESTED PHỨC TẠP

### Đề bài mẫu:
```
HÓA ĐƠN 002
Khách hàng: Lê Thị Huỳnh
Dịch vụ:
  - Điện: 150 kWh x 2.000 = 300.000
  - Nước: 20 m³ x 45.000 = 900.000
Tổng: 1.200.000
```

### Giải - XML lồng sâu:
```xml
<?xml version="1.0" encoding="UTF-8"?>
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

## 📌 ĐỀ 3: CẤU TRÚC CDATA (Dữ liệu lớn)

### Đề bài mẫu:
```
HÓA ĐƠN 003
Mô tả chi tiết: "Bộ quần áo gồm áo sơ mi, quần jean, giày thể thao..."
Chi phí: 1.300.000
```

### Giải - XML dùng CDATA:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so_hoa_don>003</so_hoa_don>
  <mo_ta><![CDATA[
    Bộ quần áo gồm:
    - Áo sơ mi: 2 cái x 250.000 = 500.000
    - Quần jean: 1 cái x 350.000 = 350.000
    - Giày thể thao: 1 đôi x 450.000 = 450.000
  ]]></mo_ta>
  <tong_tien>1300000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 4: CẤU TRÚC MIXED CONTENT (Hỗn hợp)

### Đề bài mẫu:
```
HÓA ĐƠN 004
Bệnh nhân Phan Văn Sơn chi trả:
- Khám: 200.000
- Xét nghiệm: 150.000
- Nằm viện: 2.400.000
```

### Giải - XML hỗn hợp text và tag:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <benh_nhan>
    Bệnh nhân <ten>Phan Văn Sơn</ten> chi trả:
    <chi_phi loai="Khám">200000</chi_phi>,
    <chi_phi loai="Xét nghiệm">150000</chi_phi>,
    <chi_phi loai="Nằm viện">2400000</chi_phi>
  </benh_nhan>
  <tong>2750000</tong>
</hoa_don>
```

---

## 📌 ĐỀ 5: CẤU TRÚC SELF-CLOSING (Tự đóng)

### Đề bài mẫu:
```
HÓA ĐƠN 005
Vận chuyển nội tp: 2 lần x 100.000 = 200.000
Vận chuyển ngoài tp: 1 lần x 500.000 = 500.000
```

### Giải - XML tự đóng tag:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <info so="005" khach="Hồ Bảo Anh" ngay="28/03/2024"/>
  <dich_vu ten="Vận chuyển nội tp" sl="2" gia="100000" tt="200000"/>
  <dich_vu ten="Vận chuyển ngoài tp" sl="1" gia="500000" tt="500000"/>
  <dich_vu ten="Bảo hiểm hàng" sl="1" gia="150000" tt="150000"/>
  <tong_tien>850000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 6: CẤU TRÚC NAMESPACE

### Đề bài mẫu:
```
HÓA ĐƠN 006
Internet: 350.000 | Điện thoại: 80.000 | Truyền hình: 120.000
Tổng: 550.000
```

### Giải - XML dùng Namespace:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don xmlns:dv="http://dichvu.vn" xmlns:kh="http://khachhang.vn">
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
  <dv:dich_vu>
    <dv:ten>Truyền hình</dv:ten>
    <dv:gia>120000</dv:gia>
  </dv:dich_vu>
  <tong>550000</tong>
</hoa_don>
```

---

## 📌 ĐỀ 7: CẤU TRÚC DANH SÁCH DÙNG TYPE

### Đề bài mẫu:
```
HÓA ĐƠN 007
[Quãng đường] 15 km x 12.000 = 180.000
[Chờ xe] 2 giờ x 5.000 = 10.000
[Phí] 1 lần x 10.000 = 10.000
```

### Giải - XML dùng type attribute:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so_hoa_don>007</so_hoa_don>
  <khach_hang>Tô Văn Cảnh</khach_hang>
  <item type="quang_duong" so="15" don_vi="km" gia="12000">180000</item>
  <item type="cho_xe" so="2" don_vi="gio" gia="5000">10000</item>
  <item type="phi_dich_vu" so="1" don_vi="lan" gia="10000">10000</item>
  <tong_tien>200000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 8: CẤU TRÚC MẢNG ARRAY

### Đề bài mẫu:
```
HÓA ĐƠN 008
Cơm chiên: 2 suất x 85.000 = 170.000
Canh chua cá: 1 tô x 120.000 = 120.000
Rau luộc: 1 đĩa x 60.000 = 60.000
```

### Giải - XML dạng array:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so_hoa_don>008</so_hoa_don>
  <thong_tin>
    <khach_hang>Đặng Huy Hoàng</khach_hang>
    <ngay_lap>08/04/2024</ngay_lap>
  </thong_tin>
  <order>
    <item id="1">
      <name>Cơm chiên</name>
      <qty>2</qty>
      <price>85000</price>
      <total>170000</total>
    </item>
    <item id="2">
      <name>Canh chua cá</name>
      <qty>1</qty>
      <price>120000</price>
      <total>120000</total>
    </item>
    <item id="3">
      <name>Rau luộc</name>
      <qty>1</qty>
      <price>60000</price>
      <total>60000</total>
    </item>
  </order>
  <summary>
    <grand_total>350000</grand_total>
  </summary>
</hoa_don>
```

---

## 📌 ĐỀ 9: CẤU TRÚC PHẲNG (FLAT)

### Đề bài mẫu:
```
HÓA ĐƠN 009
Cắt tóc: 80.000 | Gội đầu: 50.000 | Sấy: 40.000 | Chăm sóc: 100.000
```

### Giải - XML phẳng (không lồng):
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so>009</so>
  <ten_kh>Bùi Văn Thắng</ten_kh>
  <ngay>10/04/2024</ngay>
  <dv1_ten>Cắt tóc</dv1_ten>
  <dv1_gia>80000</dv1_gia>
  <dv2_ten>Gội đầu</dv2_ten>
  <dv2_gia>50000</dv2_gia>
  <dv3_ten>Sấy tóc</dv3_ten>
  <dv3_gia>40000</dv3_gia>
  <dv4_ten>Chăm sóc tóc</dv4_ten>
  <dv4_gia>100000</dv4_gia>
  <tong>270000</tong>
</hoa_don>
```

---

## 📌 ĐỀ 10: CẤU TRÚC JSON-LIKE (Định dạng JSON)

### Đề bài mẫu:
```
HÓA ĐƠN 010
{"medicines": [
  {"name": "Aspirin 500mg", "qty": 2, "price": 45000},
  {"name": "Vitamin C", "qty": 1, "price": 120000}
]}
```

### Giải - XML giống JSON:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <id>010</id>
  <customer>Phạm Thị Loan</customer>
  <medicines>
    <medicine id="1" name="Aspirin 500mg" qty="2" price="45000" total="90000"/>
    <medicine id="2" name="Vitamin C" qty="1" price="120000" total="120000"/>
    <medicine id="3" name="Kháng sinh" qty="1" price="200000" total="200000"/>
    <medicine id="4" name="Kem mỡ" qty="1" price="85000" total="85000"/>
  </medicines>
  <total>495000</total>
</hoa_don>
```

---

## 📌 ĐỀ 11: CẤU TRÚC COMMENT VÀ PROCESSING INSTRUCTION

### Đề bài mẫu:
```
HÓA ĐƠN 011
Sách lập trình: 250.000 (Hàng mới)
SQL cơ bản: 180.000 x 2 (Hàng cũ)
```

### Giải - XML với comment:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml-stylesheet type="text/xsl" href="invoice.xsl"?>
<hoa_don>
  <!-- Thông tin hóa đơn -->
  <so_hoa_don>011</so_hoa_don>
  <khach_hang>Lương Hồng Sơn</khach_hang>
  
  <!-- Danh sách sách -->
  <sach>
    <ten>Lập trình Python</ten>
    <so_luong>1</so_luong>
    <gia>250000</gia>
    <!-- Sách mới - giảm 5% -->
    <ghi_chu>Hàng mới</ghi_chu>
  </sach>
  
  <sach>
    <ten>SQL cơ bản</ten>
    <so_luong>2</so_luong>
    <gia>180000</gia>
    <!-- Sách cũ - không giảm giá -->
    <ghi_chu>Hàng cũ</ghi_chu>
  </sach>
  
  <tong_tien>610000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 12: CẤU TRÚC ENTITY REFERENCES

### Đề bài mẫu:
```
HÓA ĐƠN 012
Thiết kế: & (ampersand) hay &amp;
Giá: 1.000.000 đ < 2.000.000
```

### Giải - XML dùng Entity:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hoa_don [
  <!ENTITY company "Công ty ABC &amp; Co.">
  <!ENTITY currency "VND">
]>
<hoa_don>
  <so_hoa_don>012</so_hoa_don>
  <cong_ty>&company;</cong_ty>
  <khach_hang>Tạ Văn Nam</khach_hang>
  <dich_vu>
    <ten>Thiết kế logo</ten>
    <gia currency="&currency;">1000000</gia>
  </dich_vu>
  <dich_vu>
    <ten>Chỉnh sửa ảnh</ten>
    <gia>&lt;= 600000</gia>
  </dich_vu>
  <tong_tien>1600000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 13: CẤU TRÚC VỚI METADATA

### Đề bài mẫu:
```
HÓA ĐƠN 013 (Version 2.1, Created 2024-04-20)
Tập gym: 10 buổi x 50.000 = 500.000
Yoga: 8 buổi x 80.000 = 640.000
```

### Giải - XML với metadata:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don version="2.1" created="2024-04-20" updated="2024-04-21">
  <meta>
    <type>INVOICE</type>
    <status>COMPLETED</status>
    <language>vi-VN</language>
  </meta>
  <header>
    <hoa_don_id>013</hoa_don_id>
    <khach_hang>Đinh Quang Huy</khach_hang>
    <ngay_lap>20/04/2024</ngay_lap>
  </header>
  <chi_tiet>
    <goi_tap ten="Tập free" buoi="10" gia="50000" tt="500000"/>
    <goi_tap ten="Yoga" buoi="8" gia="80000" tt="640000"/>
    <goi_tap ten="PT riêng" buoi="5" gia="200000" tt="1000000"/>
  </chi_tiet>
  <footer>
    <tong>2140000</tong>
    <thue>10%</thue>
    <total_final>2354000</total_final>
  </footer>
</hoa_don>
```

---

## 📌 ĐỀ 14: CẤU TRÚC RECURSIVE (Lặp lại)

### Đề bài mẫu:
```
HÓA ĐƠN 014
Khoá 1:
  - Tháng 1: 500.000
  - Tháng 2: 500.000
  - Tháng 3: 500.000
```

### Giải - XML đệ quy:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so>014</so>
  <hoc_sinh>Dương Minh Hải</hoc_sinh>
  <khoa>
    <so_khoa>1</so_khoa>
    <tien_hoc>
      <thang so="1" gia="500000"/>
      <thang so="2" gia="500000"/>
      <thang so="3" gia="500000"/>
    </tien_hoc>
    <sach>
      <mon>Toán</mon>
      <cuon>2</cuon>
      <gia>150000</gia>
    </sach>
  </khoa>
  <tong>2050000</tong>
</hoa_don>
```

---

## 📌 ĐỀ 15: CẤU TRÚC MAP/DICTIONARY

### Đề bài mẫu:
```
HÓA ĐƠN 015
Bảo dưỡng: 300.000
Thay dầu: 150.000
Sửa lốp: 200.000
```

### Giải - XML dạng Map:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so_hoa_don>015</so_hoa_don>
  <khach_hang>
    <entry key="ho_ten">Trương Văn Toàn</entry>
    <entry key="xe">Honda Wave</entry>
    <entry key="bien_so">51-A1234</entry>
  </khach_hang>
  <chi_phi>
    <entry key="bao_duong">300000</entry>
    <entry key="thay_dau">150000</entry>
    <entry key="sua_lop">200000</entry>
    <entry key="rua_xe">80000</entry>
  </chi_phi>
  <summary>
    <entry key="tong">730000</entry>
    <entry key="vat">73000</entry>
    <entry key="total">803000</entry>
  </summary>
</hoa_don>
```

---

## 📌 ĐỀ 16: CẤU TRÚC LINKED (Liên kết)

### Đề bài mẫu:
```
HÓA ĐƠN 016
Salon: ID 016
Khách: Nguyễn Thị Hương (CustID: C025)
Nhuộm tóc: 300.000
```

### Giải - XML với ID reference:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don id="016">
  <salon_id>S001</salon_id>
  <khach_hang id="C025">
    <ten>Nguyễn Thị Hương</ten>
    <phone>0987654321</phone>
  </khach_hang>
  <chi_tiet>
    <dv_id>DV001</dv_id>
    <ten>Nhuộm tóc</ten>
    <gia>300000</gia>
    <nhan_vien_id>NV015</nhan_vien_id>
  </chi_tiet>
  <chi_tiet>
    <dv_id>DV002</dv_id>
    <ten>Uốn tóc</ten>
    <gia>250000</gia>
    <nhan_vien_id>NV015</nhan_vien_id>
  </chi_tiet>
  <tong>550000</tong>
</hoa_don>
```

---

## 📌 ĐỀ 17: CẤU TRÚC HIERARCHICAL (Phân cấp)

### Đề bài mẫu:
```
HÓA ĐƠN 017
Tầng 1:
  - Sửa cầu thang: 500.000
Tầng 2:
  - Sơn phòng khách: 400.000
  - Sơn phòng ngủ: 400.000
```

### Giải - XML phân cấp:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so>017</so>
  <cong_trinh>
    <tang level="1" ten="Tầng 1">
      <job ten="Sửa cầu thang" gia="500000"/>
    </tang>
    <tang level="2" ten="Tầng 2">
      <job ten="Sơn phòng khách" gia="400000"/>
      <job ten="Sơn phòng ngủ" gia="400000"/>
    </tang>
    <tang level="3" ten="Tầng 3">
      <job ten="Thay mạch điện" gia="600000"/>
    </tang>
  </cong_trinh>
  <tong_tien>1900000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 18: CẤU TRÚC TUPLE/RECORD

### Đề bài mẫu:
```
HÓA ĐƠN 018
[ID,Sản phẩm,Số lượng,Giá,Thành tiền]
[1,Laptop Dell,1,15000000,15000000]
[2,Chuột,2,150000,300000]
```

### Giải - XML dạng tuple:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so_hoa_don>018</so_hoa_don>
  <khach_hang>Trương Văn Hùng</khach_hang>
  <record>
    <field name="id">1</field>
    <field name="san_pham">Laptop Dell</field>
    <field name="so_luong">1</field>
    <field name="gia">15000000</field>
    <field name="thanh_tien">15000000</field>
  </record>
  <record>
    <field name="id">2</field>
    <field name="san_pham">Chuột không dây</field>
    <field name="so_luong">2</field>
    <field name="gia">150000</field>
    <field name="thanh_tien">300000</field>
  </record>
  <record>
    <field name="id">3</field>
    <field name="san_pham">Bàn phím cơ</field>
    <field name="so_luong">1</field>
    <field name="gia">800000</field>
    <field name="thanh_tien">800000</field>
  </record>
  <tong_tien>16100000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 19: CẤU TRÚC ENUMERATION

### Đề bài mẫu:
```
HÓA ĐƠN 019
Trạng thái: Đã thanh toán
T-shirt: 3 cái = 360.000 (Còn hàng)
Quần tây: 2 cái = 800.000 (Hết hàng)
```

### Giải - XML dùng enum:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don status="PAID">
  <so_hoa_don>019</so_hoa_don>
  <khach_hang>Bùi Hải Dương</khach_hang>
  <san_pham>
    <item>
      <ten>T-shirt nam</ten>
      <so_luong>3</so_luong>
      <gia>120000</gia>
      <thanh_tien>360000</thanh_tien>
      <tinh_trang>AVAILABLE</tinh_trang>
    </item>
    <item>
      <ten>Quần tây</ten>
      <so_luong>2</so_luong>
      <gia>400000</gia>
      <thanh_tien>800000</thanh_tien>
      <tinh_trang>OUT_OF_STOCK</tinh_trang>
    </item>
    <item>
      <ten>Áo khoác</ten>
      <so_luong>1</so_luong>
      <gia>600000</gia>
      <thanh_tien>600000</thanh_tien>
      <tinh_trang>AVAILABLE</tinh_trang>
    </item>
  </san_pham>
  <tong_tien>1760000</tong_tien>
</hoa_don>
```

---

## 📌 ĐỀ 20: CẤU TRÚC GRAPH (Đồ thị - Liên kết phức tạp)

### Đề bài mẫu:
```
HÓA ĐƠN 020
Cà phê đen (2 ly) -> Barista: A001 -> Quán: Q001
Cà phê sữa (3 ly) -> Barista: A002 -> Quán: Q001
```

### Giải - XML dạng graph:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<hoa_don>
  <so_hoa_don>020</so_hoa_don>
  <quan_cafe id="Q001">
    <ten>Café Anh Sáng</ten>
    <dia_chi>123 Nguyễn Huệ</dia_chi>
  </quan_cafe>
  <nhan_vien id="A001">
    <ten>Trần Minh Anh</ten>
    <vi_tri>Barista</vi_tri>
    <quan_id>Q001</quan_id>
