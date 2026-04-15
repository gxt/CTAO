# TERM--术语对照

- 术语：Terminology

## 经典算法

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| backtracking algorithm            | 回溯算法       |  |
| binary search                     | 二分查找/搜索  |  |
| breadth-first search              | 广度优先搜索   | depth-first search |
| breadth-first traversal           | 广度优先遍历   | depth-first traversal |
| bubble sort                       | 冒泡排序       |  |
| bucket sort                       | 桶排序         |  |
| counting sort                     | 计数排序       |  |
| depth-first search                | 深度优先搜索   | breadth-first search |
| depth-first traversal             | 深度优先遍历   | breadth-first traversal |
| divide and conquer                | 分治           |  |
| dynamic programming               | 动态规划       |  |
| edit distance problem             | 编辑距离问题   |  |
| greedy algorithm                  | 贪心算法       |  |
| heap sort                         | 堆排序         |  |
| heuristic algorithm               | 启发式算法     |  |
| in-place algorithm                | 原地算法       |  |
| insertion sort                    | 插入排序       |  |
| knapsack problem                  | 背包问题       |  |
| level-order traversal             | 层序遍历       |  |
| linear programming                | 线性规划       |  |
| merge sort                        | 归并排序       |  |
| n-queens problem                  | n 皇后问题     |  |
| permutations problem              | 全排列问题     |  |
| quick sort                        | 快速排序       |  |
| radix sort                        | 基数排序       |  |
| selection sort                    | 选择排序       |  |
| searching algorithm               | 搜索算法       |  |
| sorting algorithm                 | 排序算法       |  |
| subset-sum problem                | 子集和问题     |  |
| top-$k$ problem                   | Top-$k$ 问题   |  |
| tower of hanoi                    | 汉诺塔问题     |  |
| travelling salesman problem       | 旅行商问题     |  |

## 指令系统体系结构

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| CISC                              | Complex Instruction Set Computer | RISC |
| ISA                               | Instruction Set Architecture（指令系统体系结构） |  |
| RISC                              | Reduced Instruction Set Computer | CISC |
| ---                               | ---           | ---           |
| abort                             | 中止              | 通常指不可恢复的同步异常 |
| architecture                      | 体系结构（简单设计译为`架构`）   |  |
| branch instruction                | 分支/转移指令    |  |
| control flow instruction          | 控制流指令      |  |
| exception                         | 异常           | 异常通常为同步的 |
| fault                             | 故障           | 通常指可恢复的同步异常 |
| fence instruction                 | 屏障指令       |  |
| instruction                       | 指令           |  |
| instruction set                   | 指令系统（描述附加或扩展设计时翻译为`指令集`）   |  |
| interrupt                         | 中断              | 中断通常为异步的 |
| jump instruction                  | 跳转指令       |  |
| load instruction                  | 取数指令、装入指令  | store instruction |
| store instruction                 | 存数指令、存储指令 | load instruction |
| system call                       | 系统调用           |  |
| trap                              | 陷入               |  |

- branch instruction：有时泛指所有控制转移类指令，有时仅指条件分支指令或条件转移指令
- 不同的处理器设计，对于exception/interrupt的含义并不统一，需要根据具体处理器的文档来理解

