# สรุปภาพรวม: วิชาระบบฐานข้อมูล (Database System)
**กลุ่มโฟลเดอร์:** `02_Database_System`  
**วิชา:** ระบบฐานข้อมูล (Database System / Database Management Systems)  
**หัวข้อการสอนหลัก:** 
1. **Transaction Management & ACID Properties**
2. **Concurrency Control & Lock-based Concurrency Matrix (S/X Lock)**
3. **System Recovery & Crash Handling (Soft Crash vs Hard Crash / Log File Undo-Redo)**
4. **การสอบเก็บคะแนนในห้องเรียน (Pop Quiz ในชั่วโมงเรียน)**
5. **การนัดหมายหัวข้อถัดไป: Normalization**

---

## 📋 รายการไฟล์เสียงในกลุ่มนี้

| ชื่อไฟล์ | วันที่-เวลาที่บันทึก | ความยาว | สาระสำคัญ / กิจกรรมในชั้นเรียน |
| :--- | :--- | :--- | :--- |
| `20260908_130406.aac` | 08/09/2569 13:04 น. | 6 นาที 21 วินาที | **Part 1:** ชนิดของไฟล์ข้อมูล (Master File, Transaction File), นิยามของ Transaction, คำสั่ง INSERT / UPDATE / DELETE / QUERY, ตัวอย่างธุรกรรมการโอนเงิน |
| `20260908_131052.aac` | 08/09/2569 13:10 น. | 67 นาที 08 วินาที | **Part 2 (การบรรยายหลัก):** เจาะลึก Transaction Lifecycle, ACID Properties, ปัญหาเมื่อทำงานพร้อมกัน (Lost Update, Dirty Read, Inconsistent Analysis), ตาราง Lock Matrix (Shared Lock `S` vs Exclusive Lock `X`), Two-Phase Locking (2PL), Deadlock, และ System Failure Recovery |
| `20260908_143913.aac` | 08/09/2569 14:39 น. | 17 นาที 15 วินาที | **Part 3 (สอบเก็บคะแนน Pop Quiz):** อาจารย์สั่งสอบเก็บคะแนนกระทันหัน 2 ข้อ ให้เวลาข้อละ 5 นาที เขียนลงกระดาษ A4 แบ่งครึ่งหน้า-หลัง (ข้อ 1 ACID, ข้อ 2 Lock Matrix & 5 Transactions Crash Recovery) |
| `-.aac` | 08/09/2569 14:39 น. | 17 นาที 15 วินาที | *ไฟล์สำเนา (Duplicate)* ขนาดและเนื้อหาตรงกับ `20260908_143913.aac` ทุกประการ |

---

## 🎯 จุดสำคัญที่อาจารย์เน้นย้ำ (Core Lecture Concepts)

### 1. นิยาม Transaction
- Transaction คือ กลุ่มของคำสั่งการทำงานหนึ่งๆ ที่กระทำต่อฐานข้อมูลเพื่อทำให้เกิดการเปลี่ยนแปลงข้อมูล (Insert, Update, Delete) หรือสืบค้นข้อมูล (Query)
- Transaction หนึ่งๆ อาจประกอบด้วยคำสั่ง SQL เดียว หรือหลายคำสั่งรวมกันเป็นหนึ่งหน่วยงาน (Unit of Work) เช่น **การโอนเงิน (Bank Transfer):**
  1. หักเงินจากบัญชีออมทรัพย์ (Saving Account) -> `UPDATE saving SET balance = balance - X`
  2. เพิ่มเงินเข้าบัญชีกระแสรายวัน (Checking Account) -> `UPDATE checking SET balance = balance + X`
  *ทั้งสองคำสั่งต้องสำเร็จทั้งคู่ หรือไม่สำเร็จเลย*

