# สรุปภาพรวม: วิชาระบบฐานข้อมูล (Database System)
**กลุ่มโฟลเดอร์:** `02_Database_System`  
**วิชา:** ระบบฐานข้อมูล (Database System / Database Management Systems)  
**หัวข้อการสอนหลัก:** 
1. **Transaction Management & ACID Properties**
2. **Concurrency Control & Lock-based Concurrency Matrix (S/X Lock)**
3. **System Recovery & Crash Handling (Soft Crash vs Hard Crash / Log File Undo-Redo)**
4. **การสอบเก็บคะแนนในห้องเรียน (Pop Quiz ในชั่วโมงเรียน)**
5. **NoSQL Databases vs RDBMS, Big Data Architecture & CAP Theorem**
6. **การนัดหมายเรียนภาคปฏิบัติการ Lab 2 สัปดาห์ และแนวข้อสอบปลายภาค 40 คะแนน**

---

## 📋 รายการไฟล์เสียงในกลุ่มนี้

| ชื่อไฟล์ | วันที่-เวลาที่บันทึก | ความยาว | สาระสำคัญ / กิจกรรมในชั้นเรียน |
| :--- | :--- | :--- | :--- |
| [`20260908_130406.aac`](file:///C:/Project/Voice/Success/20260908_130406.aac) | 08/09/2569 13:04 น. | 6 นาที 21 วินาที | **Part 1:** ชนิดของไฟล์ข้อมูล (Master File, Transaction File), นิยามของ Transaction, คำสั่ง INSERT / UPDATE / DELETE / QUERY, ตัวอย่างธุรกรรมการโอนเงิน |
| [`20260908_131052.aac`](file:///C:/Project/Voice/Success/20260908_131052.aac) | 08/09/2569 13:10 น. | 67 นาที 08 วินาที | **Part 2 (การบรรยายหลัก):** เจาะลึก Transaction Lifecycle, ACID Properties, ปัญหาเมื่อทำงานพร้อมกัน (Lost Update, Dirty Read, Inconsistent Analysis), ตาราง Lock Matrix (Shared Lock `S` vs Exclusive Lock `X`), Two-Phase Locking (2PL), Deadlock, และ System Failure Recovery |
| [`20260908_143913.aac`](file:///C:/Project/Voice/Success/20260908_143913.aac) | 08/09/2569 14:39 น. | 17 นาที 15 วินาที | **Part 3 (สอบเก็บคะแนน Pop Quiz):** อาจารย์สั่งสอบเก็บคะแนนกระทันหัน 2 ข้อ ให้เวลาข้อละ 5 นาที เขียนลงกระดาษ A4 แบ่งครึ่งหน้า-หลัง (ข้อ 1 ACID, ข้อ 2 Lock Matrix & 5 Transactions Crash Recovery) |
| [`-.aac`](file:///C:/Project/Voice/Success/-.aac) | 08/09/2569 14:39 น. | 17 นาที 15 วินาที | *ไฟล์สำเนา (Duplicate)* ขนาดและเนื้อหาตรงกับ `20260908_143913.aac` ทุกประการ |
| [`20260915_130022.aac`](file:///C:/Project/Voice/Success/20260915_130022.aac) | 15/09/2569 13:00 น. | 67 นาที 51 วินาที | **Part 4 (การบรรยาย NoSQL & CAP Theorem):** ข้อจำกัดของ RDBMS บนระบบกระจาย (Join expensive, Hard to scale, Impedance mismatch), ลักษณะ Big Data (5 Vs), โมเดล NoSQL 4 ชนิด (Key-Value, Column Family, Graph, Document-based), CAP Theorem (Brewer's Theorem: CA vs CP vs AP), สั่งส่งงาน ER Diagram ใน Classroom, ประกาศเรียน Lab 2 สัปดาห์ และแนวข้อสอบปลายภาค 40 คะแนน |
| [`20260922_131058.aac`](file:///C:/Project/Voice/Success/20260922_131058.aac) | 22/09/2569 13:10 น. | 81 นาที 15 วินาที | **Part 5 (ปฏิบัติการแล็บ DDL & MariaDB CLI):** การติดตั้งและเปิด XAMPP MariaDB CLI, การตั้ง Character Set `utf8mb4_unicode_ci`, สร้างตาราง Customer/Order/Product, การกำหนด Primary Key, Foreign Key และ Constraint `ON DELETE CASCADE` |
| [`20260922_150154.aac`](file:///C:/Project/Voice/Success/20260922_150154.aac) | 22/09/2569 15:01 น. | 45 นาที 48 วินาที | **Part 6 (แล็บ DML & จุดตาย ERROR 1074):** ปัญหาคำสั่ง `ALTER TABLE Title MODIFY COLUMN TitleDescription CHAR(500);` ล้มเหลวเพราะ `CHAR` รองรับความยาวสูงสุดเพียง 255 ต้องแก้เป็น `VARCHAR(500)` พร้อมเทคนิคการสืบค้น `SELECT` และแก้ปัญหาภาษาไทยกลายเป็น `?` |

---

## 🎯 จุดสำคัญที่อาจารย์เน้นย้ำ (Core Lecture Concepts)

### 1. นิยาม Transaction & ACID Properties
- **Transaction:** หน่วยการทำงานเชิงตรรกะที่กระทำต่อฐานข้อมูล (Insert, Update, Delete, Query) ต้องสำเร็จทั้งหมดหรือล้มเหลวทั้งหมด (All or Nothing)
- **ACID Properties:**
  - **Atomicity:** ทำทั้งหมดหรือไม่ทำเลย (Rollback หากผิดพลาด)
  - **Consistency:** ข้อมูลเปลี่ยนจากสถานะถูกต้องหนึ่งไปยังอีกสถานะที่ถูกต้องหนึ่งตามเงื่อนไข
  - **Isolation:** Transaction ที่ทำพร้อมกันไม่ก้าวก่ายกัน
  - **Durability:** บันทึกถาวรลง Disk เมื่อ Commit สำเร็จ

### 2. Concurrency Control & Lock Compatibility Matrix
- **Shared Lock (S):** สำหรับอ่าน (Read-only) สามารถแชร์กันอ่านได้
- **Exclusive Lock (X):** สำหรับแก้ไข (Write/Read) ถือครองได้เพียง Transaction เดียว
- **กฎ:** มีกรณีเดียวที่ได้ **Yes** คือ `(S, S)` นอกนั้น `(S, X)`, `(X, S)`, `(X, X)` ตอบ **No** ทั้งหมด

### 3. การกู้คืนระบบ (Crash Recovery & Log File)
- **Soft Crash:** ตรวจสอบจาก Log File
  - Transaction ที่มีบันทึก `COMMIT` $\rightarrow$ สั่ง **REDO**
  - Transaction ที่มี `START` แต่ยังไม่มี `COMMIT` $\rightarrow$ สั่ง **UNDO / ROLLBACK**

### 4. สถาปัตยกรรม NoSQL และ Big Data
- **NoSQL ("Not Only SQL"):** ออกแบบเพื่อระบบกระจายศูนย์ (Distributed) ที่ต้องการ Scale-out ในแนวนอน
- **NoSQL Data Models 4 ชนิด:**
  1. **Key-Value Store:** (DynamoDB, Redis) ค้นหาด้วย Key รวดเร็ว จัดเก็บข้อมูลทั้งก้อน
  2. **Column Family:** (Cassandra, HBase) เขียนข้อมูลแบบ Append ต่อท้ายพร้อม Timestamp เขียนเร็วมาก (0.12ms)
  3. **Graph Database:** (Neo4j) เหมาะกับความสัมพันธ์ที่ซับซ้อน เช่น Social Network, การแกะรอยโรคระบาด, เส้นทาง
  4. **Document Store:** (MongoDB, CouchDB) เก็บในรูปแบบ JSON/BSON ฝัง Nested Document และ Array ได้
- **CAP Theorem (Brewer's Theorem):** ระบบกระจายศูนย์เลือกรับประกันได้มากสุด 2 จาก 3 คุณสมบัติ
  - **CA:** RDBMS ดั้งเดิม (เน้นความถูกต้องและพร้อมใช้งานบน Server เดี่ยว)
  - **CP:** MongoDB, HBase (เน้นความถูกต้องของข้อมูลข้ามเครือข่าย)
  - **AP:** Cassandra, CouchDB, DynamoDB (เน้นความพร้อมใช้งานตลอดเวลาแบบ Eventual Consistency)

---

## 📅 กำหนดการและนัดหมายสำคัญ (Schedule & Deadlines)

| กิจกรรม / กำหนดการ | วันที่-เวลา | รายละเอียด |
| :--- | :--- | :--- |
| **ส่งงานกลุ่ม ER Diagram** | สัปดาห์นี้ | อัปโหลดไฟล์ภาพ ER Diagram ของกลุ่มเข้าสู่ **Google Classroom** |
| **เรียนภาคปฏิบัติการ Lab** | เริ่มวันอังคารหน้า (2 สัปดาห์ติดต่อกัน) | **งดเรียนห้องบรรยายนี้ 2 สัปดาห์** ให้ไปเรียนที่ห้องปฏิบัติการคอมพิวเตอร์ตามรอบที่ลงชื่อไว้ใน Google Sheets / Worksheet เพื่อเริ่มลงมือสร้าง Database จริง |

---

## 📝 แนวข้อสอบปลายภาค (Final Exam Secrets)

- **สัดส่วนคะแนน:** ข้อสอบปลายภาคเก็บ **40 คะแนนเต็ม** (คะแนนสำคัญที่สุดของวิชา)
- **เวลาสอบ:** **3 ชั่วโมงเต็ม** (ห้ามออกจากห้องสอบก่อน 1 ชั่วโมงแรก)
- **แนวข้อสอบ:**
  - ข้อสอบแนวสถานการณ์ ให้วิเคราะห์และเลือกว่าระบบงานใดควรใช้ RDBMS หรือ NoSQL โมเดลใด
  - การวิเคราะห์ทฤษฎีบท **CAP Theorem** (จำแนก CA, CP, AP)
  - คุณสมบัติ **ACID Properties** และตาราง **Lock Compatibility Matrix (S/X)**
  - การอ่าน Log File เพื่อสั่ง **REDO / UNDO** หลังเซิร์ฟเวอร์ล่ม

---

## 📂 เอกสารและไฟล์ที่เกี่ยวข้อง
- [**คำถอดความ 08/09/2569 Part 1 (`20260908_130406.txt`)**](file:///C:/Project/Voice/02_Database_System/20260908_130406.txt)
- [**คำถอดความ 08/09/2569 Part 2 (`20260908_131052.txt`)**](file:///C:/Project/Voice/02_Database_System/20260908_131052.txt)
- [**คำถอดความ 08/09/2569 Part 3 (`20260908_143913.txt`)**](file:///C:/Project/Voice/02_Database_System/20260908_143913.txt)
- [**คำถอดความ 15/09/2569 Part 4 (`20260915_130022.txt`)**](file:///C:/Project/Voice/02_Database_System/20260915_130022.txt)
- [**บทวิเคราะห์ NoSQL, Big Data & CAP Theorem (`Transcript_20260915_130022_NoSQL_BigData_CAP.md`)**](file:///C:/Project/Voice/02_Database_System/Transcript_20260915_130022_NoSQL_BigData_CAP.md)
- [**คำถอดความ 22/09/2569 Part 5-6 (`20260922_131058.txt`)**](file:///C:/Project/Voice/02_Database_System/20260922_131058.txt)
- [**บทวิเคราะห์เจาะลึก Lab DDL/DML, Constraints & จุดตาย ERROR 1074 (`Transcript_20260922_DB_Lab_DDL_DML_ERROR1074.md`)**](file:///C:/Project/Voice/02_Database_System/Transcript_20260922_DB_Lab_DDL_DML_ERROR1074.md)
- [**ภาพหน้าจอ phpMyAdmin โครงสร้างตาราง (`IMG_20260922_124841_660@1996423590.jpg`)**](file:///C:/Project/Voice/02_Database_System/IMG_20260922_124841_660@1996423590.jpg)
- [**ภาพหน้าจอ ERROR 1074 CHAR(500) limit (`IMG_20260922_142452_298@-1416416793.jpg`)**](file:///C:/Project/Voice/02_Database_System/IMG_20260922_142452_298@-1416416793.jpg)
- [**ภาพหน้าจอคำสั่ง DDL ALTER TABLE (`IMG_20260922_142503_490@2024331400.jpg`)**](file:///C:/Project/Voice/02_Database_System/IMG_20260922_142503_490@2024331400.jpg)
