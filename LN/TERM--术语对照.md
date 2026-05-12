# TERM--术语对照

- 术语：Terminology


## 系统结构领域

### General

| Abbr. | English                                      | 中文                      | 备注/相关术语            |
| ---   | ---                                          | ---                       | ---                      |
|       | abort                                        | 中止                      | 通常指不可恢复的同步异常 |
|       | architect                                    | 架构师                    |                          |
|       | architecture                                 | 体系结构                  | 指代简单设计时可译为`架构` |
|       | buffer                                       | 缓冲器                    |                          |
|       | chip                                         | 芯片                      |                          |
|       | chiplet                                      | 芯粒                      |                          |
|       | core                                         | 核芯                      | 简称`核`                 |
|       | cycle                                        | 周期                      |                          |
|       | cycle accurate simulator                     | 周期精确模拟器            |                          |
| CISC  | Complex Instruction Set Computer              | 复杂指令系统计算机        | RISC                    |
|       | control flow instruction                     | 控制流指令                |                          |
|       | delay                                        | 延迟                      | latency（时延）          |
|       | die                                          | 管芯                      |                          |
|       | emulation                                    | 仿真                      | simulation（模拟）       |
|       | exception                                    | 异常                      | 异常通常为同步的        |
|       | fault                                        | 故障                      | 通常指可恢复的同步异常  |
|       | fence instruction                             | 屏障指令                  |                          |
| FPU   | Floating-Point Unit                          | 浮点运算部件              |                          |
|       | instruction                                  | 指令                      |                          |
|       | instruction set                              | 指令系统                  | 描述附加或扩展设计时翻译为`指令集` |
| ISA   | Instruction Set Architecture                 | 指令系统体系结构          | 通常简略翻译为`指令系统` |
|       | interrupt                                    | 中断                      | 中断通常为异步的        |
|       | jump instruction                              | 跳转指令                  |                          |
|       | latency                                      | 时延                      | delay（延迟）            |
|       | load instruction                              | 取数指令、装入指令        | store instruction        |
|       | manycore                                     | 众核                      |                          |
|       | multicore                                    | 多核                      |                          |
| NMI   | non-maskable interrupts                       | 不可屏蔽中断              |                          |
|       | off-chip                                     | 片外                      | on-chip                  |
|       | on-chip                                      | 片上                      | off-chip                 |
|       | processor                                    | 处理器                    |                          |
|       | quantum computing                            | 量子计算                  |                          |
| RISC  | Reduced Instruction Set Computer             | 精简指令系统计算机        | CISC                    |
|       | replacement policy                           | 置换策略                   |                          |
|       | sampled                                      | 抽样                      | 不建议`采样`（抽样的含义中所抽取的样本不丧失代表性，而采样没有该含义） |
|       | simulation                                   | 模拟                      | emulation（仿真）        |
|       | store instruction                             | 存数指令、存储指令        | load instruction         |
|       | system call                                  | 系统调用                  |                          |
|       | trap                                         | 陷入                      |                          |
|       | uncore                                       | 非核芯                    |                          |
|       | wafer                                        | 晶圆                      |                          |

- buffer：在软件领域，翻译为`缓冲区`，表达抽象的、非实体的存储区域概念，而在系统结构领域，则翻译为`缓冲器`，因其包含实现部件
- branch instruction：有时泛指所有控制转移类指令，有时仅指条件分支指令或条件转移指令
- 不同的处理器设计，对于exception/interrupt的含义并不统一，需要根据具体处理器的文档来理解
- load-store architecture：《中国大百科全书》翻译为`取数-存数结构`，《术语在线》翻译为`加载-存储体系结构`

### Hardware Organization and Interface

| Abbr. | English                                       | 中文                      | 备注/相关术语          |
| ---   | ---                                           | ---                       | ---                  |
| GPIO  | General Purpose Input/Output                  |                          |                      |
| GPU   | Graphics Processing Unit                      |                          |                      |
| HDMI  | High-Definition Multimedia Interface          |                          |                      |
| JTAG  | Joint Test Action Group                       |                          |                      |
|       | keyboard                                      | 键盘                    |                      |
|       | Keyboard-Video-Mouse Switch                   | KVM 切换器               | 通常缩写为`KVM switch` |
|       | mouse                                         | 鼠标                    |                      |
| RNG   | Random Number Generator                       | 随机数发生器              |                      |
|       | touchscreen                                   | 触摸屏                   |                      |
| UART  | Universal Asynchronous Receiver-Transmitter   | 通用异步收发传输器        |                      |
| UPS   | Uninterruptible Power Supply                  | 不间断电源                |                      |
| USB   | Universal Serial Bus                          | 通用串行总线              |                      |
| CPU   | Central Processing Unit                      | 中央处理器                |                      |
| ELF   | Executable and Linkable Format               | 可执行可链接格式          | 文件格式              |
| COFF  | Common Object File Format                   | 公共对象文件格式          | 文件格式              |