## 存储层次

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| MMU                               | Memory Management Unit（存储管理部件）     |  |
| NVRAM                             | Non-volatile Random Access Memory（非易失性随机访问存储器） |  |
| RAM                               | random-access memory（随机访问存储器） |  |
| ROM                               | Read-Only Memory（只读存储器） |  |
| TLB                               | Translation Look-aside Buffer（转换旁视缓冲器，简称`快表`） |  |
| ---                               | ---           | ---           |
| access fault                      | 访问故障          |  |
| address                           | 地址              |  |
| address space                     | 地址空间          |  |
| addressing                        | 寻址              |  |
| addressing mode                   | 寻址模式         |  |
| cache line                        | 高速缓存行       |  |
| cache memory                      | 高速缓存存储器（简称`高速缓存`或`缓存`）     |  |
| coherence                         | （cache）一致性        | consistency |
| consistency                       | 一致性                 | coherence   |
| hard disk                         | 硬盘           |  |
| homonyms                          | 同名           | synonyms（同义） |
| hit                               | 命中           | miss |
| hit rate                          | 命中率         | miss rate |
| locality principle                | 局部性原理     |  |
| main memory                       | 主存           | 俗称`内存` |
| memory                            | 存储器         |  |
| memory disambiguation             | 存储消歧       |  |
| memory hierarchy                  | 存储器层次结构、存储层次 |  |
| miss                              | 未命中         | hit |
| miss rate                         | 未命中率         | hit rate |
| page                              | 页、页面         | 抽象概念可用`页`，具体操作则用`页面` |
| page fault                        | 页面故障       | 若翻译为`缺页故障`，其表述并不全面 |
| page table                        | 页表            |   |
| page table entry                  | 页表项          | PTE |
| page table walker                 | 页表步进器、页表遍历器 | PTW |
| paged/paging                      | 分页/页式      |  |
| physical address                  | 物理地址       | PA |
| physical memory                   | 物理存储器     | PM |
| secondary memory                  | 次级存储、二级存储  |  |
| storage                           | 存贮器         | 俗称`外存` |
| synonyms                          | 同义           | homonyms（同名） |
| virtual address                   | 虚拟地址       | VA |
| virtual memory                    | 虚拟存储器     | VM |

- consistency解决的是访存操作以何种顺序被所有处理器观测到的问题（有序的问题），coherence解决的是一份数据的多个缓存副本是否相同的问题（没有序的问题）
- homonyms/synonyms：同名指（不同进程的）相同虚拟地址映射到不同物理地址。同义指（不同进程的）不同虚拟地址映射到同一物理地址。
- memory：存储器；狭义用法是指main memory（俗称内存，与外存对应）
- miss：Intel/AMD/ARM的中文技术手册中采用的是`未命中`；若上下文已明确讨论高速缓存或存储层级，可使用`缺失`来简化术语，如`缺失率`、`缺失惩罚`
- Page Table Walking/walker：历史原因，一直翻译为页表遍历/页表遍历器，然而实际上，walking或walk的含义应直译为 `步进`

## 微体系结构

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| ARF                               | Architectural Register File                           |  |
| BOOM                              | Berkeley Out-of-Order Machine  |   |
| BTB                               | Branch Target Buffer（分支/转移目标缓冲器） |  |
| CAM                               | Content-Addressable Memory（按内容寻址存储器） |  |
| CPI                               | Cycles Per Instruction（每指令周期数） | IPC |
| IPC                               | Instructions per Cycle（每周期指令数）   | CPI |
| PRF                               | Physical Register File      |  |
| RAW                               | Read After Write（写后读） | WAR、WAW |
| RTL                               | Register Transfer Language（寄存器传输语言） |  |
| WAR                               | Write After Read（读后写） | RAW |
| WAW                               | Write After Write（写后写） | RAW |
| ---                               | ---           | ---           |
| 5-stage pipeline                  | 5级流水线       |  |
| branch misprediction              | 分支预测错误     |  |
| branch prediction                 | 分支/转移预测    |  |
| bypass                            | 旁路           |  |
| commit                            | 提交           |  |
| control dependence                | 控制相关        |  |
| data dependence                   | 数据相关        |  |
| decode                            | 译码           |  |
| dependence                        | 相关、依赖      | 推荐翻译为`相关` |
| dispatch                          | 分发           |  |
| execution                         | 执行           |  |
| fetch                             | 取指           |  |
| flush pipeline                    | 排空流水线     |  |
| forward                           | 前递           |  |
| hazard                            | 冒险           |  |
| in-flight instructions            | 处理中指令、未完成指令    |  |
| in-order                          | 按序              | out-of-order（乱序） |
| issue                             | 发射              |  |
| load-store architecture           | 装入-存储体系结构  |  |
| load-store queue                  | 装入-存储队列      | LSQ |
| load-store unit                   | 装入-存储部件      | LSU |
| micro-code                        | 微码              |  |
| micro-op                          | 微操作            | UOP |
| microarchitecture                 | 微体系结构        | 描述某一具体的微体系结构实现版本，译为`微架构` |
| miss penalty                      | 未命中惩罚、缺失惩罚       |  |
| name dependence                   | 名称相关        |  |
| out-of-order                      | 乱序           | OOO、in-order（按序） |
| pipeline                          | 流水线          |  |
| pipeline stage                    | 流水段、流水级  |  |
| prediction                        | 预测           |  |
| prefetch                          | 预取           |  |
| register file                     | 寄存器堆、寄存器文件      | 推荐翻译为`寄存器堆` |
| reorder buffer                    | 重排序缓冲器    | ROB |
| reservation station               | 保留站         |  |
| speculation                       | 推测           |  |
| speculative execution             | 推测执行、推测式执行 |  |
| stage                             | 阶段           |  |
| stall                             | 停顿           |  |
| superscalar pipeline              | 超标量流水线   |  |
| writeback                         | 写回           |  |