### 2. คุณสมบัติ ACID Properties (ออกสอบตรงๆ ในควิซ)
- **A - Atomicity (ความเป็นหนึ่งเดียว):** ต้องทำงานสำเร็จครบทุกคำสั่ง (All) หรือไม่ทำเลย (Nothing) หากเกิดปัญหากลางคันต้องย้อนกลับ (Rollback)
- **C - Consistency (ความถูกต้องสอดคล้อง):** ข้อมูลต้องเปลี่ยนจากสถานะที่ถูกต้องหนึ่งไปยังอีกสถานะที่ถูกต้องหนึ่งตามกฎเกณฑ์ (Integrity Constraints)
- **I - Isolation (ความโดดเดี่ยว/เป็นอิสระ):** แต่ละ Transaction ที่ทำงานพร้อมกันต้องไม่รบกวนกัน เสมือนทำงานอยู่เพียงลำพัง
- **D - Durability (ความคงทนถาวร):** เมื่อ Commit สำเร็จแล้ว ผลลัพธ์ต้องถูกบันทึกอย่างถาวร แม้ระบบจะล่ม (Crash) ข้อมูลก็ต้องไม่สูญหาย

### 3. Concurrency Control & Lock Matrix (ออกสอบตรงๆ ในควิซ)
- **Shared Lock (S):** สำหรับการอ่านข้อมูล (Read-only) สามารถถือพร้อมกันหลาย Transaction ได้
- **Exclusive Lock (X):** สำหรับการแก้ไขข้อมูล (Write/Read) ถือได้เพียง Transaction เดียวเท่านั้น
- **ตาราง Lock Compatibility Matrix:**

| Lock ที่ขอเข้ามา \ Lock ที่ถืออยู่ | Shared Lock (S) | Exclusive Lock (X) |
| :---: | :---: | :---: |
| **Shared Lock (S)** | **Yes (อนุญาต)** | **No (ปฏิเสธ/ต้องรอ)** |
| **Exclusive Lock (X)** | **No (ปฏิเสธ/ต้องรอ)** | **No (ปฏิเสธ/ต้องรอ)** |

### 4. การจัดการความล้มเหลวและการกู้คืน (Crash Recovery)
- **Soft Crash (System Failure):** RAM หาย แต่ Disk ไม่พัง -> ใช้ **Log File** ในการกู้คืน
  - Transaction ที่มี `COMMIT` ใน Log -> ให้ทำการ **REDO** (ทำซ้ำเพื่อให้ข้อมูลสมบูรณ์)
  - Transaction ที่ยังไม่มี `COMMIT` หรือมี `START` แต่ยังค้างอยู่ -> ให้ทำการ **UNDO / ROLLBACK** (ยกเลิกเพื่อคืนสถานะเดิม)
- **Hard Crash (Media Failure):** Disk พังทางกายภาพ -> ต้องใช้ **Full Backup** ผสานกับ Log เพื่อ Restore

---

## 📝 ข้อสอบและการสอบเก็บคะแนนที่เกิดขึ้นจริง (In-Class Quiz)

> [!IMPORTANT]
> **ข้อสอบ Pop Quiz ประจำคาบ 8 ก.ย. 2569 (เขียนใส่กระดาษ A4 หน้า-หลัง):**
> 
> **ข้อที่ 1 (เวลาทำ 5 นาที):**  
> *"ให้อธิบายคุณสมบัติของ Transaction ที่เป็น ACID Property (Atomicity, Consistency, Isolation, Durability) มาโดยละเอียด"*
> 
> **ข้อที่ 2 (เวลาทำ 5 นาที):**  
> 1. *"ให้อธิบายตาราง Lock-based Concurrency Matrix (การทำงานของ S Lock และ X Lock ว่าทำไมตอบ Yes หรือ No)"*  
> 2. *"หากระบบเกิด Crash ขึ้นมา แล้ว Server รีสตาร์ทกลับขึ้นมาทำงานใหม่ DBMS เข้ามาตรวจเช็คที่ Log File พบว่ามีอยู่ 5 Transaction... ถามว่า DBMS จะสั่งให้ทำอะไรกับ Transaction ทั้ง 5 นี้บ้าง (Transaction ใดต้อง Redo, Transaction ใดต้อง Undo)"*

---

## ⏰ สิ่งที่อาจารย์แจ้งล่วงหน้าสำหรับคาบถัดไป
- อาจารย์แจ้งว่าเดิมทีจะให้ทำโจทย์ **Normalization** ในคาบนี้ แต่เปลี่ยนใจเอาโจทย์ ACID/Locking ก่อน
- **สัปดาห์ถัดไปจะเรียนและทำโจทย์เรื่อง "Normalization" (1NF, 2NF, 3NF, BCNF)** ให้นักศึกษาเตรียมตัวมาล่วงหน้า