### Memory Hierarchy

| Abbr. | English（术语/缩写）               | 中文/全称              | 相关领域/术语          |
| ---   | ---                               | ---                   | ---                  |
|       | access fault                      | 访问故障                |                      |
|       | address                           | 地址                    |                      |
|       | address space                     | 地址空间                |                      |
|       | addressing                        | 寻址                    |                      |
|       | addressing mode                   | 寻址模式                |                      |
|       | cache line                        | 高速缓存行              |                      |
|       | cache memory                      | 高速缓存存储器          | 简称`高速缓存`或`缓存` |
|       | coherence/cache coherence         | （高速缓存）一致性      | memory consistency    |
|       | consistency/memory consistency    | （存储）一致性          | cache coherence       |
|       | hard disk                         | 硬盘                    |                      |
|       | hit                               | 命中                    | miss                  |
|       | hit rate                          | 命中率                  | miss rate             |
|       | homonyms                          | 同名                    | synonyms（同义）      |
| ILP   | Instruction-Level Parallelism    | 指令级并行              |                      |
|       | locality principle                | 局部性原理              |                      |
|       | main memory                       | 主存                    | 俗称`内存`            |
|       | memory                            | 存储器                  |                      |
|       | memory consistency model          | 存储一致性模型          | 可缩写为`memory model` |
|       | memory disambiguation             | 存储消歧                |                      |
|       | memory hierarchy                  | 存储器层次结构、存储层次 |                      |
|       | memory wall                       | 存储器墙                |                      |
|       | miss                              | 未命中                  | hit                   |
|       | miss rate                         | 未命中率                | hit rate              |
| MMU   | Memory Management Unit            | 存储管理部件            |                      |
| NVRAM | Non-volatile Random Access Memory  | 非易失性随机访问存储器 |                      |
|       | page                              | 页、页面                | 抽象概念可用`页`，具体操作则用`页面` |
|       | page fault                        | 页面故障                | 若翻译为`缺页故障`，其表述并不全面 |
|       | page table                        | 页表                    |                      |
|       | page table entry                  | 页表项                  | PTE                   |
|       | page table walker                 | 页表步进器、页表遍历器  | PTW                   |
|       | paged/paging                      | 分页/页式               |                      |
|       | physical address                  | 物理地址                | PA                    |
|       | physical memory                   | 物理存储器              | PM                    |
| RAM   | random-access memory           | 随机访问存储器          |                      |
| ROM   | Read-Only Memory              | 只读存储器              |                      |
|       | secondary memory/storage          | 次级存储、二级存储      | 也可翻译为`存贮器`，俗称`外存` |
|       | superpage                         | 超页                    |                      |
|       | synonyms                          | 同义                    | homonyms（同名）      |
| TLB   | Translation Look-aside Buffer  | 转换旁视缓冲器          | 简称`快表`            |
|       | virtual address                   | 虚拟地址                | VA                    |
|       | virtual memory                    | 虚拟存储器              | VM                    |

- consistency解决的是访存操作以何种顺序被所有处理器观测到的问题（有序的问题），coherence解决的是一份数据的多个缓存副本是否相同的问题（没有序的问题）
- homonyms/synonyms：同名指（不同进程的）相同虚拟地址映射到不同物理地址。同义指（不同进程的）不同虚拟地址映射到同一物理地址。
- memory：存储器；狭义用法是指main memory，即主存（俗称内存，与外存对应）
- miss：Intel/AMD/ARM的中文技术手册中采用的是`未命中`；若上下文已明确讨论高速缓存或存储层级，可使用`缺失`来简化术语，如`缺失率`、`缺失惩罚`
- Page Table Walking/walker：历史原因，一直翻译为页表遍历/页表遍历器，然而实际上，walking或walk的含义应直译为 `步进` 或 `游走`

