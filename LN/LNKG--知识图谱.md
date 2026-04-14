# 知识图谱（Knowledge Graph）

## Hello-Algo 内容结构

本书的主要内容如下图所示。

- **复杂度分析**：数据结构和算法的评价维度与方法。时间复杂度和空间复杂度的推算方法、常见类型、示例等。
- **数据结构**：基本数据类型和数据结构的分类方法。数组、链表、栈、队列、哈希表、树、堆、图等数据结构的定义、优缺点、常用操作、常见类型、典型应用、实现方法等。
- **算法**：搜索、排序、分治、回溯、动态规划、贪心等算法的定义、优缺点、效率、应用场景、解题步骤和示例问题等。

![tp](assets/hello_algo_mindmap_tp.png)

![本书主要内容](assets/hello_algo_mindmap.png)


## 树的知识图谱


```mermaid
mindmap
  root(Generic Tree)
    Notations{{**NOTATIONS**}}
    	Node,Edge
    	Root,Subtree
    	Parent,Children,Sibling,Leaf
    	Path: Level,Height,Depth
      
    Representation{{**REPRESENTATION**}}
      Nested Parentheses
      Node-Based
      Indented Tree
      Adjacency List
      	Disjoint Set
      	Trie
      
    Binary Tree{{**Binary Tree**}}
      Applications
      	Parse Tree
      	Tree Traversals
      	Huffman
      Priority Queues with Binary Heaps
      Binary Search Tree
      AVL Tree
      Segment Tree,BIT
      *KD Tree
```

<center>树的知识图谱</center>

## 图的知识图谱

```mermaid
mindmap
  Graph (Graph)
    Notation{{**NOTATIONS**}}
    	Vertex,Edge
    	Path, Weight
      
    Representation{{**REPRESENTATION**}}
      Matrix
      Adjacency List
      
    Algorithm{{**ALGORITHM**}}
    	Elementary Graph Algorithms(Elementary Graph Algorithm)
    		BFS
    		DFS
    	Shortest Path(Shortest Path)
    		Dijkstra
    		*Bellman-Ford
    		Floyd-Warshall 
    	Topological Sorting
    		Depth First Forest
    		Karn / BFS
    	*Critical Path Method
    	MST(Minimum Spanning Tree)
    		Prim
    		Kruskal
    	SCC(Strongly Connected Component)
    		Kosaraju(Kosaraju / 2 DFS)
    		*Tarjan
      

```

<center>图的知识图谱</center>