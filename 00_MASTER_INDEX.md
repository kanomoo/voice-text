# สารบัญและรายงานวิเคราะห์ไฟล์เสียงฉบับสมบูรณ์ (Master Voice Index & Intelligence Report)
**ตำแหน่งไดเรกทอรี:** `C:\Project\Voice\`  
**วันที่ประมวลผลล่าสุด:** 15 กันยายน 2569  
**จำนวนไฟล์เสียงทั้งหมด:** 25 ไฟล์เสียง (.aac) + 1 โฟลเดอร์ภาพประกอบ (`DSA-pic/` รวม 87 ภาพ)  

---

## 🧭 การจัดหมวดหมู่วิชาและโครงสร้างโฟลเดอร์ (Directory Structure)

ตามคำสั่งของผู้ใช้งาน ได้ทำการแยกไฟล์เสียงออกเป็น **7 กลุ่มวิชาและโปรเจกต์** โดยสร้างโฟลเดอร์ไว้ภายใน `C:\Project\Voice\` ดังนี้:

```
C:\Project\Voice\
├── 00_MASTER_INDEX.md                                           <-- ไฟล์นี้ (สารบัญและรายงานภาพรวมทั้งหมด)
├── main.md                                                      <-- คู่มือกระบวนการทำงานสำหรับ AI (AI Workflow & Operating Guide)
│
├── 01_Innovative_Technopreneurs\                                 <-- วิชาผู้ประกอบการนวัตกรรม (โปรเจกต์ Smart Green Wall & Final Report)
│   ├── README.md                                                 <-- สรุปวิชา, โปรเจกต์, กำหนดส่งงาน 1-2 ต.ค., เกณฑ์คะแนนเต็ม 28
│   ├── Transcript_20260126_Customer_Validation.md                <-- บทวิเคราะห์สัมภาษณ์ลูกค้า 2 ราย
│   ├── Transcript_20260904_Final_Report_Guidelines.md            <-- บทวิเคราะห์คำสั่งรายงาน 10 หัวข้อ, กฎ BMC
│   ├── Transcript_20260911_Risk_Management_Deadlines.md          <-- บทวิเคราะห์เรื่องบริหารความเสี่ยง และคะแนน
│   ├── 20260126_162937.txt                                       <-- [ถอดความละเอียดทุกคำพูด] สัมภาษณ์ลูกค้า #1 (ขนาด 3 แบบ, เตือน PM2.5)
│   ├── 20260126_164100.txt                                       <-- [ถอดความละเอียดทุกคำพูด] สัมภาษณ์ลูกค้า #2 (ฟีดแบ็กห้าง/ออฟฟิศ)
│   ├── 20260904_105814.txt                                       <-- [ถอดความละเอียดทุกคำพูด] สั่งรายงานเล่มจบ 10 หัวข้อ, กฎ BMC 1 หน้า
│   └── In20260911_114230.txt                                     <-- [ถอดความละเอียดทุกคำพูด] การบริหารความเสี่ยงร้านกาแฟ, คะแนนเต็ม 28
│
├── 02_Database_System\                                           <-- วิชาระบบฐานข้อมูล (Transaction, Lock Matrix, NoSQL & CAP Theorem)
│   ├── README.md                                                 <-- สรุปวิชา, ACID, Lock Matrix S/X, NoSQL, CAP Theorem, แล็บ 2 สัปดาห์
│   ├── Transcript_20260908_130406_Transaction_Basics.md          <-- บทวิเคราะห์ Part 1: แฟ้ม Master/Transaction
│   ├── Transcript_20260908_131052_Concurrency_ACID_Recovery.md  <-- บทวิเคราะห์ Part 2: ACID, Concurrency, Recovery
│   ├── Transcript_20260908_143913_InClass_Quiz_ACID_Lock.md      <-- บทวิเคราะห์ Part 3: ข้อสอบควิซในห้อง
│   ├── Transcript_20260915_130022_NoSQL_BigData_CAP.md          <-- บทวิเคราะห์ Part 4: NoSQL, Big Data, 4 Models, CAP Theorem
│   ├── 20260908_130406.txt                                       <-- [ถอดความละเอียดทุกคำพูด] Master/Transaction File, ธุรกรรมโอนเงิน
│   ├── 20260908_131052.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บรรยายหลัก 67 นาที: ACID, 2PL, Lock Matrix
│   ├── 20260908_143913.txt                                       <-- [ถอดความละเอียดทุกคำพูด] ควิซในห้อง A4 2 ข้อ (ACID & Log Crash)
│   ├── -.txt                                                     <-- [ถอดความละเอียดทุกคำพูด] ไฟล์ซ้ำตรงกับ 20260908_143913.txt
│   └── 20260915_130022.txt                                       <-- [ถอดความละเอียดทุกคำพูด] NoSQL, 4 Data Models, CAP Theorem, นัดแล็บ
│
├── 03_Data_Structures_and_Algorithms\                            <-- วิชาโครงสร้างข้อมูลและอัลกอริทึม (DSA - Python)
│   ├── README.md                                                 <-- สรุปวิชา DSA, สารบัญภาพ DSA-pic 87 ภาพ, ข้อสอบปลายภาค
│   ├── Transcript_20260902_Hashing_Lecture.md                    <-- บทวิเคราะห์ Hashing & Collision Resolution พร้อมภาพสไลด์
│   ├── Transcript_20260902_PriorityQueue_BinaryHeap.md           <-- บทวิเคราะห์ Priority Queue & Binary Heap พร้อมภาพสไลด์
│   ├── Transcript_20260902_Exam_Focus_Node_Calculation.md        <-- บทวิเคราะห์จุดออกสอบข้อ 2 (คำนวณโหนดสูง 10) พร้อมภาพสไลด์
│   ├── Transcript_20260909_BinaryHeap_Implementation_Exam_Tips.md<-- บทวิเคราะห์โค้ด Python และโจทย์ DeleteMin 3 รอบ พร้อมภาพสไลด์
│   ├── 20260902_091736.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บทที่ 7: Separate Chaining & Linear Probing
│   ├── 20260902_094834.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บทที่ 7: Quadratic Probing & Double Hashing
│   ├── 20260902_104259.txt                                       <-- [ถอดความละเอียด] เสียงพักเบรก 2 วินาที
│   ├── 20260902_104304.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บทที่ 7: Rehashing & ตารางแฮชใหม่ 17 ช่อง
│   ├── 20260902_110748.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บทที่ 8: นิยามคิว และสิทธิพิเศษการแซงคิว
│   ├── 20260902_111515.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บทที่ 8: Heap กองทราย, Min-Heap, 2 คุณสมบัติ
│   ├── 20260902_112213.txt                                       <-- [ถอดความละเอียดทุกคำพูด] Complete Binary Tree ใส่ซ้ายไปขวา ลบขวาไปซ้าย
│   ├── 20260902_112628.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 ข้อสอบข้อ 2: คำนวณโหนดสูง 10 (1024/2047)
│   ├── 20260902_113741.txt                                       <-- [ถอดความละเอียดทุกคำพูด] แปลง Tree เป็น Array 1D (2i, 2i+1, i//2)
│   ├── dsa20260909_092220.txt                                    <-- [ถอดความละเอียดทุกคำพูด] ย้ำข้อสอบปลายภาคออกเป็น Array
│   ├── dsa20260909_092303.txt                                    <-- [ถอดความละเอียดทุกคำพูด] 🔥 ไล่โค้ดคลาส BinaryHeap, insert, percolate up
│   ├── 20260909_103704.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 ไล่โค้ด deleteMin, การบ้านเที่ยงตรง, ข้อสอบ 3 รอบ
│   └── DSA-pic/                                                  <-- คลังภาพกระดานและสไลด์ 87 ภาพ (เชื่อมโยงภาพถ่ายกับการบรรยาย)
│
├── 04_Computer_Graphics_Design\                                  <-- วิชาคอมพิวเตอร์กราฟิกส์ (Adobe Illustrator)
│   ├── README.md                                                 <-- สรุปกฎสอบ 9.00-12.00 น., ให้เน็ต 10 นาที, สอบปฏิบัติ 4 ข้อ
│   ├── Transcript_20260302_Final_Exam_Briefing.md                <-- บทวิเคราะห์ข้อสอบปฏิบัติ 4 ข้อ 300 คะแนน
│   └── 20260302_093603.txt                                       <-- [ถอดความละเอียดทุกคำพูด] ชี้แจงข้อสอบ 4 ข้อ (3D Revolve, Tesla, Pen Tool)
│
├── 05_Technical_English\                                         <-- วิชาภาษาอังกฤษเชิงเทคนิคเพื่อการสื่อสาร
│   ├── README.md                                                 <-- สรุปบทพูดนำเสนอ Custom PC และงานอดิเรกดนตรี
│   ├── Transcript_20260223_Presentation_Practice_Coaching.md     <-- บทวิเคราะห์การซ้อมพรีเซนต์
│   └── 20260223_143626.txt                                       <-- [ถอดความละเอียดทุกคำพูด] ซ้อมพรีเซนต์เดี่ยว, ออกเสียง Piece, Satisfaction
│
├── 06_Personal_Financial_Trading\                                <-- การเงินส่วนบุคคล / การลงทุนเทรดดิ้ง (Forex & MT5 EA)
│   ├── README.md                                                 <-- สรุปเงื่อนไขโบนัสเทรดครบ 5 ออเดอร์, การติดตั้ง EA บน MT5
│   ├── Transcript_20260409_Broker_MT5_EA_Support.md              <-- บทวิเคราะห์การสนทนากับฝ่ายบริการลูกค้า
│   └── 20260409_105602.txt                                       <-- [ถอดความละเอียดทุกคำพูด] คุยกับคุณบัว โบรกเกอร์ MT5 EA ถอนกำไร
│
├── 07_Software_Engineering\                                      <-- วิชาวิศวกรรมซอฟต์แวร์ (Software Engineering - Use Case Modeling)
│   ├── README.md                                                 <-- สรุปวิชา, องค์ประกอบ Use Case, Include vs Extend, กำหนดส่งงาน
│   ├── Transcript_20260915_092638_UseCase_Diagram.md             <-- บทวิเคราะห์ Use Case Diagram, System Boundary & Library Case Study
│   └── SE20260915_092638.txt                                     <-- [ถอดความละเอียดทุกคำพูด] บรรยาย Use Case Diagram, ระบบห้องสมุด
│
└── Success\                                                      <-- แหล่งจัดเก็บไฟล์เสียงต้นฉบับทั้ง 25 ไฟล์ที่แปลเสร็จแล้ว (.aac)
```

---

## 📊 ตารางแสดงความสัมพันธ์ของไฟล์เสียงทั้งหมด 25 ไฟล์ (Master Mapping Table)

> [!NOTE]
> **สถานะการจัดเก็บไฟล์เสียง:** ไฟล์เสียงต้นฉบับทั้ง 25 ไฟล์ ได้รับการถอดความและวิเคราะห์เรียบร้อยแล้วทั้งหมด และถูกย้ายไปจัดเก็บอย่างเป็นระเบียบในโฟลเดอร์ **`C:\Project\Voice\Success\`** เรียบร้อยแล้ว เพื่อให้รูทของโฟลเดอร์ `Voice/` เป็นระเบียบและพร้อมรับไฟล์เสียงใหม่เข้ามาประมวลผลตามคู่มือ [**`main.md`**](file:///C:/Project/Voice/main.md)

| ลำดับ | ชื่อไฟล์เสียง (จัดเก็บใน `Success/`) | วันที่บันทึก | ความยาว | หมวดหมู่วิชา / โฟลเดอร์ | สาระสำคัญ / การดำเนินการ |
| :---: | :--- | :---: | :---: | :--- | :--- |
| 1 | `20260126_162937.aac` | 26/01/2569 | 2m 48s | `01_Innovative_Technopreneurs` | สัมภาษณ์ Customer Validation #1 โครงการ Smart Green Wall |
| 2 | `20260126_164100.aac` | 26/01/2569 | 2m 41s | `01_Innovative_Technopreneurs` | สัมภาษณ์ Customer Validation #2 โครงการ Smart Green Wall |
| 3 | `20260223_143626.aac` | 23/02/2569 | 26m 21s | `05_Technical_English` | ซ้อมบทพูดพรีเซนต์เดี่ยว Custom PC และดนตรี |
| 4 | `20260302_093603.aac` | 02/03/2569 | 5m 16s | `04_Computer_Graphics_Design` | ชี้แจงข้อสอบปฏิบัติปลายภาค 4 ข้อ 300 คะแนน (Illustrator) |
| 5 | `20260409_105602.aac` | 09/04/2569 | 2m 23s | `06_Personal_Financial_Trading` | ฝ่ายบริการลูกค้าโบรกเกอร์ เงื่อนไขถอนกำไร MT5 / EA |
| 6 | `20260902_091736.aac` | 02/09/2569 | 29m 51s | `03_Data_Structures_and_Algorithms` | บทที่ 7 Hashing: Separate Chaining & Open Addressing |
| 7 | `20260902_094834.aac` | 02/09/2569 | 31m 43s | `03_Data_Structures_and_Algorithms` | บทที่ 7 Hashing: Quadratic Probing & Double Hashing |
| 8 | `20260902_104259.aac` | 02/09/2569 | 0m 02s | `03_Data_Structures_and_Algorithms` | เสียงช่วงพักเบรกสั้น 2 วินาที |
| 9 | `20260902_104304.aac` | 02/09/2569 | 23m 49s | `03_Data_Structures_and_Algorithms` | สรุปภาพรวม Hashing เตรียมขึ้น Priority Queue |
| 10 | `20260902_110748.aac` | 02/09/2569 | 7m 09s | `03_Data_Structures_and_Algorithms` | บทที่ 8 Priority Queue: นิยามคิวและการแซงคิว |
| 11 | `20260902_111515.aac` | 02/09/2569 | 6m 36s | `03_Data_Structures_and_Algorithms` | บทที่ 8 Heap Structure: รูปทรงพีระมิดกองทราย และ Min-Heap |
| 12 | `20260902_112213.aac` | 02/09/2569 | 4m 01s | `03_Data_Structures_and_Algorithms` | กฎ Complete Binary Tree: ใส่ซ้ายไปขวา ลบขวาไปซ้าย |
| 13 | `20260902_112628.aac` | 02/09/2569 | 10m 42s | `03_Data_Structures_and_Algorithms` | **🔥 ข้อสอบข้อ 2!** สูตรคำนวณโหนดความสูง 10 (1024/2047) |
| 14 | `20260902_113741.aac` | 02/09/2569 | 7m 02s | `03_Data_Structures_and_Algorithms` | สูตร Array 1D: Root=1, Left=2i, Right=2i+1, Parent=floor(i/2) |
| 15 | `20260904_105814.aac` | 04/09/2569 | 9m 10s | `01_Innovative_Technopreneurs` | โครงสร้างเล่มรายงาน 10 หัวข้อ, กฎ BMC 1 หน้า, นัดส่งงาน 1-2 ต.ค. |
| 16 | `20260908_130406.aac` | 08/09/2569 | 6m 21s | `02_Database_System` | นิยาม Transaction, ชนิดไฟล์ Master/Transaction, เคสโอนเงิน |
| 17 | `20260908_131052.aac` | 08/09/2569 | 67m 08s | `02_Database_System` | บรรยายหลัก ACID, Concurrency Control, Lock Matrix S/X, Log |
| 18 | `20260908_143913.aac` | 08/09/2569 | 17m 15s | `02_Database_System` | **🔥 Pop Quiz ในห้อง!** ข้อ 1 ACID / ข้อ 2 Lock Matrix & Log Crash |
| 19 | `-.aac` | 08/09/2569 | 17m 15s | `02_Database_System` | *ไฟล์ซ้ำ (Duplicate)* ตรงกับ `20260908_143913.aac` |
| 20 | `dsa20260909_092220.aac`| 09/09/2569 | 0m 36s | `03_Data_Structures_and_Algorithms` | ทบทวนสูตร Array และย้ำว่าข้อสอบออกเป็น Array |
| 21 | `dsa20260909_092303.aac`| 09/09/2569 | 50m 01s | `03_Data_Structures_and_Algorithms` | **🔥 ข้อสอบปลายภาค!** ไล่โค้ดคลาส BinaryHeap: `__init__`, `insert` |
| 22 | `20260909_103704.aac` | 09/09/2569 | 81m 39s | `03_Data_Structures_and_Algorithms` | **🔥 ข้อสอบปลายภาค!** ไล่โค้ด `deleteMin`, ข้อสอบให้ทำ 3 รอบ |
| 23 | `In20260911_114230.aac` | 11/09/2569 | 2m 23s | `01_Innovative_Technopreneurs` | การบริหารความเสี่ยงเคสร้านกาแฟ, ย้ำส่ง PDF วันที่ 1, คะแนนเต็ม 28 |
| 24 | `SE20260915_092638.aac`| 15/09/2569 | 60m 27s | `07_Software_Engineering` | บรรยาย Use Case Diagram, 4 Elements (Actor, Use Case, Boundary, Relations), Include vs Extend, ระบบห้องสมุด |
| 25 | `20260915_130022.aac` | 15/09/2569 | 67m 51s | `02_Database_System` | บรรยาย NoSQL vs RDBMS, Big Data (5 Vs), โมเดล 4 ชนิด (Key-Value, Column, Graph, Document), CAP Theorem, นัดแล็บ 2 สัปดาห์ |

---

## 📅 ปฏิทินวันเวลา กำหนดการส่งงาน และกิจกรรมสำคัญ (Master Deadlines Calendar)

| วันที่ตามกำหนด | เวลา | วิชาที่เกี่ยวข้อง | กิจกรรม / สิ่งที่ต้องส่ง / ข้อกำหนด |
| :--- | :--- | :--- | :--- |
| **09/09/2569** | **12.00 น. (เที่ยง)** | Data Structures & Algorithms | **ส่ง Assignment การบ้านในคาบ:** ทำ DeleteMin 1 ครั้ง และแปลงค่าลงในช่อง Array ส่งผ่าน Google Classroom |
| **15/09/2569** | **10.00 น.** | Software Engineering | **ประชาสัมพันธ์โครงการ IAESTE:** โครงการฝึกงานต่างประเทศ ณ ห้อง Spark ชั้น 1 |
| **สัปดาห์นี้** | ตามกำหนดใน Classroom | Software Engineering | **ส่งการบ้าน Use Case Diagram:** อาจารย์จะโพสต์โจทย์ Assignment เข้าสู่ Google Classroom ให้เขียนไดอะแกรมส่ง |
| **สัปดาห์นี้** | ในระบบ Classroom | Database System | **ส่งงานกลุ่ม ER Diagram:** ตัวแทนกลุ่มอัปโหลดภาพ/เอกสาร ER Diagram เข้าสู่ Google Classroom |
| **22/09/2569 เป็นต้นไป** | 2 สัปดาห์ติดต่อกัน | Database System | **เรียนภาคปฏิบัติการ Lab 2 สัปดาห์:** งดเรียนห้องบรรยาย ให้ไปเรียนที่ห้องแล็บคอมพิวเตอร์ตามรอบที่ลงชื่อใน Google Sheets เพื่อลงมือสร้าง Database จริง |
| **01/10/2569** | **ก่อน 12.00 น. (เที่ยง)** | Innovative Technopreneurs | **ส่งไฟล์ดิจิทัลทาง LINE กลุ่มวิชา:**<br>1. ไฟล์เล่มรายงานฉบับสมบูรณ์ (PDF)<br>2. ไฟล์สไลด์นำเสนอ Presentation (PDF) |
| **02/10/2569** | ในคาบเรียน | Innovative Technopreneurs | **1. ส่งรูปเล่มรายงานฉบับพิมพ์ Hard Copy:** ทุกกลุ่มทั้ง 18 กลุ่มต้องส่งเล่มในวันนี้ (ปริ้นท์ขาวดำได้)<br>**2. การนำเสนอผลงานรอบที่ 1:** สำหรับกลุ่มที่ 1 - 9 (บรรยาย 10 นาที ตอบคำถาม 5 นาที) |
| **09/10/2569** | ในคาบเรียน | Innovative Technopreneurs | **การนำเสนอผลงานรอบที่ 2:** สำหรับกลุ่มที่ 10 - 18 (บรรยาย 10 นาที ตอบคำถาม 5 นาที) |
| **วันสอบปลายภาค** | 09.00 - 12.00 น. | Computer Graphics & Design | **สอบปฏิบัติปลายภาค 3 ชั่วโมงเต็ม (Open Book):** ห้ามเข้าสายเกิน 09.10 น., ให้เน็ต 10 นาทีแรกยืนยันตัวตน, มี 4 ข้อ ข้อละ 75 คะแนน รวม 300 คะแนน |
| **วันสอบปลายภาค** | 3 ชั่วโมงเต็ม | Database System | **สอบปลายภาคข้อเขียน 40 คะแนนเต็ม!** ห้ามออกจากห้องสอบก่อน 1 ชั่วโมงแรก ครอบคลุม Transaction, ACID, Locking, Crash Recovery, RDBMS vs NoSQL, และ CAP Theorem |
| **วันสอบปลายภาค** | ตามตารางสอบ | Data Structures & Algorithms | **สอบข้อเขียน/ปฏิบัติปลายภาค:** มี 6-7 ข้อใหญ่ (มีโจทย์คำนวณโหนดความสูง 10, โจทย์ตารางแฮชเปล่า, และโจทย์ Array เปล่าให้ทำ DeleteMin 3 ครั้ง) |

---

## 🎯 คลังจุดเน้นย้ำและแนวข้อสอบรั่ว (Master Exam Secrets & Leaks)

### 1. วิชา Data Structures and Algorithms
1. **ข้อสอบข้อใหญ่ข้อที่ 2 (Complete Binary Tree):**
   - คำถาม: *"How many minimum/maximum number of nodes of complete binary tree at the height 10?"*
   - สูตรอย่างน้อย: $2^H = 2^{10} = \mathbf{1,024 \text{ โหนด}}$
   - สูตรอย่างมาก: $2^{H+1} - 1 = 2^{11} - 1 = \mathbf{2,047 \text{ โหนด}}$
   - **⚠️ กฎสำคัญ:** ห้ามตอบติดรูปเลขยกกำลัง ต้องตอบ 1024 และ 2047 เท่านั้น ไม่เช่นนั้นได้ 0 คะแนน
2. **ข้อสอบ Array Representation ของ Binary Heap:**
   - Root อยู่ที่ Index 1 เสมอ (Index 0 เว้นว่างไว้)
   - Left Child = $2i$, Right Child = $2i + 1$
   - Parent = $\lfloor i / 2 \rfloor$ (**ตัดเศษทิ้งเสมอ เช่น โหนด 7 พ่อคือ 3 ไม่ใช่ 4**)
3. **ข้อสอบไล่โค้ด DeleteMin ปลายภาค:**
   - ในข้อสอบจะให้ทำ **DeleteMin ติดต่อกัน 3 รอบ** แล้วเขียนสถานะของ Array สุดท้ายลงในตารางช่องสี่เหลี่ยมที่อาจารย์เตรียมไว้ให้
4. **ข้อสอบตารางแฮช (Hashing):**
   - ให้ตารางแฮชเปล่ามา พร้อมฟังก์ชัน $h_i(x) = (\text{hash}(x) + f(i)) \pmod{\text{Table\_Size}}$ ให้นำค่ามาแฮชและแก้ปัญหาการชนลงตาราง

### 2. วิชา Database System
1. **คุณสมบัติ ACID Properties:** ต้องจำและอธิบายได้ครบทั้ง 4 ตัว (Atomicity, Consistency, Isolation, Durability)
2. **ตาราง Lock Compatibility Matrix:**
   - Shared Lock (S) vs Exclusive Lock (X)
   - **มีเพียงกรณีเดียวที่อนุญาตคือ (S, S) = Yes** อีก 3 กรณีที่เหลือคือ (S, X), (X, S), (X, X) ต้องตอบ **No** ทั้งหมด
3. **การกู้คืนหลังเซิร์ฟเวอร์ล่ม (Crash Recovery):**
   - ตรวจสอบจาก Log File: รายการที่มี `COMMIT` แล้ว $\rightarrow$ ให้สั่ง **REDO**
   - รายการที่มี `START` แต่ยังไม่มี `COMMIT` $\rightarrow$ ให้สั่ง **UNDO / ROLLBACK**
4. **การเปรียบเทียบ RDBMS vs NoSQL & Big Data:**
   - ข้อจำกัด RDBMS: Join are expensive, Hard to scale-out horizontally, Impedance mismatch
   - โมเดล NoSQL 4 ชนิด: Key-Value (DynamoDB), Column Family (Cassandra เขียนเร็ว 0.12ms ด้วย Append-only), Graph (Neo4j เหมาะกับ Social Network), Document (MongoDB เก็บ JSON/BSON)
   - ทฤษฎีบท **CAP Theorem:** ระบบกระจายศูนย์เลือกได้มากสุด 2 จาก 3 (RDBMS = CA, MongoDB = CP, Cassandra = AP)
5. **ข้อสอบปลายภาค 40 คะแนนเต็ม (สอบ 3 ชั่วโมงเต็ม):** ห้ามออกจากห้องสอบก่อน 1 ชั่วโมงแรก ต้องบริหารเวลาทำข้อสอบให้ทัน

### 3. วิชา Software Engineering
1. **การแยกแยะระหว่าง `<<include>>` กับ `<<extend>>`:**
   - ถ้าฟังก์ชันย่อยต้องทำ **ทุกครั้ง ขาดไม่ได้** $\rightarrow$ ใช้ **`<<include>>`** (ลูกศรชี้จาก Base ไปหาตัวช่วย) เช่น `Withdraw` $\rightarrow$ `<<include>>` $\rightarrow$ `Login`
   - ถ้าฟังก์ชันย่อยเกิด **เฉพาะบางกรณี เป็นทางเลือก** $\rightarrow$ ใช้ **`<<extend>>`** (ลูกศรชี้จากตัวเสริมกลับมาหา Base) เช่น `Login` $\leftarrow$ `<<extend>>` $\leftarrow$ `Request OTP` หรือ `Change Password`
2. **กฎการวาด Use Case Diagram:**
   - Use Case ต้องเป็น **วงรี** เท่านั้น ตั้งชื่อด้วย **Verb + Object** (ห้ามใส่ Action ละเอียดระดับปุ่ม เช่น "Click button")
   - Actor ต้องเป็นรูป **Stickman** แทน **Role** (ห้ามใส่ชื่อบุคคลเฉพาะเจาะจง และห้ามใส่ Database หรือ Server ภายในเป็น Actor)
   - Actor ต้องอยู่นอกกรอบ System Boundary เสมอ และ Use Case ต้องอยู่ในกรอบเสมอ

### 4. วิชา Computer Graphics & Design (Adobe Illustrator)
1. **ข้อสอบปฏิบัติ 4 ข้อ ข้อละ 75 คะแนน (รวม 300 คะแนน):**
   - ข้อ 1: 3D Effect เลือกระหว่าง **Revolve** (หมุนแกนทรงสมมาตร) หรือ **Extrude & Bevel** (ดึงความหนา)
   - ข้อ 2: 3D Effect ผสานการใช้ **Offset Path** ขยายขอบ และ **Pathfinder** (Unite/Minus)
   - ข้อ 3: Image Path ตาม **Workshop รถ Tesla สีแดง**
   - ข้อ 4: **Pen Tool** ดราฟท์เส้นภาพการ์ตูนและลงสี (ใช้เวลาเยอะที่สุด)
2. **การเข้าห้องสอบ:** ห้ามสายเกิน 09.10 น. อินเทอร์เน็ตเปิดให้ 10 นาทีแรกสำหรับยืนยันตัวตนเท่านั้น หลังจากนั้นกรรมการตัดเน็ตทันที