### Microarchitecture

| Abbr. | English（术语/缩写）               | 中文/全称              | 相关领域/术语          |
| ---   | ---                               | ---                   | ---                  |
| ARF   | Architectural Register File      | 架构寄存器堆            |                      |
|       | bypass                            | 旁路                    |                      |
| BTB   | Branch Target Buffer          | 分支目标缓冲器          |                      |
|       | branch misprediction              | 分支预测错误            |                      |
|       | branch prediction                 | 分支/转移预测           |                      |
| CAM   | Content-Addressable Memory  | 按内容寻址存储器         |                      |
|       | commit                            | 提交                    |                      |
|       | control dependence                | 控制相关                |                      |
|       | data dependence                   | 数据相关                |                      |
|       | decode                            | 译码                    |                      |
|       | dependence                        | 相关、依赖              | 推荐翻译为`相关`       |
|       | dispatch                          | 分发                    |                      |
|       | execution                         | 执行                    |                      |
|       | fetch                             | 取指                    |                      |
|       | flush pipeline                    | 排空流水线              |                      |
|       | forward                           | 前递                    |                      |
|       | hazard                            | 冒险                    |                      |
|       | in-flight instructions            | 处理中指令、未完成指令  |                      |
|       | in-order                          | 按序                    | out-of-order（乱序）   |
| IPC   | Instructions per Cycle     | 每周期指令数            | CPI                   |
|       | issue                             | 发射                    |                      |
|       | load-store architecture           | 装入-存储体系结构        |                      |
|       | load-store queue                  | 装入-存储队列            | LSQ                   |
|       | load-store unit                   | 装入-存储部件            | LSU                   |
|       | micro-code                        | 微码                    |                      |
|       | micro-op                          | 微操作                  | UOP                   |
|       | microarchitecture                 | 微体系结构              | 描述某一具体的微体系结构实现版本，译为`微架构` |
|       | miss penalty                      | 未命中惩罚、缺失惩罚    |                      |
|       | name dependence                   | 名称相关                |                      |
|       | out-of-order                      | 乱序                    | OOO、in-order（按序） |
|       | pipeline                          | 流水线                  |                      |
|       | pipeline stage                    | 流水段、流水级          |                      |
|       | prediction                        | 预测                    |                      |
|       | prefetch                          | 预取                    |                      |
| PRF   | Physical Register File      | 物理寄存器堆            |                      |
|       | register file                     | 寄存器堆、寄存器文件    | 推荐翻译为`寄存器堆`   |
| RAW   | Read After Write            | 写后读                  | WAR、WAW              |
|       | reorder buffer                    | 重排序缓冲器            | ROB                   |
|       | reservation station               | 保留站                  |                      |
| RTL   | Register Transfer Language | 寄存器传输语言          |                      |
|       | speculation                       | 推测                    |                      |
|       | speculative execution             | 推测执行、推测式执行    |                      |
|       | stage                             | 阶段                    |                      |
|       | stall                             | 停顿                    |                      |
|       | superscalar pipeline              | 超标量流水线            |                      |
| WAR   | Write After Read           | 读后写                  | RAW                   |
| WAW   | Write After Write         | 写后写                  | RAW                   |
|       | writeback                         | 写回                    |                      |
|       | 5-stage pipeline                  | 5级流水线               |                      |
| BOOM  | Berkeley Out-of-Order Machine  | 伯克利乱序机器          |                      |
| CPI   | Cycles Per Instruction        | 每指令周期数            | IPC                   |

### Operating Systems