## 编解码
| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| 1's complement                    | 反码           |  |
| 2's complement                    | 补码           |  |
| ASCII                             | American Standard Code for Information Interchange    | 一种字符编码 |
| binary                            | 二进制         |  |
| bit                               | 位/比特        |  |
| bit pattern                       | 位模式/比特模式      |  |
| bit vector                        | 位向量/比特向量      |  |
| byte                              | 字节           |  |
| decimal                           | 十进制         |  |
| decode                            | 解码           | encode（编码） |
| decoder                           | 解码器         | encoder（编码器） |
| encode                            | 编码           | decode（解码） |
| encoder                           | 编码器         | decoder（解码器） |
| hexadecimal                       | 十六进制       |  |
| machine word                      | 机器字             |  |
| nibble                            | 半字节                |  |
| octal                             | 八进制         |  |
| one-hot encoding                  | 独热编码       |  |
| RGB                               | Red-Green-Blue | 一种颜色编码格式 |
| sign-magnitude                    | 原码           |  |
| word                              | 字             | 同：`machine word` |
| UTF-16                            | Unicode Transformation Format 16-bit |  |
| UTF-32                            | Unicode Transformation Format 32-bit |  |
| UTF-8                             | Unicode Transformation Format 8-bit |  |
| UUID                              | Universally Unique Identifier | GUID |
| YUV                               | YUV            | 一种颜色编码格式 |

## A

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| AI                                | Artificial Intelligence（人工智能） |  |
| ANSI                              | American National Standard Institute                  | 标准机构 |
| AST                               | Abstract Syntax Tree（抽象语法树）                     |  |
| AVL tree                          | Adelson-Velsky and Landis Tree（AVL 树）              | DA |
| ---                               | ---           | ---           |
| adjacency list                    | 邻接表            |  |
| adjacency matrix                  | 邻接矩阵          |  |
| algorithm                         | 算法              |  |
| arguments                         | 参数（实际参数）   | parameters（形式参数） |
| array                             | 数组              |  |
| architect                         | 架构师            |  |
| asymptotic complexity analysis    | 渐近复杂度分析    |  |
| asymptotic upper bound            | 渐近上界         |  |
| autoregressive model              | 自回归模型       |  |

## B
| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| BLOB                              | Binary Large Object（二进制大对象） |  |
| BPE                               | Byte Pair Encoding（字节对编码） | AI |
| ---                               | ---           | ---           |
| backpropagation                   | 反向传播         | AI |
| balance factor                    | 平衡因子       |  |
| barrier                           | 屏障           |  |
| basic block                       | 基本块         |  |
| benchmark                         | 基准测试       |  |
| big-$O$ notation                  | 大 $O$ 记号    |  |
| binary search tree                | 二叉搜索树     | balanced binary search tree（平衡二叉搜索树） |
| binary tree                       | 二叉树         | balanced binary tree（平衡二叉树）<br> complete binary tree（完全二叉树）<br> full binary tree（完满二叉树）<br> perfect binary tree（完美二叉树）|
| bucket                            | 桶             |  |
| buffer                            | 缓冲区（软件）、缓冲器（体系结构）   |  | 
| bug                               | 不符合预期行为的异常，可译为`漏洞`、`缺陷`、`错误`  |  |

- buffer：`缓冲区`表达抽象的、非实体的存储区域概念，而`缓冲器`则包含实现部件

## C

