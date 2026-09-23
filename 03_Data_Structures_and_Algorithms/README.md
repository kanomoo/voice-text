# สรุปภาพรวมและสารบัญหลัก: วิชาโครงสร้างข้อมูลและขั้นตอนวิธี (Data Structures and Algorithms)

**หมวดหมู่วิชา:** วท.บ. วิทยาการคอมพิวเตอร์ / เทคโนโลยีสารสนเทศ  
**ผู้บรรยาย:** อาจารย์ประจำวิชา (ดร.ประดิษฐ์ พิทักษ์เสถียรกุล)  
**โฟลเดอร์ปฏิบัติการ:** `C:\Project\Voice\03_Data_Structures_and_Algorithms\`  
**คลังภาพประกอบการสอน:** `C:\Project\Voice\DSA-pic\` (สไลด์, เอกสาร Word, โค้ด VS Code และภาพกระดานรวม 106 ภาพ)  

---

## 📑 สารบัญเอกสารวิเคราะห์และถอดความอย่างละเอียด (Detailed Lecture Documents)

1. 📘 [Transcript_20260902_Hashing_Lecture.md](file:///C:/Project/Voice/03_Data_Structures_and_Algorithms/Transcript_20260902_Hashing_Lecture.md)  
   - **บทที่ 7: ตารางแฮชและการแก้ปัญหาการชน (Hashing, Collision Resolution & Rehashing)**
   - วิเคราะห์เจาะลึก: Separate Chaining, Open Addressing, Linear Probing ($F(i)=i$), Quadratic Probing ($F(i)=i^2$), Double Hashing ($F(i)=i \cdot (R - (x \bmod R)), R=7$), Primary/Secondary Clustering, และการทำ Rehashing ขยายตาราง 7 เป็น 17 ช่อง พร้อมกฎอ่านข้อมูลจากบนลงล่าง
2. 📘 [Transcript_20260902_PriorityQueue_BinaryHeap.md](file:///C:/Project/Voice/03_Data_Structures_and_Algorithms/Transcript_20260902_PriorityQueue_BinaryHeap.md)  
   - **บทที่ 8: คิวลำดับความสำคัญและโครงสร้างฮีป (Priority Queue & Binary Heap Properties)**
   - วิเคราะห์เจาะลึก: เปรียบเทียบ FIFO Queue vs Priority Queue, ที่มาของรูปทรง Heap (กองดินกองทรายพีระมิด), Structure Property (Complete Binary Tree), Heap-Order Property (Min-Heap: Parent $\le$ Children)
3. 📘 [Transcript_20260902_Exam_Focus_Node_Calculation.md](file:///C:/Project/Voice/03_Data_Structures_and_Algorithms/Transcript_20260902_Exam_Focus_Node_Calculation.md)  
   - **เจาะลึกข้อสอบข้อ 2: การคำนวณจำนวนโหนดและการแปลง Tree เป็น 1D Array**
   - วิเคราะห์เจาะลึก: พิสูจน์สูตรช่วงโหนด $2^H \le N \le 2^{H+1}-1$, เฉลยข้อสอบตรง $H=10 \rightarrow \text{Min}=1024, \text{Max}=2047$ (ห้ามตอบติดเลขยกกำลัง), สูตรโครงสร้าง Array 1 มิติ (Root=1, Left=$2i$, Right=$2i+1$, Parent=$\lfloor i/2 \rfloor$)
4. 📘 [Transcript_20260909_BinaryHeap_Implementation_Exam_Tips.md](file:///C:/Project/Voice/03_Data_Structures_and_Algorithms/Transcript_20260909_BinaryHeap_Implementation_Exam_Tips.md)  
   - **เจาะลึกข้อสอบปลายภาค: การไล่โค้ด Python Binary Heap, การแทรก และการลบ**
   - วิเคราะห์เจาะลึก: คลาส `BinaryHeap`, การสร้าง `[None] * (capacity + 1)`, ตาราง Trace ทีละสเต็ปของ `insert(14)` (Percolate Up), ตาราง Trace ของ `deleteMin()` (Percolate Down), เผยไต๋ข้อสอบปลายภาคออก **DeleteMin 3 ครั้งรวด** และเทคนิคทำเสร็จใน 5-10 นาที
5. 📘 [Transcript_20260916_Comparison_Sorting_Insertion_Selection_Bubble_Exam_Trace.md](file:///C:/Project/Voice/03_Data_Structures_and_Algorithms/Transcript_20260916_Comparison_Sorting_Insertion_Selection_Bubble_Exam_Trace.md)  
   - **บทที่ 9: การเรียงลำดับข้อมูลแบบเปรียบเทียบ (Comparison-based Sorting: Insertion, Selection, Bubble Sort) และเฉลยข้อสอบใบงาน**
   - วิเคราะห์เจาะลึก: กลไก `temp` และการเปรียบเทียบถอยหลังของ Insertion Sort, การนับ Position Move และสูตร Best/Worst Case ($\frac{N(N-1)}{2}$), การแบ่ง Sorted/Unsorted Part ของ Selection Sort, โครงสร้างหน่วยความจำ `range(0)` vs `[]`, การลอยตัวของ Bubble Sort, สูตรลัด Inversion Counting หา Total Swaps, และเฉลยใบงาน Bubble Sort อาร์เรย์ `[64, 34, 25, 12, 22, 11, 90]` (6 passes, 14 swaps, Pass 1 trace)
6. 📘 [Transcript_20260923_Graph_Theory_Representations_Exam_Leaks.md](file:///C:/Project/Voice/03_Data_Structures_and_Algorithms/Transcript_20260923_Graph_Theory_Representations_Exam_Leaks.md)  
   - **บทที่ 10: ทฤษฎีกราฟ, โครงสร้าง Adjacency Matrix/List และเจาะลึกแนวข้อสอบปลายภาค 45 เส้น (Graph Theory Exam Leaks & Shortcuts)**
   - วิเคราะห์เจาะลึก: ประกาศ Drop เกือบ 100 คน, งดเรียน/สอบประชุม IMF & World Bank 12-16 ต.ค. เลื่อนสอบ Final 19 ต.ค. - 1 พ.ย. 69 (35%), นิยาม Adjacent/Path, กฎเหล็กเขียน Path ห้ามใส่ลูกศร (0 คะแนน), ข้อสอบ Complete Graph 10 Vertices ตอบจำนวนเต็ม 45 เส้น, จุดหลอก Null Graph, ตาราง Matrix 7x7 เปลืองพื้นที่ 75.51% vs List 19 ช่อง (ประหยัด 61.22%), และข้อสอบเปรียบเทียบ 10 Vertices 20 Edges (Matrix 100 vs List 30 ช่อง ประหยัด 70%)

---

## 📋 รายการไฟล์เสียงต้นฉบับในโฟลเดอร์นี้

| ชื่อไฟล์เสียง | วันที่บันทึก | ความยาว | หัวข้อการสอนหลัก |
| :--- | :--- | :--- | :--- |
| `20260902_091736.aac` | 02/09/2569 09:17 น. | 29 นาที 51 วินาที | Hashing Part 1: Separate Chaining, Open Addressing, Linear Probing |
| `20260902_094834.aac` | 02/09/2569 09:48 น. | 31 นาที 43 วินาที | Hashing Part 2: Quadratic Probing, Double Hashing, Secondary Clustering |
| `20260902_104259.aac` | 02/09/2569 10:42 น. | 2 วินาที | บันทึกช่วงพักเบรกสั้น |
| `20260902_104304.aac` | 02/09/2569 10:43 น. | 23 นาที 49 วินาที | Hashing Part 3: Rehashing, Load Factor $> 70\%$, ขนาดตาราง 17 |
| `20260902_110748.aac` | 02/09/2569 11:07 น. | 7 นาที 09 วินาที | Priority Queue Part 1: นิยามคำว่าคิวและสิทธิพิเศษแซงคิว |
| `20260902_111515.aac` | 02/09/2569 11:15 น. | 6 นาที 36 วินาที | Priority Queue Part 2: ตัวอย่างจริง, ความหมายของ Heap กองดินกองทราย |
| `20260902_112213.aac` | 02/09/2569 11:22 น. | 4 นาที 01 วินาที | Binary Heap: Complete Binary Tree, กฎแทรกซ้าย-ขวา, ลบขวา-ซ้าย |
| `20260902_112628.aac` | 02/09/2569 11:26 น. | 10 นาที 42 วินาที | **ข้อสอบข้อ 2!** คำนวณโหนดที่ความสูง $H=10$ ตอบ 1024 และ 2047 |
| `20260902_113741.aac` | 02/09/2569 11:37 น. | 7 นาที 02 วินาที | Array Representation: Root=1, Left=$2i$, Right=$2i+1$, Parent=$\lfloor i/2 \rfloor$ |
| `dsa20260909_092220.aac`| 09/09/2569 09:22 น. | 36 วินาที | สรุปทบทวน Array Representation ก่อนเริ่มไล่โค้ด |
| `dsa20260909_092303.aac`| 09/09/2569 09:23 น. | 50 นาที 01 วินาที | **ข้อสอบปลายภาค!** ไล่โค้ด Python `BinaryHeap.insert(14)` และลูป Percolate Up |
| `20260909_103704.aac` | 09/09/2569 10:37 น. | 81 นาที 39 วินาที | **ข้อสอบปลายภาค!** ไล่โค้ด `deleteMin`, Percolate Down, การบ้าน และเผยสอบ DeleteMin 3 ครั้ง |
| `20260916_092007.aac` | 16/09/2569 09:20 น. | 44 นาที 43 วินาที | **Sorting Part 1:** สัญนิยมการเรียง, เจาะลึก Insertion Sort และตาราง Position Move, 3 Cases |
| `20260916_102037.aac` | 16/09/2569 10:20 น. | 68 นาที 45 วินาที | **Sorting Part 2:** Selection Sort, range(0) ใน Python, Bubble Sort, สูตรลัด Inversion, ใบงานแบบฝึกหัดท้ายคาบ |
| `20260923_091645.aac` | 23/09/2569 09:16 น. | 147 นาที 52 วินาที| **🔥 บทที่ 10 Graph Theory:** 14 ภาพกระดาน, ข้อสอบรั่ว Complete Graph 45 เส้น, Adjacency Matrix สิ้นเปลือง 75.51% vs List 19 ช่อง, จุดลวง Path ห้ามใส่ลูกศร (0 คะแนน), โจทย์ลวง Null Graph |

---

## 🖼️ คลังภาพและสารบัญรูปภาพบรรยาย (`DSA-pic/` Visual Catalog)

โฟลเดอร์ [DSA-pic/](file:///C:/Project/Voice/DSA-pic/) รวบรวมภาพถ่ายหน้าจอโปรเจกเตอร์ สไลด์บรรยาย และกระดานดำรวม 106 ภาพ เชื่อมโยงกับเนื้อหาการเรียนดังนี้:

### กลุ่มที่ 1: คาบเรียนวันที่ 26 สิงหาคม 2569 (26 ภาพ)
- **LinkedList Implementation & Memory Layout (09:17 - 10:25 น.):**
  - [IMG_20260826_091737_550](file:///C:/Project/Voice/DSA-pic/IMG_20260826_091737_550@2133355796.jpg) ถึง [IMG_20260826_102512_637](file:///C:/Project/Voice/DSA-pic/IMG_20260826_102512_637@1078549838.jpg): ตัวอย่างคลาสโหนด, `listA.insert()`, การวาดพอยน์เตอร์บนกระดาน
- **บทนำ Hashing & Separate Chaining (10:54 - 11:09 น.):**
  - [IMG_20260826_105404_780](file:///C:/Project/Voice/DSA-pic/IMG_20260826_105404_780@868538722.jpg): สไลด์แนะนำ Chapter 7 Hashing
  - [IMG_20260826_110850_112](file:///C:/Project/Voice/DSA-pic/IMG_20260826_110850_112@2055522502.jpg), [IMG_20260826_110853_418](file:///C:/Project/Voice/DSA-pic/IMG_20260826_110853_418@-698788718.jpg), [IMG_20260826_110910_371](file:///C:/Project/Voice/DSA-pic/IMG_20260826_110910_371@-1304483386.jpg): แผนภาพ Separate Chaining
- **Open Addressing & Linear Probing (11:27 - 12:01 น.):**
  - [IMG_20260826_112751_651](file:///C:/Project/Voice/DSA-pic/IMG_20260826_112751_651@-1735638268.jpg): นิยาม Open Addressing
  - [IMG_20260826_113233_236](file:///C:/Project/Voice/DSA-pic/IMG_20260826_113233_236@553663909.jpg): สูตรหลัก $h_i(x) = (\text{hash}(x) + F(i)) \pmod{\text{Table\_Size}}$
  - [IMG_20260826_113527_438](file:///C:/Project/Voice/DSA-pic/IMG_20260826_113527_438@-1503705519.jpg): นิยาม Linear Probing $F(i) = i$
  - [IMG_20260826_114905_347](file:///C:/Project/Voice/DSA-pic/IMG_20260826_114905_347@-1119323055.jpg) ถึง [IMG_20260826_115844_081](file:///C:/Project/Voice/DSA-pic/IMG_20260826_115844_081@-725424099.jpg): ตารางใส่ข้อมูล 89, 18, 49, 58 พร้อม Wrap Around
  - [IMG_20260826_120134_783](file:///C:/Project/Voice/DSA-pic/IMG_20260826_120134_783@145435942.jpg): สไลด์สรุปการใส่ 58 และคำเตือนห้ามตอบ 6

---

### กลุ่มที่ 2: คาบเรียนวันที่ 2 กันยายน 2569 (33 ภาพ)
- **สรุปผลการชน Linear Probing & ปัญหา Primary Clustering (09:26 - 09:31 น.):**
  - [IMG_20260902_092629_264](file:///C:/Project/Voice/DSA-pic/IMG_20260902_092629_264@644218902.jpg): สไลด์สรุปใส่ครบ 5 ตัว เกิดการชน 7 ครั้ง (69: 3 ครั้ง, 58: 3 ครั้ง, 49: 1 ครั้ง)
  - [IMG_20260902_092757_185](file:///C:/Project/Voice/DSA-pic/IMG_20260902_092757_185@1043314096.jpg), [IMG_20260902_093139_293](file:///C:/Project/Voice/DSA-pic/IMG_20260902_093139_293@1056574251.jpg): แผนภาพแสดงกลุ่มก้อน Primary Clustering
- **Quadratic Probing & Secondary Clustering (09:37 - 09:49 น.):**
  - [IMG_20260902_093717_092](file:///C:/Project/Voice/DSA-pic/IMG_20260902_093717_092@1096805742.jpg) ถึง [IMG_20260902_094605_421](file:///C:/Project/Voice/DSA-pic/IMG_20260902_094605_421@1593014805.jpg): สูตร $F(i) = i^2$ และการไล่คำนวณใส่ 89, 18, 49, 58, 69
  - [IMG_20260902_094852_732](file:///C:/Project/Voice/DSA-pic/IMG_20260902_094852_732@836004370.jpg), [IMG_20260902_094919_250](file:///C:/Project/Voice/DSA-pic/IMG_20260902_094919_250@-29312171.jpg): แผนผังวงแหวนคลื่นกระเพื่อม Secondary Clustering
- **Double Hashing (09:54 - 10:20 น.):**
  - [IMG_20260902_095414_770](file:///C:/Project/Voice/DSA-pic/IMG_20260902_095414_770@1141739885.jpg) ถึง [IMG_20260902_101006_187](file:///C:/Project/Voice/DSA-pic/IMG_20260902_101006_187@1239959174.jpg): สูตร $\text{hash}_2(x) = R - (x \bmod R)$, วิธีหา $R=7$
  - [IMG_20260902_101723_409](file:///C:/Project/Voice/DSA-pic/IMG_20260902_101723_409@420928213.jpg), [IMG_20260902_102011_819](file:///C:/Project/Voice/DSA-pic/IMG_20260902_102011_819@-956099729.jpg): การคำนวณ $F(1)$ ของ 49 ได้ 7, 58 ได้ 5, 69 ได้ 1
- **Rehashing & ขยายตาราง (10:50 - 11:04 น.):**
  - [IMG_20260902_105026_745](file:///C:/Project/Voice/DSA-pic/IMG_20260902_105026_745@-2018013112.jpg) ถึง [IMG_20260902_110434_333](file:///C:/Project/Voice/DSA-pic/IMG_20260902_110434_333@-1716796054.jpg): สไลด์คำนวณเปอร์เซ็นต์ตาราง 7 ช่องใส่ 4 ตัว (57.14%) ใส่เพิ่มตัวที่ 5 เป็น 71.42% ขยายเป็นขนาด 17 และลำดับการอ่านจากบนลงล่าง (6, 15, 24, 13)
- **Priority Queue, Heap & Node Calculation (11:22 - 11:37 น.):**
  - [IMG_20260902_112203_525](file:///C:/Project/Voice/DSA-pic/IMG_20260902_112203_525@1985525037.jpg): สไลด์เปิดบทที่ 8
  - [IMG_20260902_112442_392](file:///C:/Project/Voice/DSA-pic/IMG_20260902_112442_392@2130616190.jpg), [IMG_20260902_112525_396](file:///C:/Project/Voice/DSA-pic/IMG_20260902_112525_396@-397010168.jpg): **ข้อสอบความสูง $H=10$ ตอบ 1024 และ 2047**
  - [IMG_20260902_113121_541](file:///C:/Project/Voice/DSA-pic/IMG_20260902_113121_541@-1402929343.jpg), [IMG_20260902_113308_947](file:///C:/Project/Voice/DSA-pic/IMG_20260902_113308_947@-815528554.jpg): Min-Heap และ Complete Binary Tree
  - [IMG_20260902_113705_690](file:///C:/Project/Voice/DSA-pic/IMG_20260902_113705_690@-811833240.jpg): สูตรการแปลง Tree เป็น Array (Root=1, Left=$2i$, Right=$2i+1$, Parent=$\lfloor i/2 \rfloor$)

---

### กลุ่มที่ 3: คาบเรียนวันที่ 7 กันยายน 2569 (1 ภาพ)
- [IMG_20260907_153633_628](file:///C:/Project/Voice/DSA-pic/IMG_20260907_153633_628.jpg): ภาพกระดานดำสรุปสูตรดัชนี Array และเงื่อนไขการตัดเศษทิ้ง

---

### กลุ่มที่ 4: คาบเรียนวันที่ 9 กันยายน 2569 (26 ภาพ)
- **การทบทวนและไล่โค้ด `BinaryHeap.insert(14)` (09:22 - 10:04 น.):**
  - [IMG_20260909_092253_743](file:///C:/Project/Voice/DSA-pic/IMG_20260909_092253_743.jpg) ถึง [IMG_20260909_093653_400](file:///C:/Project/Voice/DSA-pic/IMG_20260909_093653_400.jpg): โครงสร้างคลาส `BinaryHeap`, Constructor `__init__`, `[None] * (capacity + 1)`
  - [IMG_20260909_094140_669](file:///C:/Project/Voice/DSA-pic/IMG_20260909_094140_669.jpg), [IMG_20260909_094609_602](file:///C:/Project/Voice/DSA-pic/IMG_20260909_094609_602.jpg): **สไลด์โจทย์ข้อสอบ:** แทรก 14 ลงใน Heap 10 สมาชิก
  - [IMG_20260909_094650_241](file:///C:/Project/Voice/DSA-pic/IMG_20260909_094650_241.jpg) ถึง [IMG_20260909_100405_540](file:///C:/Project/Voice/DSA-pic/IMG_20260909_100405_540.jpg): ตาราง Trace `hole` แต่ละรอบ (11 $\rightarrow$ 5 $\rightarrow$ 2) และเงื่อนไข While loop
- **การไล่โค้ด `deleteMin()` และ Percolate Down (10:39 - 11:34 น.):**
  - [IMG_20260909_103928_646](file:///C:/Project/Voice/DSA-pic/IMG_20260909_103928_646.jpg) ถึง [IMG_20260909_110520_920](file:///C:/Project/Voice/DSA-pic/IMG_20260909_110520_920.jpg): นิยามการลบ Root และการลอยตัวลง
  - [IMG_20260909_110606_048](file:///C:/Project/Voice/DSA-pic/IMG_20260909_110606_048.jpg) ถึง [IMG_20260909_113431_184](file:///C:/Project/Voice/DSA-pic/IMG_20260909_113431_184.jpg): สไลด์ขั้นตอน `deleteMin` อย่างละเอียด: ดึง 13 ออก, ตัวท้ายสุด 31 ลอยมา, เลือกลูกตัวน้อยกว่าสลับที่จนได้ตำแหน่งหลุมที่ 5
- **การสั่งการบ้านและการเฉลยแนวข้อสอบปลายภาค (11:56 - 11:57 น.):**
  - [IMG_20260909_115634_445](file:///C:/Project/Voice/DSA-pic/IMG_20260909_115634_445.jpg), [IMG_20260909_115719_307](file:///C:/Project/Voice/DSA-pic/IMG_20260909_115719_307.jpg): **แบบฟอร์มการบ้านส่งก่อน 12:00 น. และเผยข้อสอบปลายภาค DeleteMin 3 ครั้งติดต่อกัน!**

---

### กลุ่มที่ 5: คาบเรียนวันที่ 16 กันยายน 2569 (5 ภาพ)
- **สัญนิยมการเรียงลำดับ & การวิเคราะห์ Insertion Sort (09:21 - 09:58 น.):**
  - [IMG_20260916_092114_638@166919381.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260916_092114_638@166919381.jpg): สไลด์เปิดบทที่ 9 Comparison-based sorting สัญนิยมเรียงจากน้อยไปหามาก
  - [IMG_20260916_094820_819@893369530.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260916_094820_819@893369530.jpg): สไลด์ตารางการทำงาน Insertion Sort Trace ข้อมูล 34, 8, 64, 51, 32, 21 รอบ p=1 ถึง 5 และ Position Move
  - [IMG_20260916_095318_496@1010269358.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260916_095318_496@1010269358.jpg): บันทึกกระดาน Best Case 8, 21, 32, 34, 51, 64 (0 moves), Worst Case, Average Case
  - [IMG_20260916_095816_275@-1897800400.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260916_095816_275@-1897800400.jpg): บันทึกกระดานโจทย์ Worst Case 64, 51, 34, 32, 21, 8 คำนวณ Position Move รวม 15 ครั้ง
- **ใบงานแบบฝึกหัดในห้องเรียน (In-Class Assignment / Quiz) (11:27 น.):**
  - [IMG_20260916_112712_580@-1614993214.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260916_112712_580@-1614993214.jpg): ใบงานจริงวิชา DSA เรื่องการไล่ Bubble Sort บนอาร์เรย์ `[64, 34, 25, 12, 22, 11, 90]` (Passes=6, Total Swaps=14, Step 4 trace, Pass 1 result, Swaps after pass 1 = 5) ส่งก่อนเที่ยงตรง

---

### กลุ่มที่ 6: คาบเรียนวันที่ 23 กันยายน 2569 (14 ภาพ)
- **ทฤษฎีกราฟ, นิยาม Path, และจุดลวงข้อสอบ 0 คะแนน (10:11 - 10:39 น.):**
  - [IMG_20260923_101115_542@-1909020087.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_101115_542@-1909020087.jpg): กราฟ 4 จุดยอด $A,B,C,D$ ตัวอย่าง Path Cycle $A,B,C,D,A$ พร้อมกฎเหล็กห้ามใส่ลูกศรเด็ดขาด (ได้ 0 ทันที)
  - [IMG_20260923_102340_253@440933343.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_102340_253@440933343.jpg): บันทึกกระดาน Disconnected Graph ที่มีโหนดไม่มี Path เชื่อมต่อ
  - [IMG_20260923_103027_887@-883680469.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103027_887@-883680469.jpg): การเดินเชื่อมต่อทางอ้อมผ่านโหนดตัวกลาง
  - [IMG_20260923_103124_138@681950856.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103124_138@681950856.jpg): กราฟ $V=\{A,B,C,D\}, E=\{(A,B),(B,C)\}$ ไม่มีเส้นตรง $A-C$ แต่มี Path $A, B, C$
  - [IMG_20260923_103349_551@-151508216.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103349_551@-151508216.jpg): กราฟย่อยที่มี Isolated Vertices
  - [IMG_20260923_103455_240@-1902186239.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103455_240@-1902186239.jpg): กราฟโหนดเดี่ยว $V=\{D\}, E=\{\}$ พิสูจน์ว่าเป็นกราฟตามนิยาม
  - [IMG_20260923_103736_910@1714137841.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103736_910@1714137841.jpg): กราฟว่าง $V=\{\}, E=\{\}$ (Null Graph) จุดลวงยอดฮิตในข้อสอบ
  - [IMG_20260923_103822_425@-1355721106.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103822_425@-1355721106.jpg): บันทึกกระดานเฉลยข้อสอบ Null Graph ถาม Path $A$ ไป $C$ ให้ตอบว่า "ไม่มี Path เพราะไม่มีโหนด $A$ และ $C$"
  - [IMG_20260923_103945_248@-2093106769.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_103945_248@-2093106769.jpg): สรุปนิยามและข้อควรระวังเรื่อง Null Graph
- **ข้อสอบ Complete Graph 45 เส้น และการคำนวณ Memory Waste (10:48 - 11:38 น.):**
  - [IMG_20260923_104814_788@-1807977296.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_104814_788@-1807977296.jpg): **ข้อสอบปลายภาค!** คำนวณเส้น Complete Graph $V=10 \implies E = \frac{10 \times 9}{2} = 45$ เส้น (ต้องตอบเลขจำนวนเต็ม 45 เท่านั้น)
  - [IMG_20260923_110059_773@1901326602.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_110059_773@1901326602.jpg): ตาราง Adjacency Matrix ขนาด $7 \times 7 = 49$ ช่อง พร้อมข้อความชี้จุดสูญเปล่าหน่วยความจำ
  - [IMG_20260923_110522_696@1035849451.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_110522_696@1035849451.jpg): **ข้อสอบภาษาอังกฤษ!** คำนวณ % Memory Waste: ช่องเลข 1 คิดเป็น 24.48%, ช่องเลข 0 สูญเปล่า 75.51%
  - [IMG_20260923_113450_494@173595678.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_113450_494@173595678.jpg): **ข้อสอบปลายภาค!** สไลด์เปรียบเทียบขนาด Adjacency List สำหรับกราฟ 10 Vertices 20 Edges ใช้ $10 + 20 = 30$ ช่อง
  - [IMG_20260923_113807_477@-1558442029.jpg](file:///C:/Project/Voice/DSA-pic/IMG_20260923_113807_477@-1558442029.jpg): **ข้อสอบปลายภาค!** Adjacency Matrix สำหรับกราฟ 10 Vertices ใช้ $10^2 = 100$ ช่อง สรุปว่า List ประหยัดหน่วยความจำกว่าถึง 70%