| Abbr. | English                                      | 中文                      | 备注/相关术语            |
| ---   | ---                                          | ---                       | ---                      |
| COW   | Copy-On-Write                                | 写时复制                  |                          |
|       | file                                         | 文件                      |                          |
| GRUB  | GNU GRUB                                     | GNU GRand Unified Bootloader |                      |
|       | guest OS                                     | 客户操作系统              |                          |
|       | hypervisor                                   | 超管系统、虚拟机监控器    | supervisor（主管系统）   |
|       | kernel                                       | 内核                      |                          |
| KVM   | Kernel-based Virtual Machine                | 基于内核的虚拟机          |                          |
| OS    | Operating System                            | 操作系统                  |                          |
|       | process                                      | 进程                      |                          |
| QEMU  | Quick Emulator                               | 快速模拟器                |                          |
|       | supervisor                                   | 主管系统                  | hypervisor（超管系统）   |
|       | thrashing                                    | 抖动、颠簸                |                          |
| UEFI  | Unified Extensible Firmware Interface       | 统一可扩展固件接口        |                          |
| UNIX  | UNIX Operating System                       | UNIX 操作系统             |                          |
| VMA   | Virtual Memory Area                         | 虚拟内存区域              |                          |
|       | virtual machine                              | 虚拟机                    |                          |
|       | working set                                  | 工作集                    |                          |
|       | zombie process                               | 僵尸进程                  |                          |

## 数据结构与算法

| Abbr. | English（术语/缩写）               | 中文/全称              | 相关领域/术语          |
| ---   | ---                               | ---                   | ---                  |
|       | algorithm                         | 算法                    |                      |
|       | data structure                    | 数据结构                |                      |
| NFA   | Nondeterministic Finite Automaton  | 非确定性有限状态自动机 |                      |
|       | space complexity                  | 空间复杂度              | time complexity（时间复杂度） |
|       | state                             | 状态                    |                      |
|       | state-transition equation         | 状态转移方程            |                      |
|       | stride                            | 步幅、步长              |                      |
|       | time complexity                   | 时间复杂度              | space complexity（空间复杂度） |
|       | weight                            | 权重                    |                      |

### 编码解码

| Abbr. | English（术语/缩写）               | 中文/全称              | 相关领域/术语          |
| ---   | ---                               | ---                   | ---                  |
|       | 1's complement                    | 反码                    |                      |
|       | 2's complement                    | 补码                    |                      |
| ASCII | American Standard Code for Information Interchange    | 美国信息交换标准字符码 | 一种字符编码          |
|       | binary                            | 二进制                  |                      |
|       | bit                               | 位/比特                 |                      |
|       | bit pattern                       | 位模式/比特模式         |                      |
|       | bit vector                        | 位向量/比特向量         |                      |
|       | byte                              | 字节                    |                      |
|       | decimal                           | 十进制                  |                      |
|       | decode                            | 解码                    | encode（编码）        |
|       | decoder                           | 解码器                  | encoder（编码器）      |
|       | double-precision floating point   | 双精度浮点              | single-precision floating point（单精度浮点） |
|       | encode                            | 编码                    | decode（解码）         |
|       | encoder                           | 编码器                  | decoder（解码器）      |
|       | floating point                    | 浮点                    |                      |
| GUID  | Globally Unique Identifier        | 全局唯一标识符          | UUID                  |
|       | hexadecimal                       | 十六进制                |                      |
|       | machine word                      | 机器字                  |                      |
|       | nibble                            | 半字节                  |                      |
|       | octal                             | 八进制                  |                      |
|       | one-hot encoding                  | 独热编码                |                      |
|       | overflow                          | 溢出（上溢）            | underflow（下溢）      |
| QR    | Quick Response Code                | 二维码                  |                      |
|       | qubit                             | 量子比特                |                      |
| RGB   | Red-Green-Blue                   | 红绿蓝                  | 一种颜色编码格式       |
|       | sign-magnitude                    | 原码                    |                      |
|       | single-precision floating point   | 单精度浮点              | double-precision floating point（双精度浮点） |
|       | word                              | 字                      | 同：`machine word`     |
|       | word                              | 字                      | 同：`machine word`     |
| UTF-16 | Unicode Transformation Format 16-bit | Unicode 16位转换格式   |                      |
| UTF-32 | Unicode Transformation Format 32-bit | Unicode 32位转换格式   |                      |
| UTF-8  | Unicode Transformation Format 8-bit  | Unicode 8位转换格式    |                      |
| UUID  | Universally Unique Identifier | 全局唯一标识符          | GUID                  |
|       | underflow                         | 下溢                    | overflow（上溢）      |
| XOR   | eXclusive OR           | 异或                    |                      |
| YUV   | YUV                    | YUV                     | 一种颜色编码格式       |
|       | zero                              | 零                      |                      |

### 数据结构