| English（术语/缩写）               | 中文/全称      |  相关领域/术语  |
| ---                               | ---           | ---           |
| CFG                               | Context-Free Grammar（上下文无关文法） |  |
| CLI                               | Command Line Interface（命令行接口） | GUI |
| COFF                              | Common Object File Format（公共对象文件格式） |  |
| COW                               | Copy-On-Write（写时复制） |  |
| CPU                               | Central Processing Unit（中央处理器） |  |
| CSS                               | Cascading Style Sheets（层叠样式表） |  |
| ---                               | ---           | ---           |
| chip                              | 芯片           |  |
| chiplet                           | 芯粒           |  |
| class                             | 类             |  |
| code                              | 代码           |  |
| connected graph                   | 连通图         |  |
| constraint                        | 约束           |  |
| context                           | 上下文          |  |
| context vector                    | 上下文向量      |  |
| core                              | 核芯（简称`核`）   |  |
| cycle                             | 周期           |  |
| cycle accurate simulator          | 周期精确模拟器 |  |

## D

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| DFA                               | Deterministic Finite Automaton（确定性有限状态自动机） |  |
| DNN                               | Deep Neural Network（深度神经网络） |  |
| ---                               | ---           | ---           |
| data structure                    | 数据结构       |  |
| data type                         | 数据类型       |  |
| debug                             | 调试           |  |
| deep copy                         | 深拷贝         | shallow copy（浅拷贝） |
| deep learning                     | 深度学习       |  |
| degree                            | 度             |  |
| delay                             | 延迟          | latency（时延） |
| deque                             | 双端队列       | double-ended queue |
| die                               | 管芯          |  |
| dimension                         | 维度           |  |
| directed graph                    | 有向图         |  |
| disconnected graph                | 非连通图       |  |
| double-ended queue                | 双端队列       | deque |
| double-precision floating point   | 双精度浮点      | single-precision floating point（单精度浮点） |
| dynamic array                     | 动态数组       |  |

## E

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| ELF                               | Executable and Linkable Format（可执行和可链接格式） |  |
| ---                               | ---           | ---           |
| edge                              | 边             | vertex（顶点） |
| embedding/embedded                | 嵌入/嵌入式     |  |
| emergence                         | 涌现           |  |
| emulation                         | 仿真           | simulation（模拟） |
| encapsulation                     | 封装           |  |

## F

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| FIFO                              | first-in first-out | LIFO  |
| FPU                               | Floating-Point Unit（浮点运算部件） |  |
| ---                               | ---           | ---           |
| file                              | 文件           |  |
| fine-tuning                       | 微调           | instruction fine-tuning（指令微调）<br> classification fine-tuning（分类微调） |
| floating point                    | 浮点           |  |
| foundation model                  | 基础模型       |  |
| function                          | 函数           | method（方法） |

## G

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| GCC                               | GNU Compiler Collection |  |
| GDB                               | GNU Debugger |  |
| GenAI                             | Generative Artificial Intelligence（生成式人工智能）        |  |
| GIT                               | Git（Global Information Tracker）；一种分布式版本控制系统     |  |
| GPG                               | GNU Privacy Guard |  |
| GPIO                              | General Purpose Input/Output |  |
| GPT                               | Generative Pre-trained Transformer（生成式预训练变换器） |  |
| GPU                               | Graphics Processing Unit |  |
| GRUB                              | GNU GRUB（GNU GRand Unified Bootloader） |  |
| GUI                               | Graphical User Interface | CLI |
| GUID                              | Globally Unique Identifier | UUID |
| ---                               | ---           | ---           |
| gateway                           | 网关           |  |
| graph                             | 图             |  |
| guest OS                          | 客户操作系统    |  |

## H

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| HDMI                              | High-Definition Multimedia Interface |  |
| HTML                              | Hypertext Markup Language（超文本置标语言） |  |
| HTTP                              | Hypertext Transfer Protocol（超文本传输协议） |  |
| HTTPS                             | Hypertext Transfer Protocol Secure（安全超文本传输协议） |  |
| ---                               | ---           | ---           |
| hash                              | 哈希、散列      |  |
| hash collision                    | 哈希冲突       |  |
| hash function                     | 哈希函数       |  |
| hash set                          | 哈希集合       |  |
| hash table                        | 哈希表         |  |
| head node                         | 头节点         |  |
| heap                              | 堆             | max heap（大顶堆） <br> min heap（小顶堆） |
| heapify                           | 堆化           |  |
| height                            | 高度           |  |
| host                              | 主机、宿主机    |  |
| hypervisor                        | 超管系统、虚拟机监控器   | supervisor（主管系统） |

