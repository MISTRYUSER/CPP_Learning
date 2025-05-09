 *记录时间：2025年3月22日*

---

### 关于编程笔记的总结（2025年3月20日-22日）

你的笔记涵盖了C语言指针高级用法和数据结构的基础知识，包括`realloc`、头文件、动态数组（Vector）、二级指针、函数指针、`qsort`，以及链表、栈、队列和哈希表。以下是三天内容的精简总结和关键要点：

#### 3月20日：指针高级

1. **`realloc`**
    
    - 用于动态调整内存大小，可能原地扩容或重新分配。
        
    - 注意：返回`NULL`时原内存不释放，需检查返回值避免泄漏。
        
    - 示例：从40字节扩展到100字节。
        
2. **头文件**
    
    - 作用：声明函数、结构体、宏等，实现代码隔离。
        
    - 保护语法：`#ifndef`防止重复包含。
        
3. **Vector（动态数组）**
    
    - 结构：`data`（存储数据）、`length`（当前元素数）、`capacity`（容量）。
        
    - 操作：创建、销毁、尾插、扩容（翻倍策略）、删除、查找。
        
    - 示例：`realloc`实现动态扩容。
        
4. **二级指针**
    
    - 指向指针的指针，用于修改指针本身。
        
    - 示例：`int **p`改变`p`的指向。
        
5. **函数指针**
    
    - 指向函数入口地址，格式：`返回类型 (*指针名)(参数列表)`。
        
    - 示例：调用`test1`或传递`add`函数。
        
6. **`qsort`**
    
    - 标准库快速排序，需自定义比较函数。
        
    - 示例：升序排序整数数组。
        

---

#### 3月21日：数据结构（链表）

1. **单链表**
    
    - 结构：节点（数据域+指针域）、链表（头指针、尾指针、大小）。
        
    - 操作：创建、销毁、头插、尾插、按索引插入、按数据删除。
        
    - 注意：释放内存时保存下一节点地址。
        
2. **双向链表**
    
    - 节点新增`prev`指针，支持双向遍历。
        
    - 操作：创建、销毁、头插、尾插、删除。
        
    - 注意：删除时调整前后指针。
        
3. **二级指针应用**
    
    - 示例：通过`Node **head`在函数中修改链表头指针。
        
4. **判断链表是否有环**
    
    - 方法：快慢指针（慢走1步，快走2步），相遇则有环。
        
5. **反转链表**
    
    - **循环法**：用`prev`、`current`、`next`逐个反转指针。
        
    - **递归法**：递归到尾部后逐层调整指针。
        

---

#### 3月22日：数据结构（栈、队列、哈希表）

1. **栈（Stack）**
    
    - 原则：后进先出（LIFO）。
        
    - 操作：`push`、`pop`、`peek`、`isEmpty`。
        
    - 实现：数组（固定大小）或链表。
        
    - 应用：函数调用、撤销机制。
        
2. **队列（Queue）**
    
    - 原则：先进先出（FIFO）。
        
    - 操作：`enqueue`、`dequeue`、`front`、`isEmpty`。
        
    - 实现：循环队列（数组高效利用空间）。
        
    - 应用：任务调度、BFS。
        
3. **哈希表（Hash Map）**
    
    - 原则：键值映射。
        
    - 操作：`put`、`get`、`delete`。
        
    - 实现：链地址法解决冲突，自定义哈希函数。
        
    - 应用：快速查找、缓存。
        

---

### 三天笔记比较总结

|主题|3月20日（指针高级）|3月21日（链表）|3月22日（栈、队列、哈希表）|
|---|---|---|---|
|**核心内容**|内存管理、指针操作|链表基础及高级操作|线性与关联数据结构|
|**关键技术**|`realloc`、二级指针、函数指针|快慢指针、递归反转|循环队列、链地址哈希|
|**复杂度**|O(1) 操作为主|O(n) 遍历与操作|栈/队列 O(1)，哈希 O(1)平均|
|**应用场景**|动态内存、函数调用|数据连接、链表算法|顺序处理、快速查找|

#### 精简总结

- **20日**：聚焦C语言内存与指针高级用法，奠定动态数据结构基础。
    
- **21日**：深入链表操作与算法，强调指针灵活性。
    
- **22日**：扩展到栈（LIFO）、队列（FIFO）和哈希表（键值查找），覆盖线性与关联结构。
    