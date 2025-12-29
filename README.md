# 📚 XML/XPath Q&A Cheat Sheet

> Ghi nhớ nhanh - Không giải thích dài dòng

---

## ⚙️ XPath Selectors

### #1 - Chọn tất cả các node có tên cụ thể
```xpath
//tagname
```
**VD:** `//book`

---

### #2 - Chọn node từ root
```xpath
/root/child
```
**VD:** `/bookstore/book`

---

### #3 - Chọn node cha của node hiện tại
```xpath
../
```
**VD:** `../parent`

---

### #4 - Chọn các attribute của node
```xpath
@attributename
```
**VD:** `//book[@lang]`

---

### #5 - Chọn theo giá trị attribute
```xpath
//tag[@attr='value']
```
**VD:** `//book[@lang='en']`

---

### #6 - Chọn node thứ n
```xpath
//tag[position()=n]
```
**VD:** `//book[1]` (thứ 1)

---

### #7 - Chọn node cuối cùng
```xpath
//tag[last()]
```
**VD:** `//book[last()]`

---

### #8 - Chọn node có text cụ thể
```xpath
//tag[text()='value']
```
**VD:** `//title[text()='Harry']`

---

### #9 - Chọn node chứa text
```xpath
//tag[contains(text(),'substring')]
```
**VD:** `//title[contains(text(),'Harry')]`

---

### #10 - Chọn node với nhiều điều kiện (AND)
```xpath
//tag[@attr1='v1' and @attr2='v2']
```
**VD:** `//book[@lang='en' and @year='2005']`

---

### #11 - Chọn node với OR
```xpath
//tag[@attr='v1' or @attr='v2']
```
**VD:** `//book[@lang='en' or @lang='fr']`

---

### #12 - Chọn node con trực tiếp
```xpath
./child
```
**VD:** `./title`

---

### #13 - Chọn tất cả node con (mọi mức)
```xpath
.//tag
./*
```
**VD:** `.//title`

---

### #14 - Chọn node với attribute không tồn tại
```xpath
//tag[not(@attr)]
```
**VD:** `//book[not(@lang)]`

---

### #15 - Chọn theo phép so sánh
```xpath
//tag[@attr > value]
```
**VD:** `//book[@year > 2005]`

---

## 📄 XML Structure

### #16 - Cấu trúc cơ bản XML
```xml
<?xml version='1.0'?>
<root>
  <element>text</element>
</root>
```

---

### #17 - Attribute trong XML
```xml
<element attr='value'>content</element>
```

---

### #18 - Comment trong XML
```xml
<!-- This is a comment -->
```

---

## 🔧 Syntax Operators

### #19 - Toán tử OR (Union)
```xpath
|
```
**VD:** `//book | //magazine` (chọn cả book và magazine)

---

### #20 - Wildcard
```xpath
*
```
**VD:** `//*` (chọn tất cả node), `/book/*` (tất cả con của book)

---

## 📋 Quick Reference Table

| Ký hiệu | Ý nghĩa |
|---------|---------|
| `/` | Từ root node |
| `//` | Bất kỳ vị trí nào |
| `.` | Node hiện tại |
| `..` | Node cha |
| `@` | Attribute |
| `[1]` | Node đầu tiên |
| `[last()]` | Node cuối cùng |
| `*` | Wildcard - tất cả |
| `\|` | Union (OR) |
| `and` | Và (AND logic) |
| `or` | Hoặc (OR logic) |
| `not()` | Phủ định |

---

## 🎯 Common Patterns

```xpath
# Tất cả book
//book

# Book với lang='en'
//book[@lang='en']

# Book thứ 2
//book[2]

# Tất cả con của book
//book/*

# Title bên trong book
//book/title

# Tất cả title ở mọi vị trí
//title

# Book có attribute lang
//book[@lang]

# Book không có attribute lang
//book[not(@lang)]

# Book có price > 10
//book[price > 10]

# Book và magazine
//book | //magazine
```

---

**💡 Mẹo:** Luôn dùng `//` khi không chắc vị trí, dùng `/` khi biết đường dẫn rõ ràng.
