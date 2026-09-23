# บทวิเคราะห์และถอดความการบรรยายปฏิบัติการวิชา Database System
## ปฏิบัติการ DDL & DML, การจัดการความคงสภาพตาราง (Constraints), และการแก้ไขข้อผิดพลาด MariaDB ERROR 1074

- **วันที่บรรยาย:** วันอังคารที่ 22 กันยายน 2569
- **เวลา:** 13:10:58 - 15:49:00 (ความยาวรวม: ~2 ชั่วโมง 38 นาที)
- **ผู้สอน:** อาจารย์ผู้สอนปฏิบัติการวิชาฐานข้อมูล (ดร.สวาท / Dr. Sawat)
- **ไฟล์เสียงต้นฉบับ:** `20260922_131058.aac` & `20260922_150154.aac`
- **ไฟล์ Transcript ฉบับเต็ม:** [20260922_131058.txt](file:///C:/Project/Voice/02_Database_System/20260922_131058.txt)
- **โครงการปลายทาง:** `C:\Project\database-system\`
- **ภาพถ่ายประกอบ:**
  - `IMG_20260922_124841_660@1996423590.jpg` (โครงสร้างตาราง `tutorials.users` ใน phpMyAdmin)
  - `IMG_20260922_142452_298@-1416416793.jpg` (ข้อผิดพลาด MariaDB `ERROR 1074 (42000)`: Column length too big max=255)
  - `IMG_20260922_142503_490@2024331400.jpg` (หน้าจอคำสั่ง MariaDB CLI DDL `ALTER TABLE`)

---

## 1. จุดเน้นและข้อผิดพลาดสำคัญในข้อสอบแล็บ (Lab Exam Highlights & Traps)

### 1.1 กับดักข้อสอบ: ความแตกต่างระหว่าง `CHAR` และ `VARCHAR` (ERROR 1074)
> [!CAUTION]
> **ข้อผิดพลาดที่เกิดขึ้นจริงในคาบเรียน (ดูภาพ `IMG_20260922_142452`):**
> เมื่อนักศึกษาพิมพ์คำสั่ง:
> ```sql
> ALTER TABLE Title MODIFY COLUMN TitleDescription CHAR(500);
> ```
> ระบบ MariaDB จะแจ้ง Error ทันที:
> ```text
> ERROR 1074 (42000): Column length too big for column 'TitleDescription' (max = 255); use BLOB or TEXT instead
> ```
> **คำอธิบายทางเทคนิค:**
> - ชนิดข้อมูล `CHAR` เป็น **Fixed-Length String** มีข้อจำกัดสูงสุดใน MariaDB/MySQL ที่ **255 ตัวอักษร**
> - หากต้องการเก็บข้อความที่มีขนาดยาวกว่า 255 ตัวอักษร (เช่น 500 ตัวอักษร) จะต้องใช้ `VARCHAR(500)` (Variable-Length String) หรือ `TEXT` / `BLOB`
> - คำสั่งแก้ไขที่ถูกต้อง:
>   ```sql
>   -- กรณีใช้ VARCHAR:
>   ALTER TABLE Title MODIFY COLUMN TitleDescription VARCHAR(500);
>   -- หรือปรับลดขนาดให้พอดีกับ CHAR(255):
>   ALTER TABLE Title MODIFY COLUMN TitleDescription CHAR(255);
>   ```

---

### 1.2 กฎความคงสภาพของการอ้างอิง (Referential Integrity Constraints)
```sql
CONSTRAINT fk_orders_customer FOREIGN KEY (CustomerID) 
    REFERENCES Customer(CustomerID)
    ON DELETE CASCADE 
    ON UPDATE CASCADE;
```
- **ON DELETE CASCADE:** เมื่อข้อมูลลูกค้าในตารางแม่ (`Customer`) ถูกลบ ข้อมูลการสั่งซื้อของลูกค้ารายนั้นในตารางลูก (`Orders`) จะถูกลบตามไปด้วยโดยอัตโนมัติ เพื่อป้องกันการเกิดข้อมูลกำพร้า (Orphan Records)
- **ON UPDATE CASCADE:** เมื่อรหัสลูกค้ามีการเปลี่ยนแปลงในตารางแม่ รหัสในตารางลูกจะได้รับการอัปเดตให้ตรงกันทันที

---

### 1.3 การจัดการ Character Set รองรับภาษาไทยและ Emoji
- **คำสั่งสร้างฐานข้อมูลที่ถูกต้อง:**
  ```sql
  CREATE DATABASE my_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
  ```
- **เหตุผลทางเทคนิค:**
  - `utf8mb4` ใช้พื้นที่จัดเก็บ 1 ตัวอักษรได้สูงสุด **4 ไบต์**
  - รองรับภาษาไทยทุกสระ วรรณยุกต์ และสัญลักษณ์ Emoji สมัยใหม่
  - ป้องกันปัญหาตัวอักษรกลายเป็นเครื่องหมายคำถาม (`?`) หรือภาษาต่างดาวเมื่อบันทึกผ่าน CLI/Web Form

---

## 2. ขั้นตอนการปฏิบัติการ XAMPP MariaDB CLI Step-by-Step

### 2.1 การเปิดใช้งาน Service ผ่าน CMD
```bat
cd C:\xampp
xampp_start.exe
cd C:\xampp\mysql\bin
mysql.exe -u root
```

### 2.2 โค้ดคำสั่ง DDL สร้างฐานข้อมูลและตารางจำลองระบบ
```sql
-- 1. สร้างฐานข้อมูลพร้อม Character Set
CREATE DATABASE IF NOT EXISTS store_db 
CHARACTER SET utf8mb4 
COLLATE utf8mb4_unicode_ci;

USE store_db;

-- 2. สร้างตารางคำนำหน้าชื่อ (Parent 1)
CREATE TABLE Title (
    TitleID VARCHAR(4) NOT NULL,
    TitleName VARCHAR(50) NOT NULL,
    PRIMARY KEY (TitleID)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- 3. สร้างตารางลูกค้า (Parent 2 / Child of Title)
CREATE TABLE Customer (
    CustomerID INT AUTO_INCREMENT,
    CustomerName VARCHAR(100) NOT NULL,
    Telephone VARCHAR(20),
    TitleID VARCHAR(4),
    PRIMARY KEY (CustomerID),
    CONSTRAINT fk_customer_title FOREIGN KEY (TitleID) 
        REFERENCES Title(TitleID) 
        ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- 4. สร้างตารางคำสั่งซื้อ (Child of Customer)
CREATE TABLE Orders (
    OrderID INT AUTO_INCREMENT,
    OrderDate DATE NOT NULL,
    CustomerID INT NOT NULL,
    TotalAmount DECIMAL(10, 2) DEFAULT 0.00,
    PRIMARY KEY (OrderID),
    CONSTRAINT fk_orders_customer FOREIGN KEY (CustomerID) 
        REFERENCES Customer(CustomerID) 
        ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- 5. สร้าง Index เพื่อเพิ่มความเร็วในการสืบค้นเบอร์โทรศัพท์
CREATE INDEX idx_customer_tel ON Customer(Telephone);
```

---

## 3. ตารางเปรียบเทียบคำสั่ง DDL vs. DML

| หมวดหมู่ | คำสั่ง | หน้าที่และลักษณะการทำงาน | ผลกระทบต่อ Transaction |
| :--- | :--- | :--- | :--- |
| **DDL** | `CREATE` | สร้าง Database, Table, Index | Auto-commit ทันที ไม่สามารถ Rollback ได้ |
| **DDL** | `ALTER` | เพิ่ม ลบ หรือแก้ไขคอลัมน์และ Constraints | Auto-commit ทันที |
| **DDL** | `DROP` | ลบทิ้งโครงสร้างและข้อมูลทั้งหมด | Auto-commit ทันที |
| **DDL** | `TRUNCATE` | ล้างข้อมูลในตารางและรีเซ็ต `AUTO_INCREMENT` | Auto-commit ทำงานเร็วกว่า DELETE |
| **DML** | `INSERT` | เพิ่มแถวข้อมูลใหม่เข้าตาราง | สามารถ Rollback ได้ |
| **DML** | `UPDATE` | แก้ไขข้อมูลในแถวที่มีอยู่ตามเงื่อนไข `WHERE` | สามารถ Rollback ได้ |
| **DML** | `DELETE` | ลบแถวข้อมูลทีละแถวตามเงื่อนไข `WHERE` | สามารถ Rollback ได้ |
| **DML** | `SELECT` | ดึงข้อมูลออกมาแสดงผลตามเงื่อนไข | ไม่มีผลต่อการเปลี่ยนแปลงข้อมูล |