## I

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| IDE                               | Integrated Development Environment（集成开发环境） |  |
| ILP                               | Instruction-Level Parallelism（指令级并行）   |  |
| IR                                | Intermediate Representation（中间表示） |  |
| ---                               | ---           | ---           |
| in-degree                         | 入度           | out-degree（出度） |
| index                             | 索引           |  |
| inheritance                       | 继承           |  |
| initial state                     | 初始状态       |  |
| iteration                         | 迭代           |  |

## J

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| JIT                               | Just-In-Time Compilation |  |
| JSON                              | JavaScript Object Notation |  |
| JTAG                              | Joint Test Action Group |  |
| JVM                               | Java Virtual Machine |  |
| ---                               | ---           | ---           |

## K

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| K8S                               | Kubernetes |  |
| KMP                               | Knuth-Morris-Pratt |  |
| KVM                               | Kernel-based Virtual Machine |  |
| KVM switch                        | Keyboard-Video-Mouse Switch（KVM 切换器） |  |
| ---                               | ---           | ---           |
| kernel                            | 内核           |  |
| key                               | 键             |  |
| key-value store                   | 键值存储       |  |
| keyboard                          | 键盘           |  |

## L

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| LIFO                              | last-in first-out | FIFO |
| LLM                               | Large Language Model（大语言模型） |  |
| ---                               | ---           | ---           |
| latency                           | 时延           | delay（延迟） |
| leaf node                         | 叶节点         |  |
| left-child node                   | 左子节点       |  |
| left subtree                      | 左子树         |  |
| level                             | 层             |  |
| linked list                       | 链表           |  |
| linked list node                  | 链表节点       |  |
| list                              | 列表           |  |
| load factor                       | 负载因子       |  |
| lock                              | 锁             |  |
| loop                              | 循环           |  |
| lazy deletion                     | 懒删除         |  |

- load-store architecture：《中国大百科全书》翻译为`取数-存数结构`，《术语在线》翻译为`加载-存储体系结构`

## M

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| ML                                | Machine Learning（机器学习） |  |
| ---                               | ---           | ---           |
| manycore                          | 众核           |  |
| matrix                            | 矩阵           |  |
| method                            | 方法           | function（函数） |
| mouse                             | 鼠标           |  |
| multicore                         | 多核           |  |

## N

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| NFA                               | Nondeterministic Finite Automaton（非确定性有限状态自动机） |  |
| NLP                               | Natural Language Processing（自然语言处理） |  |
| NMI                               | non-maskable interrupts（不可屏蔽中断） |  |
| ---                               | ---           | ---           |
| next-word prediction              | 下一单词预测          |  |

## O

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| OCR                               | Optical Character Recognition（光学字符识别） |  |
| OOP                               | Object-Oriented Programming（面向对象程序设计） |  |
| OS                                | Operating System（操作系统） |  |
| ---                               | ---           | ---           |
| object                            | 对象           |  |
| off-chip                          | 片外           | on-chip |
| on-chip                           | 片上           | off-chip |
| open addressing                   | 开放寻址       |  |
| out-degree                        | 出度           | in-degree（入度） |
| overflow                          | 溢出（上溢）    | underflow（下溢） |

## P

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| parameters                        | 参数（形式参数）  | arguments（实际参数） |
| parent node                       | 父节点         |  |
| path                              | 路径           |  |
| polymorphism                      | 多态           |  |
| pre-training                      | 预训练         |  |
| primitive data types              | 基本数据类型   | DA |
| priority queue                    | 优先队列       |  |
| process                           | 进程           |  |
| processor                         | 处理器         |  |
| prompt                            | 提示/提示符/提示词    |  |
| pruning                           | 剪枝           |  |