| Abbr. | English                                      | 中文                      | 备注/相关术语            |
| ---   | ---                                          | ---                       | ---                      |
| AVL  | AVL tree                                     | Adelson-Velsky and Landis Tree（AVL 树） | DA |
|       | adjacency list                               | 邻接表                    |                          |
|       | adjacency matrix                             | 邻接矩阵                  |                          |
|       | array                                        | 数组                      |                          |
|       | degree                                       | 度                        |                          |
|       | deque                                        | 双端队列                  | double-ended queue       |
|       | dimension                                    | 维度                      |                          |
|       | directed graph                               | 有向图                    |                          |
|       | disconnected graph                           | 非连通图                  |                          |
|       | double-ended queue                           | 双端队列                  | deque                    |
|       | dynamic array                                | 动态数组                  |                          |
|       | graph                                        | 图                        |                          |
|       | in-degree                                    | 入度                      | out-degree（出度）        |
|       | matrix                                       | 矩阵                      |                          |
|       | out-degree                                   | 出度                      | in-degree（入度）         |
|       | parent node                                  | 父节点                    |                          |
|       | priority queue                               | 优先队列                  |                          |
|       | queue                                        | 队列                      | front of the queue（队首）<br> rear of the queue（队尾） |
|       | recursion tree                               | 递归树                    |                          |
|       | red-black tree                               | 红黑树                    |                          |
|       | right-child node                             | 右子节点                  |                          |
|       | right subtree                                | 右子树                    |                          |
|       | root node                                    | 根节点                    |                          |
|       | set                                          | 集合                      |                          |
|       | stack                                        | 栈                        | stack bottom（栈底）<br> stack top（栈顶） |
|       | tail node                                    | 尾节点                    |                          |
|       | tree node                                    | 树节点                    |                          |
|       | undirected graph                             | 无向图                    |                          |
|       | vertex                                       | 顶点                      | edge（边）               |
|       | weighted graph                               | 有权图                    |                          |


### 经典算法

| Abbr. | English（术语/缩写）               | 中文/全称              | 相关领域/术语          |
| ---   | ---                               | ---                   | ---                  |
|       | backtracking algorithm            | 回溯算法                |                      |
|       | binary search                     | 二分查找/搜索           |                      |
|       | breadth-first search              | 广度优先搜索             | depth-first search    |
|       | breadth-first traversal           | 广度优先遍历             | depth-first traversal |
|       | bubble sort                       | 冒泡排序                 |                      |
|       | bucket sort                       | 桶排序                   |                      |
|       | counting sort                     | 计数排序                 |                      |
|       | depth-first search                | 深度优先搜索             | breadth-first search  |
|       | depth-first traversal             | 深度优先遍历             | breadth-first traversal |
|       | divide and conquer                | 分治                    |                      |
|       | dynamic programming               | 动态规划                |                      |
|       | edit distance problem             | 编辑距离问题             |                      |
|       | greedy algorithm                  | 贪心算法                |                      |
|       | heap sort                         | 堆排序                  |                      |
|       | heuristic algorithm               | 启发式算法              |                      |
|       | in-place algorithm                | 原地算法                |                      |
|       | insertion sort                    | 插入排序                |                      |
|       | knapsack problem                  | 背包问题                |                      |
|       | level-order traversal             | 层序遍历                |                      |
|       | linear programming                | 线性规划                |                      |
|       | merge sort                        | 归并排序                |                      |
|       | n-queens problem                  | n 皇后问题              |                      |
|       | open addressing                   | 开放寻址                |                      |
|       | permutations problem              | 全排列问题              |                      |
|       | pruning                           | 剪枝                    |                      |
|       | quick sort                        | 快速排序                |                      |
|       | radix sort                        | 基数排序                |                      |
|       | recursion                         | 递归                    |                      |
|       | selection sort                    | 选择排序                |                      |
|       | searching algorithm               | 搜索算法                |                      |
|       | sorting algorithm                 | 排序算法                |                      |
|       | subset-sum problem                | 子集和问题              |                      |
|       | top-$k$ problem                   | Top-$k$ 问题            |                      |
|       | tower of hanoi                    | 汉诺塔问题              |                      |
|       | travelling salesman problem       | 旅行商问题              |                      |

## 编程语言

