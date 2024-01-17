---
layout: post
title:  "Share To Learn Draft"
author: "Fuku"
tags: Random
---

Some Share To Learn Idea but just draft & brief content

# Mechanical Sympathy

ref:

[Tìm hiểu về khái niệm Mechanical Sympathy trong phần mềm.](https://batnamv.medium.com/t%C3%ACm-hi%E1%BB%83u-v%E1%BB%81-kh%C3%A1i-ni%E1%BB%87m-mechanical-sympathy-v%C3%A0-b%E1%BB%99-th%C6%B0-vi%E1%BB%87n-lmax-disruptor-4d553dc7fa55)

[Concurrency is hard](https://mkralka.github.io/blog/concurrency-is-hard)

## the idea/definition
Man and machine working togenther in harmony
Sorfware and hardware working together in harmony
Ki Ken Tai Ichi harmonize the internal energy (ki), the sword (ken) and the body (tai) to maximize the power of your strike

Apply a Scentific Mindset:
- Draw on Experience
- Do your Reasearch
- Learn by Experimenting

Understanding the safety features will greatly improve your understanding of the model:
- **Bounds checking** is any method of detecting whether a variable is within some bounds before it is used.
- **forward error correction** is a method of obtaining error control in data transmission in which the source (transmitter) sends redundant data and the destination (receiver) recognizes only the portion of the data that contains no apparent errors
- **RAID (redundant array of independent disks)** is a data storage virtualization technology that combines multiple physical disk drive components into one or more logical units for the purposes of data redundancy, performance improvement, or both.
- Circuit Breaker (pattern)
- replication
- congestion control
- error/exception handling
- automatic memory management

Apply telemetry and perform real-time monitoring on the data
Requires efficient collection, centralised aggregation, analysis, and alerting

## Mechanical Sympathy in Action:

- It is all about experience and understanding executed with finesse
- Know where the limits are and plan to stay inside them
- React appropriately to spikes in load...
- ...apply batching to amortise costs and back-off strategiesto prevent failure
- Do you know the fundamentals of how your platform works?
- Networks are faster than Storage
- Memory Access Patterns Matter

## Why

- Chia sẻ bộ nhớ (share memory) giữa các thread rất dễ gặp lỗi, chúng ta phải rất cẩn thận khi sử dụng.
- Sử dụng bộ nhớ của CPU (CPU cache) nhanh hơn sử dụng bộ nhớ đệm chính (DRAM), nhưng nếu sử dụng mà không hiểu rõ cách hoạt động (ví dụ như khái niệm cache lines v.V...) sẽ làm mọi thứ trở nên tồi tệ hơn.

## Shared memory

Các process/thread của CPU sẽ sử dụng chung một vùng không gian nhớ chung (share memory). Việc tương tác giữa hai process sẽ hoàn toàn do việc đọc/ghi trên vùng nhớ chung này. OS không hề can thiệp vào quá trình này, thế nên shared memory là phương pháp nhanh nhất (nhanh về mặt tốc độ) để các process nói chuyện với nhau. Tuy nhiên, nhược điểm của phương pháp này là các process phải tự quản lý việc đọc ghi dữ liệu, và quản lý việc tranh chấp tài nguyên (race condition).

**Race condition**

**CPU caches**
L1, L2, L3, Main memory (DRAM)

**cache lines**

## Concurrent programming

### Tương tranh - Mutual Exclusion (cơ chế loại trừ lẫn nhau)

Trong ngành khoa học máy tính, tương tranh là một tính chất của các hệ thống bao gồm các tính toán được thực thi trùng nhau về mặt thời gian, trong đó các tính toán chạy đồng thời có thể chia sẻ các tài nguyên dùng chung. Hoặc theo lời của Edsger Dijkstra: “Tương tranh xảy ra khi nhiều hơn một luồng thực thi có thể chạy đồng thời.” Việc cùng sử dụng các tài nguyên dùng chung, chẳng hạn bộ nhớ hay file dữ liệu trên đĩa cứng, là nguồn gốc của nhiều khó khăn. Các tranh đoạt điều khiển (race condition) liên quan đến các tài nguyên dùng chung có thể dẫn đến ứng xử không đoán trước được của hệ thống. Việc sử dụng cơ chế loại trừ lẫn nhau(mutual exclusion) có thể ngăn chặn các tình huống chạy đua, nhưng có thể dẫn đến các vấn đề như tình trạng bế tắc (deadlock) và đói tài nguyên (resource starvation).

Tóm lại Mutual Exclusion là ta phải đảm bảo trong một thời điểm chỉ duy nhất 1 thread được thực thi vào share memeory. -> locking/CAS(compare and swap)

### Visibility of Change

"Những thay đổi được thực hiện bởi một luồng (thread) với dữ liệu chia sẻ (share data), sẽ được thông báo và hiển thị (visible) ngay lập tức với các thread khác để duy trì tính nhất quán của dữ liệu (data consistency)"

**sharing memory by communicating**

## LMAX Disruptor

### Ring Buffer


[Arcturus — Inventory Processing System](https://engineering.tiki.vn/arcturus-inventory-processing-system/) an application of LMAX Disruptor

# The silent majority

# Tăng tốc data base

## Index

Mục lục của cuốn sách cố định sau khi in xong, nó không bao giờ lớn hơn kích thước nội dung , còn index thì có thể theo nhiều trường dữ liệu khác nhau, nó tốn dung lượng lưu trữ trong ổ cứng, làm phình to database (tốn tài nguyên ở đây chứ đâu). Mỗi khi dữ liệu thay đổi nó lại phải cập nhật lại, chèn thêm bớt index sau khi thêm sửa xóa. Vấn đề làm sao để khi bạn thay đổi dữ liệu database chạy vẫn nhanh, nó không cần đợi quá lâu để đợi cập nhật index, vậy làm thế nào mà index lại được cập nhanh như thế sau mỗi lệnh insert, delete,update? Dữ đúng thứ tự của index mà không cần thay đổi một đống data của index.

Điều này được giải quyết bằng cách kết hợp hai cấu trúc dữ liệu "doubly linked list" và một "cây tìm kiếm"

## Leaf node

**Doubly linked list**

Mỗi một node trong danh sách liên kết này có thể chứa một hoặc nhiều cục index, mỗi node được gọi là **index leaf nodes**. Bởi vì đơn vị lưu trữ nhỏ nhất của một database là page hoặc block, dung lượng của nó thường to hơn dung lượng của một index (thường cố định tầm vài kilobyte), database dùng các khoảng trống còn lại trong các block này để chèn thêm vài cục index vào cho khỏi lãng phí.

## B-Tree (balance search tree)

khoảng cách từ root node tới leaf node luôn luôn bằng nhau với tất cả các node.

Sau khi index được tạo, mỗi khi insert, delete, update dữ liệu database đều cập nhật lại index vài giữ cho cây luôn cân bằng, điều này gây ra vấn đề hiệu năng (Index chậm)

độ sâu của cây tăng theo mức logarit với dữ liệu. Các index trong thực tế với hàng triệu bản ghi thường chỉ có độ sâu là 4 hoặc 5, cây với độ sâu là 6 rất hiếm gặp.

yếu tố chính ảnh hưởng tới độ sâu là số cục trên một node, số cục càng lớn, cây càng nông hơn, duyệt càng nhanh hơn. Database cố gắng nhét càng nhiều cục càng tốt vào một node, tới hàng trăm vì vậy với dữ liệu lớn gấp hàng trăm lần thì số level mới tăng lên 1

## Index chậm

truy vấn dữ liệu theo index gồm 3 bước:
- Duyệt cây
- Duyệt theo các leaf node
- Lấy dữ liệu trong bảng

Index chậm do hai nguyên nhân:
- Bước duyệt theo leaf node chậm: để chắc chắn lấy hết các bản ghi hợp lý database phải duyệt sang leaf node tiếp theo, trong thực tế có rất nhiều bản ghi thỏa mãn điều kiện như vậy, nên database phải duyệt qua nhiều leaf node. Mỗi leaf node này nằm trên các block khác nhau, không kề nhau
- Bước lấy dữ liệu trong bảng chậm: Trong trường hợp một leaf node có thể chứa nhiều cục index (thường là hàng trăm) nhưng khi lấy dữ liệu từ bảng thì mỗi cục dữ liệu trong bảng có thể nằm trên nhiều block khác nhau

Oracle giải thích về các kiểu duyệt cơ bản khi tìm kiếm theo index như sau:
- INDEX UNIQUE SCAN: Kiểu này là chỉ có duyệt cây thôi, kiểu này được dùng khi tìm kiếm trong một trường có ràng buộc unique đảm bảo rằng có duy nhất một bản ghi thỏa mãn. 
- INDEX RANGE SCAN: Kiểu này sẽ là vừa duyệt cây vừa duyệt theo leaf node để tìm tất cả bản ghi thỏa mãn, chạy khi có khả năng có nhiều bản ghi thỏa mãn kết quả tìm kiếm.
- TABLE ACCESS BY INDEX ROWID: Kiểu này để lấy các dòng dữ liệu trong table , thao tác này thường được thực hiện với các bản ghi phù hợp từ các thao tác trước đó

## Where trên khóa chính

```sql
SELECT first_name, last_name
  FROM employees
 WHERE employee_id = 123
```

_The PostgreSQL operation Index Scan combines the INDEX [UNIQUE/RANGE] SCAN and TABLE ACCES BY INDEX ROWID operations from the Oracle Database. It is not visible from the execution plan if the index access might potentially return more than one row._

Một lệnh truy vấn chậm thường có nguyên nhân đầu tiên là một lệnh WHERE viết cùi

dù dữ liệu to nhỏ mặc lòng khi cần tìm kiếm theo Primary Key thì cứ vô tư đi, không thể nào chậm được.

## Index kết hợp (Concatenated Indexes / Multi-column Indexes)

```sql
SELECT first_name, last_name
  FROM employees
 WHERE employee_id   = 123
   AND subsidiary_id = 30
```

index không hỗ trợ tìm kiếm theo trường thứ hai, giống như việc tìm danh bạ theo HỌ vậy (cái này mình nói quyển danh bạ ngày xưa chứ giờ tra IPhone thì cái gì nó chả ra, hoặc ví dụ khác là các bạn tìm kiếm từ điển bằng chữ cái thứ hai vậy)

Một bảng càng ít index các thao tác Insert, Delete, Update chạy càng nhanh

The Query Optimizer, hay query planner là một thành phần của database chuyển các câu lệnh SQL thành execution plan quá trình này gọi là compiling hoặc parsing. Có hai loại trình tối ưu như sau:

Cost-based optimizers (CBO) tạo ra rất nhiều execution plan khác nhau và tính toán chi phí cho mỗi plan, nó được ước tính dựa vào số thao tác cần xử lý và số lượng bản ghi. Chi phí (cost) này được dùng để chọn execution plan tốt nhất.

Rule-based optimizers (RBO) tạo ra execution plan dựa vào một tập hợp rule cố định,Rule based optimizers kém linh hoạt hơn và hiện tại ít được sử dụng.

statistics: Một trình tối ưu theo kiểu cost-base sử dụng các số liệu thống kê về bảng, cột và index. Hầu hết các statistics được thu thập ở cấp độ cột, số lượng các giá trị không trùng lặp, giá trị nhỏ nhất và lớn nhất (data range), số lượng giá trị NULL, và sự phân phối của dữ liệu. Giá trị thống kê quan trọng nhất cho một bảng là kích cỡ của bảng ( được tính bằng số dòng hoặc số block)

Giá trị thống kê quan trọng nhất cho một index là độ sâu của tree, số lượng leaf node, số lượng các distinct key và clustering (Phần này mình sẽ viết sau) Trình tối ưu sẽ dùng các giá trị này để ước lượng selectivity trong predicates của mệnh đề WHERE

Selectivity là gì: Nó được tính bằng công thức Selectivity = cardinality/(tổng số bản ghi) * 100% . cardinality là số lượng bản ghi có giá trị khác nhau (distinct values). Ví dụ nếu một trường giới tính có hai giá trị Nam/Nữ thì cardinality 2. Trong ví dụ của chúng ta có hai công ty sáp nhập thì SUBSIDIARY_ID có hai giá trị công ty mới và công ty cũ nên cardinality cũng bằng 2.

**Nếu có một statistics đúng, trình tối ưu sẽ hoạt động tốt hơn.**

## Index trên hàm

Các index được định nghĩa trên hàm hoặc biểu thức được gọi là **function-based index(FBI)**

Thỉnh thoảng ORM tool tự thêm UPPER và LOWER mà developer không biết khi tìm kiếm không phân biệt hoa thường (:P)

SQL Server và MySQL không hỗ trợ FBI nhưng chúng ta có thể đánh index trên computed hoặc generated column

## Query Planner Postgresql

[ref](https://use-the-index-luke.com/sql/explain-plan/postgresql/operations)

### Index and Table Access

**Seq Scan**: scans the entire relation (table) as stored on disk (like TABLE ACCESS FULL)

**Index Scan**: performs a B-tree traversal, walks through the leaf nodes to find all matching entries, and fetches the corresponding table data. It is like an INDEX RANGE SCAN followed by a TABLE ACCESS BY INDEX ROWID operation.

**Index Only Scan** (PostgreSQL9.2+): performs a B-tree traversal and walks through the leaf nodes to find all matching entries. There is no table access needed because the index has all columns to satisfy the query

 **Bitmap Index Scan / Bitmap Heap Scan / Recheck Cond**: A plain Index Scan fetches one tuple-pointer at a time from the index, and immediately visits that tuple in the table. A bitmap scan fetches all the tuple-pointers from the index in one go, sorts them using an in-memory “bitmap” data structure, and then visits the table tuples in physical tuple-location order.

 ### Join Operations

 **Nested Loop**: Joins two tables by fetching the result from one table and querying the other table for each row from the first.
 
 **Hash Join / Hash**: The hash join loads the candidate records from one side of the join into a hash table (marked with Hash in the plan) which is then probed for each record from the other side of the join.

 **Merge Join**: The (sort) merge join combines two sorted lists like a zipper. Both sides of the join must be presorted.

 ### Sorting and Grouping

  **Sort / Sort Key** Sorts the set on the columns mentioned in Sort Key. The Sort operation needs large amounts of memory to materialize the intermediate result (not pipelined).

  **GroupAggregate**: Aggregates a presorted set according to the group by clause. This operation does not buffer large amounts of data (pipelined).

  **HashAggregate**: Uses a temporary hash table to group records. The HashAggregate operation does not require a presorted data set, instead it uses large amounts of memory to materialize the intermediate result (not pipelined). The output is not ordered in any meaningful way.

  ### Top-N Query

  **Limit**: Aborts the underlying operations when the desired number of rows has been fetched.

  **WindowAgg**: PostgreSQL cannot use conditions on the result of window functions to abort top-N queries.

  - Giá trị thống kê quan trọng nhất cho một **bảng**  là kích cỡ của bảng (só dòng hoặc số block)
  - Giá trị thống kê quan trọng nhất cho một **index** là độ sâu của tree, số leaf node, distinct key và clustering
  - Selectivity = (cardinality/tổng số bản ghi)*100
  - Dưới góc nhìn của database, index đánh trên last_name và upper(last_name) là hoàn toàn khác nhau
**TODO** cơ chế update dữ liệu statistics trên các DBMS




# Communication

## Common

- menu
- step by step
- one and only one terminology to express a thing
- screenshot rather than just url (but both is better)
- environment is neccessary
- current behavior first
- clue is good, but dont mix it with other section
- if u met the problem before, say it
- for features, writing is better than talking