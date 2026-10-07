# บทวิเคราะห์และถอดความการบรรยายวิชา Data Structures & Algorithms
## บทที่ 11: การหาเส้นทางที่สั้นที่สุด (Shortest Path), เฉลย Assignment 4 และประกาศแนวข้อสอบปลายภาคฉบับทางการ (Official Final Exam Leaks: 7 ข้อ 70 คะแนน)

- **วันที่บรรยาย:** วันพุธที่ 7 ตุลาคม 2569
- **เวลา:** 09:25:25 - 11:56:43 น. (ความยาวรวม: 2 ชั่วโมง 31 นาที 18 วินาที)
- **ผู้สอน:** ดร.ประดิษฐ์ พิทักษ์เสถียรกุล (Dr. Pradit Pitaksatheinkul)
- **ไฟล์เสียงต้นฉบับ:** `20261007_092525.aac`
- **ไฟล์ Transcript ฉบับเต็ม:** [20261007_092525.txt](file:///C:/Project/voice-text/03_Data_Structures_and_Algorithms/20261007_092525.txt)
- **ภาพประกอบหลักฐานชั้นต้นจากห้องเรียน:**
  - [ภาพกระดาน/หน้าจอ Notepad แนวข้อสอบ 7 ข้อ](file:///C:/Project/python-data-structures-and-algorithms/IMG_20261007_120504_255.jpg)
  - [ภาพกระดาน/หน้าจอ Notepad คำถามย่อย Properties & Calculations](file:///C:/Project/python-data-structures-and-algorithms/IMG_20261007_120456_375.jpg)
  - [ใบงาน Assignment 4 ฉบับจริง](file:///C:/Project/python-data-structures-and-algorithms/IMG_20261007_114532_858@2103460530.jpg)
  - [ภาพถ่ายงานส่ง Assignment 4 ลายมือนักศึกษา](file:///C:/Project/python-data-structures-and-algorithms/IMG_20261007_192354_720@-1896741484.jpg)
- **โครงการปลายทาง:**
  - `C:\Project\wiki-data-structure\`
  - `C:\Project\python-data-structures-and-algorithms\`

---

## 1. ข้อมูลสำคัญและการสอบปลายภาค (Final Exam Intelligence & Official Rules)

### 1.1 เกณฑ์และกติกาห้องสอบ Final
- **คะแนนสอบปลายภาค:** 70 คะแนนดิบ $\div 2 =$ **35% ของคะแนนรวมทั้งภาคการศึกษา**
- **สัดส่วนคะแนนเก็บในห้องเรียน:** รวม 30 คะแนน
  - 4 Assignments $\times 5$ คะแนน $= 20$ คะแนน (Assignment 1 Linked List, Assignment 2 Tree, Assignment 3 Heap, Assignment 4 Shortest Path)
  - 2 Test Programs $\times 5$ คะแนน $= 10$ คะแนน (Test Program 1 Queue, Test Program 2 Sorting)
- **กติกาการสอบ (Exam Regulations):**
  - ✅ **เปิดตำราได้ (Open Book):** สามารถนำชีต สไลด์ เล่มเลกเชอร์ โน้ตย่อ เอกสาร และหนังสือเข้าห้องสอบได้
  - ✅ **ใช้เครื่องคิดเลขได้ (Calculator Allowed):** อนุญาตให้นำเครื่องคิดเลขวิทยาศาสตร์เข้าห้องสอบเพื่อคำนวณ Hash Function, เปอร์เซ็นต์ขยะ, และสูตรคณิตศาสตร์
  - ❌ **ห้ามใช้โทรศัพท์มือถือและอุปกรณ์สื่อสารทุกชนิดทุกกรณี (Strictly NO Smartphones/Tablets):** ต้องปิดเครื่องและเก็บลงกระเป๋าก่อนเริ่มสอบ

---

## 2. เจาะลึกโครงสร้างข้อสอบปลายภาค 7 ข้อใหญ่ (100% Leaked Structure & Trap Analysis)

อาจารย์ได้เปิดโปรแกรม Notepad ฉายขึ้นจอโปรเจกเตอร์เวลา 11:54 น. เพื่อระบุหัวข้อข้อสอบทั้ง 7 ข้ออย่างชัดเจน:

```text
แนวทางข้อสอบปลายภาค คะแนนในข้อสอบ 70 คะแนน หาร 2 เหลือ 35 คะแนน
เปิดตำรา ใช้เครื่องคิดเลขได้ ห้ามใช้โทรศัพท์มือถือทุกกรณี
1. Hashing
2. binary heap
3. insertion sort
4. selection sort/bubble sort
5. topological sort
6. unweighted shortest path
7. เป็นคำถามย่อยๆ หลายข้อ เช่น
properties (โครงสร้างอะไรเอ่ยที่มี 2, 3 three properties two properties)
พวกที่มีการคำนวณ ใช้สูตร เปอร์เซนต์ what percentage of เป็นต้น how many
```

### ข้อ 1: Hashing (10 คะแนน)
- **รูปแบบโจทย์:** กำหนดขนาด Table Size $M$ (มักเป็นจำนวนเฉพาะ เช่น 10, 11 หรือ 13) และ Hash Function $h(k) = k \bmod M$ พร้อมชุดข้อมูลตัวเลข
- **เนื้อหาที่ทดสอบ:**
  1. การนำคีย์เข้าตาราง (Insert Keys)
  2. การจัดการการชน (Collision Resolution):
     - **Separate Chaining:** การต่อ Linked List เมื่อเกิดการชน
     - **Linear Probing:** $h_i(k) = (h(k) + i) \bmod M$
     - **Quadratic Probing:** $h_i(k) = (h(k) + i^2) \bmod M$
     - **Double Hashing:** $h_i(k) = (h(k) + i \cdot h_2(k)) \bmod M$
  3. การคำนวณ Load Factor ($\lambda = N/M$) และการ Rehash เมื่อ $\lambda > 0.5$

### ข้อ 2: Binary Heap (10 คะแนน)
- **รูปแบบโจทย์:** กำหนดชุดตัวเลขมาให้ ให้สร้าง Binary Min-Heap (หรือ Max-Heap)
- **เนื้อหาที่ทดสอบ:**
  1. **Insert Operation:** การแทรกที่ Leaf ตำแหน่งท้ายสุดของ Complete Binary Tree แล้วทำ **Percolate Up** (ลอยขึ้น)
  2. **DeleteMin Operation:** การนำ Root ออก แล้วดึง Leaf ตัวสุดท้ายมาแทนที่ Root จากนั้นทำ **Percolate Down** (จมลง) โดยสลับกับ Child ที่มีค่าน้อยที่สุด
  3. **การแทนที่ใน Array 1 มิติ:** การคำนวณตำแหน่ง Index โดยเริ่มจากช่อง 1 (ช่อง 0 ปล่อยว่าง):
     - $\text{Left Child}(i) = 2i$
     - $\text{Right Child}(i) = 2i + 1$
     - $\text{Parent}(i) = \lfloor i/2 \rfloor$

### ข้อ 3: Insertion Sort Tracing (10 คะแนน)
- **รูปแบบโจทย์:** กำหนด Array ตัวเลข เช่น `[34, 8, 64, 51, 32, 21]`
- **เนื้อหาที่ทดสอบ:**
  1. ให้แสดงสถานะของ Array ในแต่ละ Pass $p = 1, 2, \dots, N-1$
  2. ถามคำถามเจาะจง: "After Pass $p=3$, array มีค่าเป็นอย่างไร?"
  3. การนับจำนวน Inversions, จำนวนการเปรียบเทียบ (Comparisons) และจำนวนการเลื่อนข้อมูล (Data Shifts)

### ข้อ 4: Selection Sort หรือ Bubble Sort (10 คะแนน)
- อาจารย์ระบุว่าจะ **เลือกตัวใดตัวหนึ่ง** ระหว่าง Selection Sort หรือ Bubble Sort
- ให้ Tracing ทีละรอบเหมือนใบงานและ Test Program 2 ที่ส่งไป
- **จุดสังเกต:**
  - **Bubble Sort:** ตรวจสอบ adjacent pairs $(A[j], A[j+1])$ แล้ว swap ค่ามากไปข้างหลัง
  - **Selection Sort:** หาค่าที่น้อยที่สุดในส่วนที่ยังไม่เรียง แล้ว swap กับตำแหน่งแรกของช่วงนั้น

### ข้อ 5: Topological Sort (10 คะแนน)
- **รูปแบบโจทย์:** กำหนดกราฟแบบ Directed Acyclic Graph (DAG) ที่มี Vertex $v_1$ ถึง $v_7$
- **เนื้อหาที่ทดสอบ:**
  1. สร้างตาราง Indegree ของทุก Vertex
  2. การใช้ Queue เก็บ Vertex ที่มี $\text{Indegree} = 0$
  3. การแสดงสถานะการขีดฆ่าค่า Indegree เมื่อ dequeue จุดยอดออกมา และการ enqueue จุดยอดใหม่ที่ Indegree ลดลงเป็น 0
  4. ผลลัพธ์ลำดับ Topological Ordering (เช่น $v_1, v_2, v_5, v_4, v_3, v_7, v_6$)

### ข้อ 6: Unweighted Shortest Path (10 คะแนน)
- **รูปแบบโจทย์:** เหมือน **Assignment 4** ที่ทำในห้องเรียนวันนี้!
- **เนื้อหาที่ทดสอบ:**
  1. แปลงกราฟเป็น **Adjacency List**
  2. สร้างและขีดฆ่าตารางประมวลผลที่มี 3 คอลัมน์:
     - `Known` (T/F)
     - `Dist` ($d_v$, เริ่มต้นจุดเริ่ม $= 0$, จุดอื่น $= 999$ หรือ $\infty$)
     - `Path` ($p_v$, เริ่มต้น $= 0$)
  3. การแสดงสถานะของ Queue $Q$ ในแต่ละรอบ
  4. การตอบเส้นทาง (Shortest Path) โดยการ Backtrack ย้อนกลับจากปลายทางผ่านช่อง $p_v$ และตอบความยาว (Length) ของเส้นทาง

### ข้อ 7: คำถามย่อย ทฤษฎี สูตร และการคำนวณ (Short Questions & Properties: 10 คะแนน)
คำถามสั้นๆ ข้อละ 1-3 คะแนน รวมประมาณ 10 คะแนน ซึ่งอาจารย์เน้นย้ำบนกระดาน 2 หมวด:
1. **หมวด Properties (คุณสมบัติของโครงสร้างข้อมูล):**
   - *"โครงสร้างข้อมูลอะไรเอ่ยที่มี 2 Properties?"*
     $\rightarrow$ **Binary Heap** (มี 2 Properties คือ **Structure Property** [ต้องเป็น Complete Binary Tree] และ **Heap-Order Property** [Parent $\le$ Children สำหรับ Min-Heap])
   - *"โครงสร้างข้อมูลอะไรเอ่ยที่มี 3 Properties?"*
     $\rightarrow$ **Red-Black Tree** หรือ **B-Tree** หรือ **AVL Tree** (Binary Search Tree Property + Height-Balanced Property $|\Delta h| \le 1$)
2. **หมวด Calculations & Formulas (สูตรและเปอร์เซ็นต์):**
   - **Memory Waste ใน Graph:**
     - ในกราฟเบาบาง (Sparse Graph): Adjacency Matrix เสียพื้นที่เป็น 0 (ไม่ได้ใช้งาน) สูงถึง **75.51%** ขณะที่ใช้งานจริงเพียง **24.48%** จึงควรใช้ Adjacency List
   - **จำนวนเส้นเชื่อมใน Complete Graph:**
     - Undirected: $E = \frac{V(V-1)}{2}$ (เช่น $V=10 \rightarrow E = 45$ เส้น)
     - Directed: $E = V(V-1)$ (เช่น $V=10 \rightarrow E = 90$ เส้น)
   - **จำนวนโหนดสูงสุดใน Binary Tree ความสูง $h$:**
     - $N_{\max} = 2^{h+1} - 1$ (เริ่มนับ Root สูง 0)
   - **สูตรพ่อลูกใน Array ของ Heap:**
     - Left Child $= 2i$, Right Child $= 2i+1$, Parent $= \lfloor i/2 \rfloor$

---

## 3. สรุปเนื้อหาบทเรียน: Unweighted Shortest Path Algorithm

### 3.1 ขั้นตอนวิธี (Algorithm Pseudocode)
```python
def unweighted_shortest_path(graph, start_vertex):
    # 1. กำหนดค่าเริ่มต้นตาราง
    for v in graph.vertices:
        v.dist = 999  # infinity
        v.known = False
        v.path = None
    
    start_vertex.dist = 0
    Q = Queue()
    Q.enqueue(start_vertex)
    
    # 2. ประมวลผลจนกระทั่ง Queue ว่าง
    while not Q.is_empty():
        v = Q.dequeue()
        v.known = True
        
        for w in v.adjacent_vertices:
            if w.dist == 999:  # ยังไม่เคยถูกเยี่ยมชม
                w.dist = v.dist + 1
                w.path = v
                Q.enqueue(w)
```

### 3.2 ตัวอย่างการ Trace บนสไลด์หน้า 11–14 (จุดเริ่มต้น $v_3$)
เมื่อกำหนดจุดเริ่มต้นคือ $v_3$:
- **รอบที่ 0 (Init):** $Q = [v_3]$, $d(v_3) = 0$
- **รอบที่ 1:** Dequeue $v_3 \rightarrow \text{Known}[v_3]=T$, เพื่อนบ้านของ $v_3$ คือ $v_1, v_6$
  - $d(v_1) = 0 + 1 = 1, p(v_1) = v_3, Q = [v_1, v_6]$
  - $d(v_6) = 0 + 1 = 1, p(v_6) = v_3$
- **รอบที่ 2:** Dequeue $v_1 \rightarrow \text{Known}[v_1]=T$, เพื่อนบ้านของ $v_1$ คือ $v_2, v_4$
  - $d(v_2) = 1 + 1 = 2, p(v_2) = v_1, Q = [v_6, v_2, v_4]$
  - $d(v_4) = 1 + 1 = 2, p(v_4) = v_1$
- **ตารางสรุปสุดท้าย (Slide 14):**

| Vertex | Known | Dist ($d_v$) | Path ($p_v$) |
| :---: | :---: | :---: | :---: |
| $v_1$ | **T** | **1** | $v_3$ |
| $v_2$ | **T** | **2** | $v_1$ |
| $v_3$ | **T** | **0** | $0$ |
| $v_4$ | **T** | **2** | $v_1$ |
| $v_5$ | **T** | **3** | $v_2$ |
| $v_6$ | **T** | **1** | $v_3$ |
| $v_7$ | **T** | **3** | $v_4$ |

- **การหา Shortest Path จาก $v_3$ ไปยัง $v_5$:**
  - $d(v_5) = 3$ $\rightarrow$ **Length = 3**
  - Backtrack: $v_5 \leftarrow v_2 \leftarrow v_1 \leftarrow v_3$
  - **Shortest Path:** $v_3, v_1, v_2, v_5$

---

## 4. เฉลยละเอียด Assignment 4 (Shortest Path on Directed Graph)

### 4.1 ข้อมูลโจทย์
- จุดยอด: $A, B, C, D, E, F, G$ (7 จุด)
- จุดเริ่มต้น: **Vertex A**
- เส้นเชื่อมทิศทาง (Directed Edges):
  - $A \rightarrow B, C$
  - $B \rightarrow G, E, C$
  - $C \rightarrow E, D$
  - $D \rightarrow F, A$
  - $E \rightarrow D, F$
  - $F \rightarrow \text{Ground (ไม่มีเส้นออก)}$
  - $G \rightarrow E$

### 4.2 เฉลยข้อ 1: Adjacency List
```text
A -> [ B ] -> [ C ] -||
B -> [ G ] -> [ E ] -> [ C ] -||
C -> [ E ] -> [ D ] -||
D -> [ F ] -> [ A ] -||
E -> [ D ] -> [ F ] -||
F -> -||
G -> [ E ] -||
```

### 4.3 เฉลยข้อ 2: ตารางประมวลผล Shortest Path (เริ่มต้นที่ A)
ลำดับการประมวลผล Queue $Q$:
1. $Q = [A]$
2. Dequeue $A$: $A$ Known, อัปเดต $B (d=1, p=A)$, $C (d=1, p=A) \rightarrow Q = [B, C]$
3. Dequeue $B$: $B$ Known, อัปเดต $G (d=2, p=B)$, $E (d=2, p=B)$ ($C$ มีค่า $1$ อยู่แล้ว ไม่เปลี่ยน) $\rightarrow Q = [C, G, E]$
4. Dequeue $C$: $C$ Known, อัปเดต $D (d=2, p=C)$ ($E$ มีค่า $2$ อยู่แล้ว) $\rightarrow Q = [G, E, D]$
5. Dequeue $G$: $G$ Known, เพื่อนบ้าน $E$ มี $d=2$ อยู่แล้ว ไม่เปลี่ยน $\rightarrow Q = [E, D]$
6. Dequeue $E$: $E$ Known, อัปเดต $F (d=3, p=E)$ ($D$ มี $d=2$ อยู่แล้ว) $\rightarrow Q = [D, F]$
7. Dequeue $D$: $D$ Known, เพื่อนบ้าน $F$ มี $d=3, A$ มี $d=0$ ไม่เปลี่ยน $\rightarrow Q = [F]$
8. Dequeue $F$: $F$ Known, ไม่มีเพื่อนบ้าน $\rightarrow Q = []$ จบการทำงาน

**ตารางสรุปผลลัพธ์ (Final Table):**

| Vertex | Known | Dist ($d_v$) | Path ($p_v$) | ค่าที่ถูกขีดฆ่าในกระดาษคำตอบ |
| :---: | :---: | :---: | :---: | :--- |
| **A** | **T** | **0** | **0** | $F \rightarrow T$, $999 \rightarrow 0$ |
| **B** | **T** | **1** | **A** | $F \rightarrow T$, $999 \rightarrow 1$, $0 \rightarrow A$ |
| **C** | **T** | **1** | **A** | $F \rightarrow T$, $999 \rightarrow 1$, $0 \rightarrow A$ |
| **D** | **T** | **2** | **C** | $F \rightarrow T$, $999 \rightarrow 2$, $0 \rightarrow C$ |
| **E** | **T** | **2** | **B** | $F \rightarrow T$, $999 \rightarrow 2$, $0 \rightarrow B$ |
| **F** | **T** | **3** | **E** | $F \rightarrow T$, $999 \rightarrow 3$, $0 \rightarrow E$ (หรือ $D$) |
| **G** | **T** | **2** | **B** | $F \rightarrow T$, $999 \rightarrow 2$, $0 \rightarrow B$ |

---

## 5. การดำเนินการบูรณาการระบบ (System Deployment Status)
- [x] ถอดความคำต่อคำ 100% บรรจุใน [20261007_092525.txt](file:///C:/Project/voice-text/03_Data_Structures_and_Algorithms/20261007_092525.txt)
- [x] วิเคราะห์เจาะลึก 7 ข้อสอบ Final Leaks ในไฟล์นี้
- [x] ย้ายไฟล์เสียงต้นฉบับเข้า [Success/](file:///C:/Project/voice-text/Success/)
- [x] อัปเดต Master Index และ README ของหมวด 03
- [x] ผสานข้อมูลเข้าสู่ Wiki Obsidian ใน `wiki-data-structure/`
- [x] ผสานข้อมูลเข้าสู่ Web Wiki และจัดทำ Mock Final Exam ใน `python-data-structures-and-algorithms/`