## Q

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| QEMU                              | Quick Emulator |  |
| QoS                               | Quality of Service |  |
| QR Code                           | Quick Response Code |  |
| ---                               | ---           | ---           |
| quantum computing                 | 量子计算       |  |
| qubit                             | 量子比特       |  |
| queue                             | 队列           | front of the queue（队首）<br> rear of the queue（队尾） |

## R

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| RE                                | Regular Expression（正则表达式） |  |
| RNG                               | Random Number Generator（随机数发生器） |  |
| RNN                               | Recurrent Neural Network（循环神经网络） |  |
| ---                               | ---           | ---           |
| raw text                          | 原始文本       |  |
| recursion                         | 递归           |  |
| recursion tree                    | 递归树         |  |
| red-black tree                    | 红黑树         |  |
| replacement policy                | 置换策略       |  |
| right-child node                  | 右子节点       |  |
| right subtree                     | 右子树         |  |
| root node                         | 根节点         |  |

## S

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| SSA                               | Static Single Assignment（静态单赋值） |  |
| ---                               | ---           | ---           |
| sampled                           | 抽样           |  |
| self-attention mechanism          | 自注意力机制    | AI |
| self-supervised learning          | 自监督学习       | AI |
| set                               | 集合           |  |
| shallow copy                      | 浅拷贝         | deep copy（深拷贝） |
| simulation/emulation              | 模拟/仿真       |  |
| single-precision floating point   | 单精度浮点      | double-precision floating point（双精度浮点） |
| sliding window                    | 滑动窗口       |  |
| space complexity                  | 空间复杂度     | time complexity（时间复杂度） |
| stack                             | 栈             | stack bottom（栈底）<br> stack top（栈顶） |
| state                             | 状态           |  |
| state-transition equation         | 状态转移方程   |  |
| stride                            | 步幅、步长        |  |
| struct                            | 结构体         |  |
| supervisor                        | 主管系统        | hypervisor（超管系统） |

- sampled：推荐翻译`抽样`，不建议`采样`（抽样的含义中所抽取的样本不丧失代表性，而采样没有该含义）

## T

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| tail node                         | 尾节点         |  |
| tail recursion                    | 尾递归         |  |
| thrashing                         | 抖动、颠簸      |  |
| time complexity                   | 时间复杂度     | space complexity（空间复杂度） |
| token                             | 词元           | AI |
| touchscreen                       | 触摸屏         |  |
| transformer                       | 变换器（通常不译，直接用英文）       | AI |
| tree node                         | 树节点         |  |

## U

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| UART                              | Universal Asynchronous Receiver-Transmitter |  |
| UDP                               | User Datagram Protocol |  |
| UEFI                              | Unified Extensible Firmware Interface |  |
| UNIX                              | UNIX Operating System |  |
| UPS                               | Uninterruptible Power Supply |  |
| URL                               | Uniform Resource Locator |  |
| USB                               | Universal Serial Bus（通用串行总线） |  |
| ---                               | ---           | ---           |
| uncore                            | 未核芯         |  |
| underflow                         | 下溢          | overflow（上溢） |
| underflow                         | 下溢          | overflow（上溢） |
| undirected graph                  | 无向图         |  |
| union                             | 联合体         |  |

## V

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| VMA                               | Virtual Memory Area |  |
| VPN                               | Virtual Private Network |  |
| ---                               | ---           | ---           |
| variable                          | 变量           |  |
| vertex                            | 顶点           | edge（边） |
| virtual machine                   | 虚拟机         |  |

## W

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| wafer                             | 晶圆           |  |
| weight                            | 权重           |  |
| weighted graph                    | 有权图         |  |
| working set                       | 工作集         |  |

## X

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| XML                               | eXtensible Markup Language（扩展置标语言） |  |
| XOR                               | eXclusive OR（异或）           |  |

## Y

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| YAML                              | YAML Ain't Markup Language（YAML不是置标语言） |  |

## Z

| English（术语/缩写）               | 中文/全称      | 相关领域/术语  |
| ---                               | ---           | ---           |
| zero                              | 零             |  |
| zero-day attack                   | 零日攻击       |  |
| zero-day vulnerability            | 零日漏洞       |  |
| zombie process                    | 僵尸进程       |  |