| Abbr. | English                               | 中文                      | 备注/相关术语            |
| ---   | ---                                   | ---                       | ---                      |
| AST  | Abstract Syntax Tree                | 抽象语法树               |                          |
|       | arguments                           | 参数（实际参数）         | parameters（形式参数） |
|       | basic block                         | 基本块                  |                          |
|       | data type                           | 数据类型                |                          |
|       | deep copy                           | 深拷贝                  | shallow copy（浅拷贝） |
|       | function                            | 函数                    | method（方法）          |
| IR   | Intermediate Representation         | 中间表示                 |                          |
|       | leaf node                           | 叶节点                  |                          |
|       | left-child node                     | 左子节点                |                          |
|       | left subtree                        | 左子树                  |                          |
|       | level                               | 层                      |                          |
|       | linked list                         | 链表                    |                          |
|       | linked list node                    | 链表节点                |                          |
|       | list                                | 列表                    | Python                   |
|       | method                              | 方法                    | function（函数）        |
| OOP  | Object-Oriented Programming         | 面向对象程序设计         |                          |
|       | object                              | 对象                    |                          |
|       | parameters                          | 参数（形式参数）         | arguments（实际参数） |
|       | polymorphism                        | 多态                    |                          |
|       | primitive data types                | 基本数据类型            |                          |
| RE   | Regular Expression                  | 正则表达式               |                          |
|       | shallow copy                        | 浅拷贝                  | deep copy（深拷贝）     |
| SSA  | Static Single Assignment             | 静态单赋值               |                          |
|       | struct                              | 结构体                  |                          |
|       | tail recursion                      | 尾递归                  |                          |
|       | union                               | 联合体                  |                          |
|       | variable                            | 变量                    |                          |

## 开发环境

| Abbr. | English                               | 中文                      | 备注/相关术语            |
| ---   | ---                                   | ---                       | ---                      |
| CLI  | Command Line Interface                | 命令行接口               | GUI                     |
| GCC  | GNU Compiler Collection               | GNU 编译器集合           |                          |
| GDB  | GNU Debugger                          | GNU 调试器               |                          |
| GIT  | Git                                   | 全球信息追踪器；分布式版本控制系统 |                          |
| GUI  | Graphical User Interface              | 图形用户界面             | CLI                     |
| IDE  | Integrated Development Environment    | 集成开发环境             |                          |
|       | path                                  | 路径                    |                          |
|       | prompt                                | 提示符                  |                          |
|       | raw text                              | 原始文本                 |                          |
| TUI  | Text User Interface                   | 文本用户界面             |                          |
| XML  | eXtensible Markup Language            | 扩展置标语言             | 通常不译，直接用缩写   |
| YAML | YAML Ain't Markup Language            | YAML 不是置标语言        | 通常不译，直接用缩写   |

## 网络安全

| Abbr. | English                               | 中文                      | 备注/相关术语            |
| ---   | ---                                   | ---                       | ---                      |
|       | zero-day attack                       | 零日攻击               |                          |
|       | zero-day vulnerability                | 零日漏洞               |                          |

## 人工智能

| Abbr. | English                               | 中文                      | 备注/相关术语            |
| ---   | ---                                   | ---                       | ---                      |
|       | agent                                 | 智能体                |                          |
| AI    | Artificial Intelligence               | 人工智能               |                          |
|       | backpropagation                       | 反向传播               |                          |
|       | deep learning                         | 深度学习                |                          |
| DNN   | Deep Neural Network                   | 深度神经网络          |                          |
| GenAI | Generative Artificial Intelligence    | 生成式人工智能        |                          |
| GPT   | Generative Pre-trained Transformer    | 生成式预训练变换器    |                          |
| LLM   | Large Language Model                  | 大语言模型            |                          |
| MCP   | Model Context Protocol                | 模型上下文协议        |                          |
| ML    | Machine Learning                      | 机器学习              |                          |
| NLP   | Natural Language Processing           | 自然语言处理           |                          |
|       | next-word prediction                  | 下一单词预测          |                          |
| OCR   | Optical Character Recognition         | 光学字符识别           |                          |
|       | pre-training                          | 预训练                |                          |
|       | prompt                                | 提示词                 |                          |
| RNN   | Recurrent Neural Network              | 循环神经网络           |                          |
|       | self-attention mechanism              | 自注意力机制          |                          |
|       | self-supervised learning              | 自监督学习            |                          |
|       | token                                 | 词元                  |                          |
|       | transformer                           | 变换器               | 通常不译，直接用英文 |

