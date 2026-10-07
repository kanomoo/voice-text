# สารบัญและรายงานวิเคราะห์ไฟล์เสียงฉบับสมบูรณ์ (Master Voice Index & Intelligence Report)
**ตำแหน่งไดเรกทอรี:** `C:\Project\Voice\`  
**วันที่ประมวลผลล่าสุด:** 7 ตุลาคม 2569  
**จำนวนไฟล์เสียงทั้งหมด:** 45 รายการไฟล์เสียง (.aac / .m4a) + โฟลเดอร์ภาพประกอบ (`DSA-pic/` รวม 106 ภาพ + ภาพแล็บฐานข้อมูลใน `02_Database_System/` 3 ภาพ + ภาพกระดาน/ประกาศใน `07_Software_Engineering/` 2 ภาพ)  

---

## 🧭 การจัดหมวดหมู่วิชาและโครงสร้างโฟลเดอร์ (Directory Structure)

ตามคำสั่งของผู้ใช้งาน ได้ทำการแยกไฟล์เสียงออกเป็น **8 กลุ่มวิชาและโปรเจกต์** โดยสร้างโฟลเดอร์ไว้ภายใน `C:\Project\Voice\` ดังนี้:

```text
C:\Project\Voice\
├── 00_MASTER_INDEX.md                                           <-- ไฟล์นี้ (สารบัญและรายงานภาพรวมทั้งหมด)
├── main.md                                                      <-- คู่มือกระบวนการทำงานสำหรับ AI (AI Workflow & Operating Guide)
│
├── 01_Innovative_Technopreneurs\                                 <-- วิชาผู้ประกอบการนวัตกรรม (โปรเจกต์ Smart Green Wall & Final Report)
│   ├── README.md                                                 <-- สรุปวิชา, โปรเจกต์, กำหนดส่งงาน 1-2 ต.ค., เกณฑ์คะแนนเต็ม 28
│   ├── Transcript_20260126_Customer_Validation.md                <-- บทวิเคราะห์สัมภาษณ์ลูกค้า 2 ราย
│   ├── Transcript_20260904_Final_Report_Guidelines.md            <-- บทวิเคราะห์คำสั่งรายงาน 10 หัวข้อ, กฎ BMC
│   ├── Transcript_20260911_Risk_Management_Deadlines.md          <-- บทวิเคราะห์เรื่องบริหารความเสี่ยง และคะแนน
│   ├── Transcript_20260925_Business_Forms_CNV_Intellectual_Property.md <-- 🔥 บทวิเคราะห์บทที่ 10: ภาษีซ้ำซ้อน, CNV, Intrapreneurship, ลิขสิทธิ์ vs สิทธิบัตร, Reverse Engineering, CL
│   ├── 20260126_162937.txt                                       <-- [ถอดความละเอียดทุกคำพูด] สัมภาษณ์ลูกค้า #1
│   ├── 20260126_164100.txt                                       <-- [ถอดความละเอียดทุกคำพูด] สัมภาษณ์ลูกค้า #2
│   ├── 20260904_105814.txt                                       <-- [ถอดความละเอียดทุกคำพูด] สั่งรายงานเล่มจบ 10 หัวข้อ
│   ├── In20260911_114230.txt                                     <-- [ถอดความละเอียดทุกคำพูด] การบริหารความเสี่ยง, คะแนนเต็ม 28
│   ├── 20260925_093530.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 บทที่ 10 Part 1: โครงสร้างองค์กร, 5 ธุรกิจ, CNV 4 โมเดล, สิทธิบัตร
│   └── 20260925_105917.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 บทที่ 10 Part 2: เครื่องหมายการค้า, ความลับทางการค้า, CL, Parallel Import
│
├── 02_Database_System\                                           <-- วิชาระบบฐานข้อมูล (Transaction, NoSQL, DDL/DML, Error 1074)
│   ├── README.md                                                 <-- สรุปวิชา, ACID, Lock Matrix, NoSQL, DDL/DML CLI
│   ├── Transcript_20260908_130406_Transaction_Basics.md          <-- บทวิเคราะห์ Part 1: แฟ้ม Master/Transaction
│   ├── Transcript_20260908_131052_Concurrency_ACID_Recovery.md  <-- บทวิเคราะห์ Part 2: ACID, Concurrency, Recovery
│   ├── Transcript_20260908_143913_InClass_Quiz_ACID_Lock.md      <-- บทวิเคราะห์ Part 3: ข้อสอบควิซในห้อง
│   ├── Transcript_20260915_130022_NoSQL_BigData_CAP.md          <-- บทวิเคราะห์ Part 4: NoSQL, Big Data, CAP Theorem
│   ├── Transcript_20260922_DB_Lab_DDL_DML_ERROR1074.md           <-- 🔥 บทวิเคราะห์เจาะลึกแล็บ DDL/DML, Constraints, ERROR 1074 CHAR(500)
│   ├── Transcript_20260929_DB_Lab_FK_Constraints_Cascade_Restrict_Exam_Presentation.md <-- 🔥 บทวิเคราะห์แล็บ 2: CASCADE vs RESTRICT, Normalization, การบ้าน SQL, พรีเซนต์ห้อง 307
│   ├── Transcript_20261006_DB_Final_Exam_Rules_Negative_Marking_ER_Presentation.md <-- 🔥 บทวิเคราะห์กฎสอบ Final ปรนัย 80 ข้อ Open Book, กฎหักคะแนนติดลบ, สรุปพรีเซนต์ Total/Partial
│   ├── 20260908_130406.txt                                       <-- [ถอดความละเอียดทุกคำพูด] Master/Transaction File
│   ├── 20260908_131052.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บรรยายหลัก 67 นาที: ACID
│   ├── 20260908_143913.txt                                       <-- [ถอดความละเอียดทุกคำพูด] ควิซในห้อง A4 2 ข้อ
│   ├── 20260915_130022.txt                                       <-- [ถอดความละเอียดทุกคำพูด] NoSQL, CAP Theorem
│   ├── 20260922_131058.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 ปฏิบัติการแล็บ DDL, XAMPP CLI, utf8mb4, ERROR 1074
│   ├── 20260929_142500.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 แล็บ 2: Foreign Key Constraints, ผลสุ่มกงล้อพรีเซนต์ห้อง 307
│   ├── 20261006_161408.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 กฎสอบ Final ปรนัย 80 ข้อ, Negative Marking, ดินสอ 2B, ส่ง ER 2 ช่อง
│   ├── IMG_20260922_124841_660@1996423590.jpg                    <-- โครงสร้างตารางใน phpMyAdmin
│   ├── IMG_20260922_142452_298@-1416416793.jpg                   <-- ภาพหน้าจอ ERROR 1074 CHAR(500) limit
│   └── IMG_20260922_142503_490@2024331400.jpg                    <-- ภาพหน้าจอคำสั่ง DDL ALTER TABLE
│
├── 03_Data_Structures_and_Algorithms\                            <-- วิชาโครงสร้างข้อมูลและอัลกอริทึม (DSA - Python)
│   ├── README.md                                                 <-- สรุปวิชา DSA, สารบัญภาพ DSA-pic 106 ภาพ, ข้อสอบปลายภาค
│   ├── Transcript_20260902_Hashing_Lecture.md                    <-- บทวิเคราะห์ Hashing & Collision Resolution
│   ├── Transcript_20260902_PriorityQueue_BinaryHeap.md           <-- บทวิเคราะห์ Priority Queue & Binary Heap
│   ├── Transcript_20260902_Exam_Focus_Node_Calculation.md        <-- บทวิเคราะห์จุดออกสอบข้อ 2 (คำนวณโหนดสูง 10)
│   ├── Transcript_20260909_BinaryHeap_Implementation_Exam_Tips.md<-- บทวิเคราะห์โค้ด Python และโจทย์ DeleteMin 3 รอบ
│   ├── Transcript_20260916_Comparison_Sorting_Insertion_Selection_Bubble_Exam_Trace.md <-- บทวิเคราะห์เจาะลึก Sorting 3 แบบ
│   ├── Transcript_20260923_Graph_Theory_Representations_Exam_Leaks.md <-- 🔥 บทวิเคราะห์เจาะลึก Graph Theory, ข้อสอบรั่ว 14 ภาพ, Memory Waste 24.48% vs 75.51%
│   ├── Transcript_20261007_ShortestPath_Assignment4_Final_Exam_Leaks.md <-- 🔥 บทวิเคราะห์บทที่ 11 Shortest Path, เฉลยละเอียด Assignment 4, ชี้แจงข้อสอบ Final 7 ข้อ 70 คะแนน (35%) Open Book + เครื่องคิดเลข
│   ├── 20260902_091736.txt ถึง 20260916_102037.txt (12 ไฟล์)    <-- [ถอดความละเอียดทุกคำพูด] Hashing, Heap, Sorting
│   ├── 20260923_091645.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 บทที่ 10 Graph, ทฤษฎีกราฟ, ข้อสอบรั่ว Complete Graph 45 เส้น
│   ├── 20261007_092525.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 บทที่ 11 Shortest Path, Unweighted Graph, เฉลย Assignment 4, ประกาศข้อสอบ Final 7 ข้อ
│   └── DSA-pic/                                                  <-- คลังภาพกระดานและสไลด์ 106 ภาพ (เชื่อมโยงกับการบรรยาย)
│
├── 04_Computer_Graphics_Design\                                  <-- วิชาคอมพิวเตอร์กราฟิกส์ (Adobe Illustrator)
│   ├── README.md                                                 <-- สรุปกฎสอบ 9.00-12.00 น., ให้เน็ต 10 นาที
│   ├── Transcript_20260302_Final_Exam_Briefing.md                <-- บทวิเคราะห์ข้อสอบปฏิบัติ 4 ข้อ 300 คะแนน
│   └── 20260302_093603.txt                                       <-- [ถอดความละเอียดทุกคำพูด] ชี้แจงข้อสอบ 4 ข้อ
│
├── 05_Technical_English\                                         <-- วิชาภาษาอังกฤษเชิงเทคนิคเพื่อการสื่อสาร
│   ├── README.md                                                 <-- สรุปบทพูดนำเสนอ Custom PC
│   ├── Transcript_20260223_Presentation_Practice_Coaching.md     <-- บทวิเคราะห์การซ้อมพรีเซนต์
│   └── 20260223_143626.txt                                       <-- [ถอดความละเอียดทุกคำพูด] ซ้อมพรีเซนต์เดี่ยว
│
├── 06_Personal_Financial_Trading\                                <-- การเงินส่วนบุคคล / การลงทุนเทรดดิ้ง (Forex & MT5 EA)
│   ├── README.md                                                 <-- สรุปเงื่อนไขโบนัสเทรดครบ 5 ออเดอร์
│   ├── Transcript_20260409_Broker_MT5_EA_Support.md              <-- บทวิเคราะห์การสนทนากับฝ่ายบริการลูกค้า
│   └── 20260409_105602.txt                                       <-- [ถอดความละเอียดทุกคำพูด] คุยกับโบรกเกอร์ MT5 EA
│
├── 07_Software_Engineering\                                      <-- วิชาวิศวกรรมซอฟต์แวร์ (Software Engineering - UML)
│   ├── README.md                                                 <-- สรุปวิชา, Use Case & Activity Diagram, include vs extend
│   ├── Transcript_20260915_092638_UseCase_Diagram.md             <-- บทวิเคราะห์ Use Case Diagram, System Boundary
│   ├── Transcript_20260922_SE_UseCase_Activity_Diagram_Exam_Secrets.md <-- 🔥 บทวิเคราะห์ Case Study ระบบยืมคืนอุปกรณ์, Activity Diagram, ข้อสอบ Final
│   ├── Transcript_20261006_SE_Final_Exam_5_Items_Leak_Scrum_Testing_Complexity.md <-- 🔥 บทวิเคราะห์ชี้แจงข้อสอบ Final 5 ข้อใหญ่ 100% EXPLICIT LEAKS, EP/BVA, Cyclomatic, Burn-down
│   ├── SE20260915_092638.txt                                     <-- [ถอดความละเอียดทุกคำพูด] บรรยาย Use Case Diagram
│   ├── 20260922_093313.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 Case Study ยืมคืนอุปกรณ์, Activity Diagram สัญลักษณ์ครบ
│   ├── 20261006_094018.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 ข้อสอบ Final 5 ข้อใหญ่, Open Book, Dictionary, เฉลยการบ้านยืมคืนอุปกรณ์แล็บ
│   ├── images/
│   │   ├── IMG_20261006_100254_624@1909396080.jpg           <-- 📸 ภาพถ่ายกระดานขณะบรรยายสด 10:02 น. สรุปข้อสอบ 5 ข้อ
│   │   └── Screenshot_2026-10-07_083942.png                 <-- 📢 ภาพแคปหน้าจอประกาศทางการ Google Classroom
│
├── 08_Computer_Networks_and_Internet\                            <-- วิชาเครือข่ายคอมพิวเตอร์และอินเทอร์เน็ต (Network & Link Layer)
│   ├── README.md                                                 <-- สรุปวิชา, Distance Vector, BGP, CRC, MAC Protocols
│   ├── Transcript_20260914_Network_Routing_DistanceVector_BGP.md <-- บทวิเคราะห์ Routing Algorithm, Bellman-Ford, Count-to-Infinity, BGP
│   ├── Transcript_20260921_LinkLayer_CRC_MAC_Protocols.md        <-- 🔥 บทวิเคราะห์ Link Layer, ตรวจจับ Error (Parity, Checksum, CRC), Multiple Access Protocols
│   ├── 20260914_132959.txt                                       <-- [ถอดความละเอียดทุกคำพูด] บทที่ 5: Distance Vector & Hierarchical Routing
│   └── 20260921_135415.txt                                       <-- [ถอดความละเอียดทุกคำพูด] 🔥 บทที่ 6: Link Layer, การตั้งหาร CRC, TDMA, CSMA/CD, สั่งการบ้าน
│
└── Success\                                                      <-- แหล่งจัดเก็บไฟล์เสียงต้นฉบับทั้ง 44 ไฟล์ที่ประมวลผลเสร็จแล้ว (.aac / .m4a)
```

---

## 📊 ตารางแสดงความสัมพันธ์ของไฟล์เสียงทั้งหมด 42 ไฟล์ (Master Mapping Table)

| ลำดับ | ชื่อไฟล์เสียง (จัดเก็บใน `Success/`) | วันที่บันทึก | ความยาว | หมวดหมู่วิชา / โฟลเดอร์ | สาระสำคัญ / การดำเนินการ |
| :---: | :--- | :---: | :---: | :--- | :--- |
| 1 | `20260126_162937.aac` | 26/01/2569 | 2m 48s | `01_Innovative_Technopreneurs` | สัมภาษณ์ Customer Validation #1 Smart Green Wall |
| 2 | `20260126_164100.aac` | 26/01/2569 | 2m 41s | `01_Innovative_Technopreneurs` | สัมภาษณ์ Customer Validation #2 Smart Green Wall |
| 3 | `20260223_143626.aac` | 23/02/2569 | 26m 21s | `05_Technical_English` | ซ้อมบทพูดพรีเซนต์เดี่ยว Custom PC |
| 4 | `20260302_093603.aac` | 02/03/2569 | 5m 16s | `04_Computer_Graphics_Design` | ชี้แจงข้อสอบปฏิบัติปลายภาค 4 ข้อ 300 คะแนน |
| 5 | `20260409_105602.aac` | 09/04/2569 | 2m 23s | `06_Personal_Financial_Trading` | ฝ่ายบริการลูกค้าโบรกเกอร์ ถอนกำไร MT5 EA |
| 6 | `20260902_091736.aac` | 02/09/2569 | 29m 51s | `03_Data_Structures_and_Algorithms` | บทที่ 7 Hashing: Separate Chaining & Linear Probing |
| 7 | `20260902_094834.aac` | 02/09/2569 | 31m 43s | `03_Data_Structures_and_Algorithms` | บทที่ 7 Hashing: Quadratic Probing & Double Hashing |
| 8 | `20260902_104259.aac` | 02/09/2569 | 0m 02s | `03_Data_Structures_and_Algorithms` | เสียงช่วงพักเบรกสั้น 2 วินาที |
| 9 | `20260902_104304.aac` | 02/09/2569 | 23m 49s | `03_Data_Structures_and_Algorithms` | สรุปภาพรวม Hashing เตรียมขึ้น Heap |
| 10 | `20260902_110748.aac` | 02/09/2569 | 7m 09s | `03_Data_Structures_and_Algorithms` | บทที่ 8 Priority Queue: นิยามคิวและการแซงคิว |
| 11 | `20260902_111515.aac` | 02/09/2569 | 6m 36s | `03_Data_Structures_and_Algorithms` | บทที่ 8 Heap กองทราย และ Min-Heap |
| 12 | `20260902_112213.aac` | 02/09/2569 | 4m 01s | `03_Data_Structures_and_Algorithms` | Complete Binary Tree ใส่ซ้ายไปขวา ลบขวาไปซ้าย |
| 13 | `20260902_112628.aac` | 02/09/2569 | 10m 42s | `03_Data_Structures_and_Algorithms` | **🔥 ข้อสอบข้อ 2:** คำนวณโหนดความสูง 10 (1024/2047) |
| 14 | `20260902_113741.aac` | 02/09/2569 | 7m 02s | `03_Data_Structures_and_Algorithms` | สูตร Array 1D: Root=1, Left=2i, Right=2i+1, Parent=floor(i/2) |
| 15 | `20260904_105814.aac` | 04/09/2569 | 9m 10s | `01_Innovative_Technopreneurs` | โครงสร้างรายงาน 10 หัวข้อ, กฎ BMC 1 หน้า |
| 16 | `20260908_130406.aac` | 08/09/2569 | 6m 21s | `02_Database_System` | นิยาม Transaction, ชนิดไฟล์ Master/Transaction |
| 17 | `20260908_131052.aac` | 08/09/2569 | 67m 08s | `02_Database_System` | บรรยายหลัก ACID, Concurrency, Lock Matrix S/X |
| 18 | `20260908_143913.aac` | 08/09/2569 | 17m 15s | `02_Database_System` | **🔥 Pop Quiz:** ACID & Lock Matrix & Log Crash |
| 19 | `-.aac` | 08/09/2569 | 17m 15s | `02_Database_System` | *ไฟล์ซ้ำ* ตรงกับ `20260908_143913.aac` |
| 20 | `dsa20260909_092220.aac`| 09/09/2569 | 0m 36s | `03_Data_Structures_and_Algorithms` | ทบทวนสูตร Array และย้ำข้อสอบออก Array |
| 21 | `dsa20260909_092303.aac`| 09/09/2569 | 50m 01s | `03_Data_Structures_and_Algorithms` | **🔥 ข้อสอบปลายภาค:** ไล่โค้ด BinaryHeap, insert |
| 22 | `20260909_103704.aac` | 09/09/2569 | 81m 39s | `03_Data_Structures_and_Algorithms` | **🔥 ข้อสอบปลายภาค:** ไล่โค้ด deleteMin 3 รอบ |
| 23 | `In20260911_114230.aac` | 11/09/2569 | 2m 23s | `01_Innovative_Technopreneurs` | การบริหารความเสี่ยงร้านกาแฟ |
| 24 | `20260914_132959.aac` | 14/09/2569 | 84m 12s | `08_Computer_Networks_and_Internet` | **🔥 Routing Algorithms:** Distance Vector, Bellman-Ford |
| 25 | `20260914_153152.aac` | 14/09/2569 | 16m 28s | `08_Computer_Networks_and_Internet` | **🔥 BGP Routing:** Count-to-Infinity & Autonomous Systems |
| 26 | `SE20260915_092638.aac`| 15/09/2569 | 60m 27s | `07_Software_Engineering` | บรรยาย Use Case Diagram ระบบห้องสมุด |
| 27 | `20260915_130022.aac` | 15/09/2569 | 67m 51s | `02_Database_System` | NoSQL, Big Data (5 Vs), CAP Theorem |
| 28 | `20260916_092007.aac` | 16/09/2569 | 44m 43s | `03_Data_Structures_and_Algorithms` | **🔥 Sorting Part 1:** Insertion Sort, Position Move |
| 29 | `20260916_102037.aac` | 16/09/2569 | 68m 45s | `03_Data_Structures_and_Algorithms` | **🔥 Sorting Part 2:** Selection Sort, Bubble Sort, Inversion |
| 30 | `20260921_135415.aac` | 21/09/2569 | 9m 31s | `08_Computer_Networks_and_Internet` | Data Link Layer บทนำ & NIC Controller |
| 31 | `20260921_140424.aac` | 21/09/2569 | 74m 43s | `08_Computer_Networks_and_Internet` | **🔥 Error Detection:** Parity 1D/2D, Checksum, CRC |
| 32 | `20260921_153320.aac` | 21/09/2569 | 31m 53s | `08_Computer_Networks_and_Internet` | **🔥 Multiple Access:** TDMA, Slotted ALOHA 37%, CSMA/CD |
| 33 | `20260921_160636.aac` | 21/09/2569 | 0m 57s | `08_Computer_Networks_and_Internet` | มอบหมายการบ้าน CRC ส่งก่อนเที่ยงคืนวันอังคาร |
| 34 | `20260922_093313.aac` | 22/09/2569 | 40m 52s | `07_Software_Engineering` | **🔥 ข้อสอบ Final:** Use Case Case Study ยืมคืนอุปกรณ์ |
| 35 | `20260922_102855.aac` | 22/09/2569 | 28m 36s | `07_Software_Engineering` | **🔥 Activity Diagram:** Start, Stop, Action, Guard, Decision |
| 36 | `20260922_105854.aac` | 22/09/2569 | 23m 33s | `07_Software_Engineering` | **🔥 Activity Diagram:** Fork, Join, Swimlanes, Login Flow |
| 37 | `20260922_131058.aac` | 22/09/2569 | 81m 15s | `02_Database_System` | **🔥 DB Lab:** XAMPP MariaDB CLI, utf8mb4, PK/FK Constraints |
| 38 | `20260922_150154.aac` | 22/09/2569 | 45m 48s | `02_Database_System` | **🔥 จุดตาย ERROR 1074:** CHAR(500) เกิน 255 ต้องใช้ VARCHAR |
| 39 | `20260923_091645.aac` | 23/09/2569 | 147m 52s| `03_Data_Structures_and_Algorithms` | **🔥 บทที่ 10 Graph Theory:** 14 ภาพกระดาน, ข้อสอบรั่ว Complete Graph 45 เส้น, Adjacency Matrix สิ้นเปลือง 75.51% vs List 30 ช่อง |
| 40 | `20260925_093530.aac` | 25/09/2569 | 79m 33s | `01_Innovative_Technopreneurs` | **🔥 บทที่ 10 Part 1:** โครงสร้างองค์กร, ภาษีซ้ำซ้อน (Double Taxation), 5 รูปแบบธุรกิจ, CNV 4 โมเดล, Intrapreneurship, 15% Rule ของ 3M, สถาปัตยกรรมทีม (Founders, BOD, Advisory), ลิขสิทธิ์ vs สิทธิบัตร |
| 41 | `20260925_105917.aac` | 25/09/2569 | 11m 04s | `01_Innovative_Technopreneurs` | **🔥 บทที่ 10 Part 2:** เครื่องหมายรับรอง (อย./มอก./ฮาลาล), เครื่องหมายร่วม (SCG), ความลับทางการค้า (KFC/Coke), Reverse Engineering, การบังคับใช้สิทธิ์ (CL สิทธิบัตรยา), การสิ้นสิทธิ & การนำเข้าซ้อน |
| 42 | `database 29_9_2569 14.25.m4a` | 29/09/2569 | 68m 16s | `02_Database_System` | **🔥 DB Lab Week 2 & พรีเซนต์:** Foreign Key CASCADE vs RESTRICT, การบ้าน SQL (P.40-P.41+ เขียนมือ), นัดตรวจ ER พรุ่งนี้ 10:30 น., ผลสุ่มกงล้อพรีเซนต์โครงงานห้อง 307 และเลื่อนสอบปลายภาค |
| 43 | `20261006_094018.aac` | 06/10/2569 | 45m 59s | `07_Software_Engineering` | **🔥 ชี้แจงข้อสอบปลายภาค 5 ข้อใหญ่ 100% EXPLICIT LEAKS:** Open Book + Dictionary, Case Study Actor & Role, Use Case Diagram, Activity Diagram, Software Testing (EP & BVA), Cyclomatic Complexity ($V(G)$ 3 วิธี) & Independent Paths, Agile/Scrum Roles, Burn-down Chart, เฉลยการบ้านระบบแล็บ และเกณฑ์ตัดเกรดอิงเกณฑ์ (A=80) |
| 44 | `20261006_161408.aac` | 06/10/2569 | 7m 34s | `02_Database_System` | **🔥 กฎเหล็กสอบ Final & Negative Marking:** ข้อสอบปรนัย 80 ข้อ (40 คะแนน), Open Book, กฎติดลบ: ถูก 2 ข้อได้ 1 แต้ม / ผิด 2 ข้อหัก 1 แต้ม, ศัพท์เทคนิคอังกฤษ, เตรียมดินสอ 2B ฝน, ส่ง ER Diagram 2 ช่องใน Classroom (หลังมิดเทอม vs Final ฉบับแก้), เทคนิคพรีเซนต์ Total/Partial vs Cardinality |
| 45 | `20261007_092525.aac` | 07/10/2569 | 151m 18s| `03_Data_Structures_and_Algorithms` | **🔥 บทที่ 11 Shortest Path & ข้อสอบปลายภาค 7 ข้อ 70 คะแนน:** Topological Sort Tracing, Unweighted Shortest Path (BFS + Queue), ตารางสถานะ Known, Dist, Path, การ Backtrack เส้นทาง, เฉลย Assignment 4 ส่งเที่ยง, ประกาศแนวข้อสอบ Final 7 ข้อ Open Book + เครื่องคิดเลข (35%) |

---

## 📅 ปฏิทินวันเวลา กำหนดการส่งงาน และกิจกรรมสำคัญ (Master Deadlines Calendar)

| วันที่ตามกำหนด | เวลา | วิชาที่เกี่ยวข้อง | กิจกรรม / สิ่งที่ต้องส่ง / ข้อกำหนด |
| :--- | :--- | :--- | :--- |
| **22/09/2569** | **23:59 น. (เที่ยงคืน)** | Software Engineering | **ส่ง Use Case Diagram เวิร์กช็อป:** ออกแบบระบบยืม-คืนอุปกรณ์ห้องปฏิบัติการ (Student/Staff $\rightarrow$ Member, Include, Extend) ผ่าน Google Classroom |
| **22/09/2569** | **23:59 น. (เที่ยงคืน)** | Computer Networks | **ส่งการบ้านคำนวณ CRC:** แสดงขั้นตอนการตั้งหาร XOR หาเศษ CRC จาก $D = 100100$ และ $G = x^3+1 (1001)$ ส่งผ่าน Google Classroom |
| **27/09/2569** | **23:59 น. (เที่ยงคืน)** | Data Structures & Algorithms | **ส่ง Take-Home Programming Assignment 2 (5 คะแนน):** เขียนโปรแกรมเปรียบเทียบ Insertion, Selection, Bubble Sort ในภาษา Python พร้อม Trace สลับ/ขยับแต่ละรอบและจำนวนครั้ง |
| **30/09/2569** | **10:30 น.** | Database System | **นัดตรวจร่างแบบ ER Diagram:** พบ ดร.สวาท ณ ห้องพักอาจารย์ภาควิชาเทคโนโลยีสารสนเทศ (ชั้น 1 หรือ ชั้น 4) |
| **01/10/2569** | **ก่อน 12.00 น. (เที่ยง)** | Innovative Technopreneurs | **ส่งไฟล์ดิจิทัลทาง LINE กลุ่มวิชา:** เล่มรายงานฉบับสมบูรณ์ (PDF) และสไลด์นำเสนอ (PDF) |
| **02/10/2569** | ในคาบเรียน | Innovative Technopreneurs | **ส่งรูปเล่มรายงานฉบับพิมพ์ Hard Copy ทุกกลุ่ม + พรีเซนต์กลุ่ม 1-9** |
| **06/10/2569** | **13:00 น. เป็นต้นไป** | Database System | **🔥 นำเสนอโครงงาน Database ตอนเรียนวันอังคาร (Section 2 - 15 กลุ่ม):** ณ **ห้องทฤษฎี 307** (กลุ่มละ 15-20 นาที) + ส่งเล่มรายงาน Hard Copy + ส่งการบ้านแบบฝึกหัด SQL (เขียนมือ ห้ามพิมพ์) |
| **07/10/2569** | **ก่อน 12:25 น.** | Data Structures & Algorithms | **🔥 ส่ง Assignment 4 ใน Google Classroom (5 คะแนน):** กราฟ Shortest Path จุดเริ่มต้น A แปลง Adjacency List และเขียนตาราง Known, Dist, Path, Queue แสดงรอยขีดฆ่าด้วยลายมือตนเอง |
| **08/10/2569** | **09:00 น. เป็นต้นไป** | Database System | **🔥 นำเสนอโครงงาน Database ตอนเรียนวันพฤหัสบดี (Section 1 - 12 กลุ่ม):** ณ **ห้องทฤษฎี 307** (กลุ่มละ 15-20 นาที) + ส่งเล่มรายงาน Hard Copy + ส่งการบ้านแบบฝึกหัด SQL (เขียนมือ ห้ามพิมพ์) |
| **09/10/2569** | ในคาบเรียน | Innovative Technopreneurs | **การนำเสนอผลงานรอบที่ 2 (กลุ่ม 10-18)** |
| **09/10/2569** | สิ้นสุดคาบเรียน | ทุกวิชา | **วันสุดท้ายของการเรียนการสอนประจำภาคเรียนที่ 1/2569** |
| **12-16/10/2569** | ทั้งสัปดาห์ | ทุกวิชา | **วันหยุดราชการกรณีพิเศษ (งดการเรียนการสอนและงดสอบ):** ประเทศไทยเป็นเจ้าภาพจัดประชุมธนาคารโลก & IMF ณ ศูนย์ฯ สิริกิติ์ |
| **19/10 - 01/11/2569**| 2 สัปดาห์เต็ม | ทุกวิชา | **ช่วงเวลาสอบปลายภาค (Final Examination Period):** มีการจัดสอบวันเสาร์-อาทิตย์ด้วย (วิชา Database จะสรุปรูปแบบ Open Book ในคาบพรีเซนต์) |

---

## 🎯 คลังจุดเน้นย้ำและแนวข้อสอบรั่วฉบับอัปเดต (Master Exam Secrets & Leaks)

### 1. Data Structures & Algorithms (ดร.ประดิษฐ์ พิทักษ์เสถียรกุล)
1. **ข้อสอบ Complete Graph คำนวณเส้น:** $E = \frac{V(V-1)}{2}$ หากโจทย์ถาม $V = 10$ **ต้องตอบจำนวนเต็ม 45 เท่านั้น! ห้ามตอบติดสูตร** (ตอบติดสูตรได้ 0 คะแนน)
2. **ข้อสอบการเขียน Path:** จงเขียน Path จาก $A$ ไปยัง $C$ **ต้องตอบ `$A, B, C$` หรือ `(A, B, C)` คั่นด้วยจุลภาคเท่านั้น ห้ามตอบเป็นลูกศร `$A \rightarrow B \rightarrow C$` เด็ดขาด (ได้ 0 คะแนนทันที)**
3. **ข้อสอบหน่วยของความยาว Path:** ตอบเป็นจำนวน **"เส้น" (Edges)** ไม่ใช่หน่วยวัดความยาวไม้บรรทัด
4. **ข้อสอบคำถามบน Null Graph ($V=\{\}, E=\{\}$):** ถาม Path จาก $A$ ไป $C$ ให้ตอบว่า **"ไม่มี Path จาก $A$ ไป $C$ เพราะไม่มีโหนด $A$ และ $C$ อยู่ในกราฟ"**
5. **ข้อสอบคำนวณ Memory Waste ของ Adjacency Matrix:**
   - กราฟ 7 จุด 12 เส้น ขนาด $7 \times 7 = 49$ ช่อง
   - ช่องเลข 1 คิดเป็น: $\frac{12 \times 100}{49} = \mathbf{24.48\%}$
   - ช่องเลข 0 (สูญเปล่า): $\frac{37 \times 100}{49} = \mathbf{75.51\%}$
6. **ข้อสอบเปรียบเทียบ Matrix vs List (10 Vertices, 20 Edges):**
   - Adjacency Matrix ใช้: $|V|^2 = 10^2 = \mathbf{100\text{ ช่อง}}$
   - Adjacency List ใช้: $|E| + |V| = 20 + 10 = \mathbf{30\text{ ช่อง}}$ (ประหยัดกว่า 70%)

### 2. Database System (ดร.สวาท)
1. **🔥 กฎเหล็กข้อสอบปลายภาค 80 ข้อ (40 คะแนน) Open Book:**
   - ข้อสอบเป็น **ปรนัย (Multiple Choice) 80 ข้อ** เก็บ 40 คะแนนเต็ม
   - **Negative Marking Penalty (กฎติดลบ):** ทำถูก 2 ข้อได้ 1 แต้ม / **ทำผิด 2 ข้อ หัก 1 แต้ม (-0.5 ต่อข้อ)!** หากไม่มั่นใจห้ามเดาสุ่มเด็ดขาด ให้เว้นว่างไว้จะไม่โดนหัก
   - **Open Book:** นำเอกสาร ตำรา และสรุปเข้าห้องสอบได้ทุกชนิด
   - **อุปกรณ์บังคับ:** ดินสอ 2B สำหรับฝนกระดาษคำตอบ, ยางลบดินสอ, ปากกา, ลิควิด
   - **ส่ง ER Diagram ใน Classroom 2 ช่อง:** ช่องหลังมิดเทอม (ไฟล์เดิม) และช่อง Final (ไฟล์ฉบับปรับปรุง)
2. **จุดตาย ERROR 1074:** คำสั่ง `ALTER TABLE Title MODIFY COLUMN TitleDescription CHAR(500);` ล้มเหลวเพราะ `CHAR` รองรับความยาวสูงสุดเพียง **255 ตัวอักษร** ต้องแก้ไขเป็น `VARCHAR(500)` หรือ `TEXT`
3. **Character Set utf8mb4:** ต้องระบุ `CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci` เพื่อรองรับภาษาไทยและ Emoji ให้ครบ 4 ไบต์ ป้องกันข้อความกลายเป็น `?`
4. **ความแตกต่างระหว่าง CASCADE vs RESTRICT:**
   - `CASCADE`: ลบ/อัปเดตตารางแม่แล้วตารางลูกโดนด้วยอัตโนมัติ
   - `RESTRICT`: ห้ามลบ/อัปเดตตารางแม่เด็ดขาดหากยังมีตารางลูกอ้างอิงอยู่ (`ERROR 1451 (23000)`)
5. **การนำเสนอ E-R Diagram:** ให้เลือกอธิบายความสัมพันธ์แบบเดียวที่กลุ่มถนัด เช่น **Total / Partial Participation** (ชัดเจนและไม่สับสน) หรือ Cardinality Ratio ห้ามอธิบายปนกันจนขัดแย้ง

### 3. Software Engineering
1. **🔥 โครงสร้างข้อสอบปลายภาค 5 ข้อใหญ่ 30 คะแนน (100% EXPLICIT LEAKS):**
   - **Item 1:** Case Study ภาษาอังกฤษ (~10 บรรทัด) $\rightarrow$ Part A: ค้นหา Actor พร้อมระบุ Role (ห้ามตอบเกินช่องที่ล็อกไว้) + Part B: วาด Use Case Diagram ครบทุกความสัมพันธ์
   - **Item 2:** Case Study มีขั้นตอน 1-2-3 ชัดเจน $\rightarrow$ วาด Activity Diagram ครบทุกสัญลักษณ์ (Start, End, Action, Decision, Fork/Join, Swimlanes)
   - **Item 3:** Software Testing $\rightarrow$ Part A: Equivalence Partitioning (EP), Part B: Boundary Value Analysis (BVA), Part C: ระบุชื่อและหลักการกระบวนการ
   - **Item 4:** Software Complexity Metrics $\rightarrow$ โค้ด Python 5 บรรทัด + กราฟ Control Flow Graph (มีให้แล้ว) คำนวณ Cyclomatic Complexity ($V(G)$) 3 วิธี ($E-N+2P$, Regions, Predicates+1) และระบุเส้นทางอิสระ (Independent Paths)
   - **Item 5:** Agile & Scrum & Burn-down Chart $\rightarrow$ Part A: ระบุหน้าที่บทบาท Product Owner, Scrum Master, Dev Team + Part B: อ่านและวิเคราะห์กราฟ Burn-down Chart
2. **กฎการสอบและการตัดเกรด:** Open Book นำเอกสารและพจนานุกรมเข้าได้, ตัดเกรดอิงเกณฑ์ (A $\ge$ 80, B+ $\ge$ 75, B $\ge$ 70, C+ $\ge$ 65, C $\ge$ 60, D+ $\ge$ 55, D $\ge$ 50, F < 50)
3. **สัญลักษณ์ UML แม่นยำ:**
   - Generalization: สามเหลี่ยมโปร่ง $\triangle$ ชี้เข้าหาคลาสแม่ (`Student` / `Staff` $\rightarrow$ `Member`)
   - `<<include>>`: ชี้จาก Use Case หลัก $\rightarrow$ Use Case บังคับที่ต้องเรียกใช้เสมอ
   - `<<extend>>`: ชี้จาก Use Case เงื่อนไขทางเลือก $\rightarrow$ Use Case หลัก

### 4. Computer Networks & Internet (ดร.วรลักษณ์)
1. **การคำนวณ CRC:** ตั้งหารแบบ Modulo-2 XOR ไม่มีการยืมบิต ตัวหารความยาว $L$ บิต ต้องเติมศูนย์ต่อท้ายข้อมูล $L-1$ บิต เศษที่ได้คือ CRC
2. **การแปลง Polynomial:** พจน์ที่ไม่มีสัมประสิทธิ์ต้องแทนด้วยบิต `0` เช่น $x^3 + 1 \rightarrow 1 0 0 1$
3. **Multiple Access Protocols:** Slotted ALOHA มีประสิทธิภาพสูงสุดเพียง **37% ($1/e$)**, CSMA/CD ใช้บนสายแลน Ethernet (ฟังก่อนส่ง + ตรวจจับการชนขณะส่ง)
4. **Bellman-Ford Distance Vector:** $d_x(y) = \min_v \{ c(x,v) + d_v(y) \}$, จุดอ่อนคือปัญหา Count-to-Infinity แก้ด้วย Split Horizon

### 5. Innovative Technopreneurs (ผู้ประกอบการนวัตกรรม)
1. **การเปรียบเทียบภาษี (Tax Comparison):**
   - บริษัทจำกัด (Taxable Entity) เกิด **Double Taxation** (ภาษีนิติบุคคล + ภาษีบุคคลธรรมดาจากเงินปันผล) แต่ได้ประโยชน์จากการจำกัดความรับผิด (Limited Liability)
   - เจ้าของคนเดียว / ห้างหุ้นส่วน (Flow-Through Entity) กำไรไหลผ่านไปคิดภาษีบุคคลโดยตรง แต่มีความรับผิดชอบในหนี้สินไม่จำกัด (Unlimited Liability)
2. **ความแตกต่างระหว่างสิทธิบัตรการประดิษฐ์ vs อนุสิทธิบัตร:**
   - **สิทธิบัตรการประดิษฐ์:** ต้องมี Inventive Step ขั้นสูง คุ้มครอง **20 ปี** (ต่ออายุไม่ได้ เมื่อหมดอายุตกเป็นสมบัติสาธารณะ)
   - **อนุสิทธิบัตร:** ปรับปรุงเล็กน้อย ไม่ต้องมีขั้นการประดิษฐ์สูงขึ้น คุ้มครอง **6 ปี** (ต่ออายุได้ 2 ครั้ง ครั้งละ 2 ปี รวมสูงสุด **10 ปี**)
3. **อายุการคุ้มครองทรัพย์สินทางปัญญา:**
   - ลิขสิทธิ์ = ตลอดอายุผู้สร้างสรรค์ + **50 ปี** (คุ้มครองอัตโนมัติ ไม่ต้องจดทะเบียน)
   - เครื่องหมายการค้า = **10 ปี** (ต่ออายุได้คราวละ 10 ปี ไม่จำกัดจำนวนครั้ง)
   - ความลับทางการค้า = **ตลอดไป** ตราบเท่าที่ยังเป็นความลับทางการค้า
4. **ความชอบธรรมทางกฎหมายของ Reverse Engineering:**
   - การทำวิศวกรรมย้อนกลับ (Reverse Engineering) **ไม่ถือเป็นการละเมิดความลับทางการค้า** หากได้สินค้านั้นมาอย่างถูกต้องตามกฎหมาย เว้นแต่จะมีสัญญาข้อตกลงห้ามแกะไว้ล่วงหน้า
5. **การบังคับใช้สิทธิ์ (Compulsory Licensing - CL):**
   - รัฐมีอำนาจสั่งบังคับใช้สิทธิบัตรยาเพื่อประโยชน์สาธารณสุขได้โดยไม่ถือว่าละเมิดสิทธิบัตร เจ้าของสิทธิบัตรเดิมยังคงเป็นเจ้าของสิทธิบัตรอยู่
6. **การสิ้นสิทธิ (Exhaustion of Rights) & การนำเข้าซ้อน:**
   - การนำเข้าซ้อน (Parallel Importation / สินค้าหิ้วแท้) **ถูกต้องตามกฎหมาย** เพราะสิทธิเด็ดขาดของเจ้าของในสินค้านั้นสิ้นสุดลงนับแต่การขายครั้งแรก (First-sale Doctrine)
