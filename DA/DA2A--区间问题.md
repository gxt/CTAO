
# 区间问题

一文读懂五类常见区间问题，https://zhuanlan.zhihu.com/p/446371757

增加了6 覆盖连续区间

> 练习网址，https://leetcode.cn 。leetcode只需要完成核心代码就可以，不用写输入输出部分。
>
> 核心代码已经指定好类名、方法名、参数名，请勿修改或重命名，直接返回值即可。



## 1 区间合并

### 1.1 题意描述

区间合并问题大概**题意**就是：

给出一堆区间，要求**合并**所有**有交集的区间** （端点处相交也算有交集）。最后问合并之后的**区间**。

如下图所示：

![img](https://pic4.zhimg.com/80/v2-6e3bb59ed6c14eacfa1331c645d4afdf_1440w.jpg)

<center>区间合并问题示例：合并结果包含3个区间</center>



### 1.2 解题步骤

【**步骤一**】：按照区间**左端点**从小到大排序。

【**步骤二**】：维护前面区间中最右边的端点为ed。从前往后枚举每一个区间，判断是否应该将当前区间视为新区间。

假设当前遍历到的区间为第i个区间 $[l_i,r_i]$，有以下两种情况：

- $l_i \le ed$：说明当前区间与前面区间**有交集**。因此**不需要**增加区间个数，但需要设置 $ed = max(ed, r_i)$。
- $l_i > ed$: 说明当前区间与前面**没有交集**。因此**需要**增加区间个数，并设置 $ed = max(ed, r_i)$。



### 练习LC M56.合并区间

https://leetcode.cn/problems/merge-intervals/

以数组 `intervals` 表示若干个区间的集合，其中单个区间为 `intervals[i] = [starti, endi]` 。请你合并所有重叠的区间，并返回 *一个不重叠的区间数组，该数组需恰好覆盖输入中的所有区间* 。

 

**示例 1：**

```
输入：intervals = [[1,3],[2,6],[8,10],[15,18]]
输出：[[1,6],[8,10],[15,18]]
解释：区间 [1,3] 和 [2,6] 重叠, 将它们合并为 [1,6].
```

**示例 2：**

```
输入：intervals = [[1,4],[4,5]]
输出：[[1,5]]
解释：区间 [1,4] 和 [4,5] 可被视为重叠区间。
```

 

**提示：**

- `1 <= intervals.length <= 10^4`
- `intervals[i].length == 2`
- `0 <= starti <= endi <= 10^4`





```python
from typing import List
import sys

class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        # 对区间进行排序
        intervals.sort()

        res = []
        st, ed = -sys.maxsize, -sys.maxsize
        
        for v in intervals:
            if ed == -sys.maxsize:
                st, ed = v[0], v[1]
            elif v[0] <= ed:
                ed = max(v[1], ed)
            elif v[0] > ed:
                res.append([st, ed])
                st, ed = v[0], v[1]

        if ed != -sys.maxsize:
            res.append([st, ed])

        return res
```

这里有几个需要注意的地方：

- `-sys.maxsize` 用于表示最小整数值。
- 类型注解（如 `List[List[int]]`）是可选的，但有助于提高代码的可读性和类型检查工具的效率。



### M29947:校门外的树又来了

greedy, interval merging, stack, http://cs101.openjudge.cn/practice/29947/

某校大门外长度为L的马路上有一排树，每两棵相邻的树之间的间隔都是1米。我们可以把马路看成一个数轴，马路的一端在数轴0的位置，另一端在L的位置；数轴上的每个整数点，即0，1，2，……，L，都种有一棵树。 马路上有一些区域要用来建地铁，这些区域用它们在数轴上的起始点和终止点表示。已知任一区域的起始点和终止点的坐标都是整数，区域之间可能有重合的部分。现在要把这些区域中的树（包括区域端点处的两棵树）移走。你的任务是计算将这些树都移走后，马路上还有多少棵树。

**输入**

输入的第一行有两个整数L（1 <= L <= 10^9）和 M（1 <= M <= 100），L代表马路的长度，M代表区域的数目，L和M之间用一个空格隔开。接下来的M行每行包含两个不同的整数，用一个空格隔开，表示一个区域的起始点和终止点的坐标。

**输出**

输出包括一行，这一行只包含一个整数，表示马路上剩余的树的数目。

样例输入

```
500 3
150 300
100 200
470 471
```

样例输出

```
298
```

来源

yan



思路：区间合并。排序是为了保证取交集的方向唯一，这种单向关系可以避免分类讨论。

```python
L, M = map(int, input().split())
intervals = []

for _ in range(M):
    s, e = map(int, input().split())
    if s > e:
        s, e = e, s
    intervals.append((s, e))

# 按起点排序
intervals.sort()

# 合并区间
merged = []
for s, e in intervals:
    if not merged or s > merged[-1][1] + 1:
        merged.append([s, e])
    else:
        merged[-1][1] = max(merged[-1][1], e)

# 计算被砍掉的树总数
cut = sum(e - s + 1 for s, e in merged)
remain = (L + 1) - cut

print(remain)
```





## 2 选择不相交区间

### 2.1 题意描述

**选择不相交区间问题**大概题意就是：

给出一堆区间，要求选择**尽量多**的区间，使得这些区间**互不相交**，求可选取的区间的**最大数量**。这里端点相同也算有重复。

> **优先保留结束早的区间**，这样能为后续留下更多空间，从而保留更多区间。

如下图所示：

![img](https://pic1.zhimg.com/80/v2-690f7e53fd34c39802f45f48b59d5c5a_1440w.webp)

<center>选择不相交区间问题示例：结果包含3个区间</center>

### 2.2 解题步骤

【**步骤一**】：按照区间**右端点**从小到大排序。

【**步骤二**】：从前往后依次枚举每个区间。

假设当前遍历到的区间为第i个区间 $[l_i,r_i]$，有以下两种情况：

- $l_i \le ed$：说明当前区间与前面区间有交集。因此直接跳过。
- $l_i > ed$: 说明当前区间与前面没有交集。因此选中当前区间，并设置 $ed = r_i$。



### 练习LC M435.无重叠区间

https://leetcode.cn/problems/non-overlapping-intervals/

给定一个区间的集合 `intervals` ，其中 `intervals[i] = [starti, endi]` 。返回 *需要移除区间的最小数量，使剩余区间互不重叠* 。

**注意** 只在一点上接触的区间是 **不重叠的**。例如 `[1, 2]` 和 `[2, 3]` 是不重叠的。

 

**示例 1:**

```
输入: intervals = [[1,2],[2,3],[3,4],[1,3]]
输出: 1
解释: 移除 [1,3] 后，剩下的区间没有重叠。
```

**示例 2:**

```
输入: intervals = [ [1,2], [1,2], [1,2] ]
输出: 2
解释: 你需要移除两个 [1,2] 来使剩下的区间没有重叠。
```

**示例 3:**

```
输入: intervals = [ [1,2], [2,3] ]
输出: 0
解释: 你不需要移除任何区间，因为它们已经是无重叠的了。
```

 

**提示:**

- `1 <= intervals.length <= 10^5`
- `intervals[i].length == 2`
- `-5 * 10^4 <= starti < endi <= 5 * 10^4`





```python
from typing import List
import sys

class Solution:
    def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
        # 按照右端点从小到大排序
        intervals.sort(key=lambda x: x[1])

        res = 0
        ed = -sys.maxsize
        
        for v in intervals:
            if ed <= v[0]:
                res += 1
                ed = v[1]

        return len(intervals) - res
```



## 3 区间选点问题

### 3.1 题意描述

**区间选点问题**大概题意就是：

给出一堆区间，取**尽量少**的点，使得每个区间内**至少有一个点**（不同区间内含的点可以是同一个，位于区间端点上的点也算作区间内）。

如下图所示：

![img](https://pica.zhimg.com/80/v2-a7ef021e1191ec53f20609ba870b44ba_1440w.webp)

<center>区间选点问题示例，最终至少选择3个点</center>



这个题可以转化为上一题的**求最大不相交区间**的数量。

对于这些**最大的不相交区间**，肯定是每个区间都需要选出一个点。而其他的区间都是和这些选出的区间有重复的，我们只需要把点的位置选在**重合**的部分即可。

也可以换一种思路：

我们将区间按照**右端点**从小到大排序，这时我们应该尽量选择**当前区间最右边的点**。

因为最右边的点可能和下面的其他区间重复，所以至少不比选择区间靠前位置的点差。

所以，最后的解法与选择不相交区间问题解法完全一样。

### 3.2 解题步骤

【**步骤一**】：按照区间右端点从小到大排序。

【**步骤二**】：从前往后依次枚举每个区间。

假设当前遍历到的区间为第i个区间 $[l_i,r_i]$，有以下两种情况：

- $l_i \le ed$：说明当前区间与前面区间有交集，前面已经选点了。因此直接跳过。
- $l_i > ed$: 说明当前区间与前面没有交集。因此选中当前区间，并设置 $ed = r_i$。



### 练习LC M452. 用最少量的箭引爆气球

https://leetcode.cn/problems/minimum-number-of-arrows-to-burst-balloons/

有一些球形气球贴在一堵用 XY 平面表示的墙面上。墙面上的气球记录在整数数组 `points` ，其中`points[i] = [xstart, xend]` 表示水平直径在 `xstart` 和 `xend`之间的气球。你不知道气球的确切 y 坐标。

一支弓箭可以沿着 x 轴从不同点 **完全垂直** 地射出。在坐标 `x` 处射出一支箭，若有一个气球的直径的开始和结束坐标为 xstart，xend， 且满足  `xstart ≤ x ≤ xend`，则该气球会被 **引爆** 。可以射出的弓箭的数量 **没有限制** 。 弓箭一旦被射出之后，可以无限地前进。

给你一个数组 `points` ，*返回引爆所有气球所必须射出的 **最小** 弓箭数* 。

 

**示例 1：**

```
输入：points = [[10,16],[2,8],[1,6],[7,12]]
输出：2
解释：气球可以用2支箭来爆破:
-在x = 6处射出箭，击破气球[2,8]和[1,6]。
-在x = 11处发射箭，击破气球[10,16]和[7,12]。
```

**示例 2：**

```
输入：points = [[1,2],[3,4],[5,6],[7,8]]
输出：4
解释：每个气球需要射出一支箭，总共需要4支箭。
```

**示例 3：**

```
输入：points = [[1,2],[2,3],[3,4],[4,5]]
输出：2
解释：气球可以用2支箭来爆破:
- 在x = 2处发射箭，击破气球[1,2]和[2,3]。
- 在x = 4处射出箭，击破气球[3,4]和[4,5]。
```

 



**提示:**

- `1 <= points.length <= 105`
- `points[i].length == 2`
- `-231 <= xstart < xend <= 231 - 1`



```python
class Solution:
    def findMinArrowShots(self, points: List[List[int]]) -> int:
        # 按照右端点从小到大排序
        points.sort(key=lambda x: x[1])

        res = 0
        ed = -sys.maxsize
        
        for v in points:
            if ed < v[0]:
                res += 1
                ed = v[1]

        return res
```



### M01328: Radar Installation

greedy, http://cs101.openjudge.cn/pctbook/M01328/

Assume the coasting is an infinite straight line. Land is in one side of coasting, sea in the other. Each small island is a point locating in the sea side. And any radar installation, locating on the coasting, can only cover d distance, so an island in the sea can be covered by a radius installation, if the distance between them is at most d.

We use Cartesian coordinate system, defining the coasting is the x-axis. The sea side is above x-axis, and the land side below. Given the position of each island in the sea, and given the distance of the coverage of the radar installation, your task is to write a program to find the minimal number of radar installations to cover all the islands. Note that the position of an island is represented by its x-y coordinates.
![image-20231021115237439](https://raw.githubusercontent.com/GMyhf/img/main/img/image-20231021115237439.png)
Figure A Sample Input of Radar Installations

**输入**

The input consists of several test cases. The first line of each case contains two integers n (1<=n<=1000) and d, where n is the number of islands in the sea and d is the distance of coverage of the radar installation. This is followed by n lines each containing two integers representing the coordinate of the position of each island. Then a blank line follows to separate the cases.

The input is terminated by a line containing pair of zeros

**输出**

For each test case output one line consisting of the test case number followed by the minimal number of radar installations needed. "-1" installation means no solution for that case.

样例输入

```
3 2
1 2
-3 1
2 1

1 2
0 2

0 0
```

样例输出

```
Case 1: 2
Case 2: 1
```

来源: Beijing 2002



映射到x轴，排序，左右端点互相看看。程序逻辑解释：

1. **计算岛屿的覆盖区间**：对于每个岛屿，先根据其x和y坐标计算出在x轴上的区间范围。这是通过$\sqrt{d^2 - y^2}$来确定的。
2. **排序**：将所有岛屿的区间按照右端点进行排序，目的是尽可能让新的雷达覆盖更多的岛屿。
3. **更新覆盖范围**：逐个岛屿进行遍历，尝试更新当前雷达能够覆盖的最远点。如果当前岛屿的左端点在已经覆盖的区间之外，则必须增加一个新的雷达，并将新的覆盖范围设为当前岛屿的区间。

```python
import math

def solve(n, d, islands):
    if d < 0:
        return -1

    ranges = []
    for x, y in islands:
        if y > d:
            return -1
        delta = math.sqrt(d * d - y * y)
        ranges.append((x - delta, x + delta))

    if not ranges:
        return -1

    ranges.sort(key=lambda x:x[1])

    number = 1
    r = ranges[0][1]
    for start, end in ranges[1:]:
        if r < start:
            r = end
            number += 1

    return number

case_number = 0
while True:
    n, d = map(int, input().split())
    if n == 0 and d == 0:
        break

    case_number += 1
    islands = []
    for _ in range(n):
        islands.append(tuple(map(int, input().split())))

    result = solve(n, d, islands)
    print(f"Case {case_number}: {result}")
    input()
```





## 4 区间覆盖问题

### 4.1 题意描述

**区间覆盖问题**大概题意就是：

给出一堆区间和一个目标区间，问最少选择多少区间可以**覆盖**掉题中给出的这段目标区间。

如下图所示： 

![img](https://pic3.zhimg.com/80/v2-66041d9941667482fc51adeb4a616f64_1440w.webp)

<center>区间覆盖问题示例，最终至少选择2个区间才能覆盖目标区间</center>

### 4.2. 解题步骤

【**步骤一**】：按照区间左端点从小到大排序。

**步骤二**】：**从前往后**依次枚举每个区间，在所有能覆盖当前目标区间起始位置start的区间之中，选择**右端点**最大的区间。

假设右端点最大的区间是第$i$个区间，右端点为 $r_i$。

最后将目标区间的start更新成$r_i$





### 练习LC M1024. 视频拼接

https://leetcode.cn/problems/video-stitching/

你将会获得一系列视频片段，这些片段来自于一项持续时长为 `time` 秒的体育赛事。这些片段可能有所重叠，也可能长度不一。

使用数组 `clips` 描述所有的视频片段，其中 `clips[i] = [starti, endi]` 表示：某个视频片段开始于 `starti` 并于 `endi` 结束。

甚至可以对这些片段自由地再剪辑：

- 例如，片段 `[0, 7]` 可以剪切成 `[0, 1] + [1, 3] + [3, 7]` 三部分。

我们需要将这些片段进行再剪辑，并将剪辑后的内容拼接成覆盖整个运动过程的片段（`[0, time]`）。返回所需片段的最小数目，如果无法完成该任务，则返回 `-1` 。

 

**示例 1：**

```
输入：clips = [[0,2],[4,6],[8,10],[1,9],[1,5],[5,9]], time = 10
输出：3
解释：
选中 [0,2], [8,10], [1,9] 这三个片段。
然后，按下面的方案重制比赛片段：
将 [1,9] 再剪辑为 [1,2] + [2,8] + [8,9] 。
现在手上的片段为 [0,2] + [2,8] + [8,10]，而这些覆盖了整场比赛 [0, 10]。
```

**示例 2：**

```
输入：clips = [[0,1],[1,2]], time = 5
输出：-1
解释：
无法只用 [0,1] 和 [1,2] 覆盖 [0,5] 的整个过程。
```

**示例 3：**

```
输入：clips = [[0,1],[6,8],[0,2],[5,6],[0,4],[0,3],[6,7],[1,3],[4,7],[1,4],[2,5],[2,6],[3,4],[4,5],[5,7],[6,9]], time = 9
输出：3
解释： 
选取片段 [0,4], [4,7] 和 [6,9] 。
```

 

**提示：**

- `1 <= clips.length <= 100`
- `0 <= starti <= endi <= 100`
- `1 <= time <= 100`





```python
from typing import List

class Solution:
    def videoStitching(self, clips: List[List[int]], time: int) -> int:
        # 对 clips 按起点升序排序
        clips.sort()

        st, ed = 0, time
        res = 0

        i = 0
        while i < len(clips) and st < ed:
            maxR = 0
            # 找到所有起点小于等于 st 的片段，并记录这些片段的最大终点 maxR
            while i < len(clips) and clips[i][0] <= st:
                maxR = max(maxR, clips[i][1])
                i += 1

            if maxR <= st:
                # 无法继续覆盖
                return -1

            # 更新 st 为 maxR，并增加结果计数
            st = maxR
            res += 1

            if maxR >= ed:
                # 已经覆盖到终点
                return res

        # 如果没有成功覆盖到终点
        return -1
```



### 练习T27104: 世界杯只因

greedy/dp, http://cs101.openjudge.cn/practice/27104/

卡塔尔世界杯正在火热进行中，P大富哥李哥听闻有一种叫"肤白·态美·宇宙无敌·世界杯·预测鸡"的鸡品种（以下简称为只因）有概率能准确预测世界杯赛果，一口气买来无数只只因，并把它们塞进了N个只因窝里，但只因窝实在太多了，李哥需要安装摄像头来观测里面的只因的预测行为。

具体来说，李哥的只因窝可以看作分布在一条直线上的N个点，编号为1到N。由于每个只因窝的结构不同，在编号为i的只因窝处安装摄像头，观测范围为a_i，其中a是长为N的整数列，表示若在此安装摄像头，可以观测到编号在 [ i - a_i , i + a_i ]（闭区间）内的所有只因窝。

李哥觉得摄像头成本高，决定抠门一下，请你来帮忙看看最少需要安装多少个摄像头，才能观测到全部N个只因窝。作为回报，他会请你喝一杯芋泥波波牛乳茶。

**输入**

第一行：一个正整数，代表有N个只因窝。
第二行给出数列a：N个非负整数，第i个数代表a_i，也就是在第i个只因窝装摄像头能观测到的区间的半径。

数据保证 N ≤ 500000，0 ≤ a_i ≤ N

**输出**

一个整数，即最少需要装的摄像头数量。

样例输入

```
10
2 0 1 1 0 3 1 0 2 0
```

样例输出

```
3
```

提示：彩蛋：只因们很喜欢那个穿着蓝白球衣长得像黄金矿工的10号

来源：计概A 2022期末



是典型的“**区间覆盖最小集合**”问题，本质上是贪心算法在一维线段上的最优覆盖。
下面先解析题意→说明贪心思想→再给出代码。

------

**题意解析**

有 N 个窝在一条线上，每个窝 i 对应一个整数 ( a_i )。
如果在窝 i 装摄像头，它能覆盖区间：
$
[i - a_i,, i + a_i]
$

目标：用尽量少的摄像头，使区间 `[1, N]` 被完全覆盖。

约束：

- $( N \le 5\times 10^5 )$
- $( 0 \le a_i \le N )$
- 必须线性或 O(N log N) 算法。

------

💡 **核心思想：区间覆盖贪心（Interval Covering Greedy）**

等价于：

> 给定一系列区间 `[L_i, R_i]`，要覆盖 `[1, N]`，求最少区间数量。

经典贪心策略：

1. 按 **左端点 L 升序** 排序。
2. 用一个变量 `rightmost` 表示当前已覆盖的最右端。
3. 在能“接上当前覆盖区间”的所有候选区间中，**选右端点 R 最大的**那一个。
4. 每当 `rightmost` 无法继续延伸时，新增一个区间（摄像头）。

时间复杂度 O(N log N)，如果不排序、直接预处理每个位置的最远可达右端，也能做到 O(N)。

内存: 96740kB，时间: 1040ms

```python
n = int(input())
a = list(map(int, input().split()))

# 1. 计算每个位置的覆盖区间
intervals = []
for i, x in enumerate(a, start=1):
    left = max(1, i - x)
    right = min(n, i + x)
    intervals.append((left, right))

# 2. 按左端点排序
intervals.sort()

# 3. 贪心选择最少区间覆盖 [1, N]
ans = 0
i = 0
covered = 0

while covered < n:
    best = covered
    # 在所有能接上的区间中，选右端点最大的
    while i < n and intervals[i][0] <= covered + 1:
        best = max(best, intervals[i][1])
        i += 1
    if best == covered:  # 无法延伸
        break
    covered = best
    ans += 1

print(ans)
```

思路说明

- `covered` 是当前覆盖的最右边界。
- 每次扩展时：
  - 找所有 `L_i ≤ covered + 1` 的区间。
  - 从中选 `R_i` 最大的那一个。
  - 更新 `covered = R_i`。
  - 计数器 `ans += 1`。
- 重复直到 `covered ≥ N`。



**若需 纯 O(N) 版本（无需排序）**

利用「右端最远覆盖数组」：

内存: 59472kB，时间: 627ms

```python
n = int(input())
a = list(map(int, input().split()))

far = [0] * (n + 2)
for i, x in enumerate(a, start=1):
    L = max(1, i - x)
    R = min(n, i + x)
    far[L] = max(far[L], R)

ans = 0
covered = 0
best = 0

for i in range(1, n + 1):
    best = max(best, far[i])
    if i > covered:
        ans += 1
        covered = best

print(ans)
```

这个写法等价于“跳台阶式区间扩展”，非常精炼、线性复杂度，是此类题的最优模板。

------

✅ 总结对比

| 特征     | 优化版（O(N log N)） | 优化版（O(N)）       |
| -------- | -------------------- | -------------------- |
| 核心思路 | 区间覆盖标准贪心     | 线性扫描右端最远覆盖 |
| 复杂度   | O(N log N)           | O(N)                 |
| 代码长度 | 20行                 | 15行                 |
| 可读性   | ★★★★                 | ★★★★★                |
| 是否易记 | 是                   | 是（推荐模板）       |

------

**建议**

今后遇到类似题型（如“最少灯照亮道路”“覆盖线段”等），
直接记下面这两种模板：

- **排序版**：适合任意输入区间。
- **线性版**：适合“按位置定义区间”的题。





## 5 区间分组问题

### 5.1 题意描述

**区间分组**问题大概题意就是：给出一堆区间，问最少可以将这些区间分成多少组使得每个组内的区间互不相交。

如下图所示： 

![img](https://pic2.zhimg.com/80/v2-6c6a045d481ddc44c66b046ef3e7d4cd_1440w.webp)

<center>区间分组问题示例，最少分成3个组</center>

### 5.2. 解题步骤

【**步骤一**】：按照区间左端点从小到大排序。

【**步骤二**】：从**前往后**依次枚举每个区间，判断当前区间能否被放到某个现有组里面。

（即判断是否存在某个组的右端点在当前区间之中。如果可以，则不能放到这一组）

假设现在已经分了 m 组了，第 k 组最右边的一个点是 $r_k$，当前区间的范围是 $[L_i,R_i]$ 。则：

如果$L_i \le r_k$ 则表示第 i 个区间无法放到第 k 组里面。反之，如果 $L_i > r_k$， 则表示可以放到第 k 组。

- 如果所有 m 个组里面没有组可以接收当前区间，则当前区间新开一个组，并把自己放进去。
- 如果存在可以接收当前区间的组 k，则将当前区间放进去，并更新当前组的 $r_k = R_i$。

**注意：**

为了能快速的找到能够接收当前区间的组，我们可以使用**优先队列 （小顶堆）**。

优先队列里面记录每个组的右端点值，每次可以在 O(1) 的时间拿到右端点中的的最小值。



### 练习NC147 主持人调度

https://www.nowcoder.com/questionTerminal/4edf6e6d01554870a12f218c94e8a299

有 n 个活动即将举办，每个活动都有开始时间与活动的结束时间，第 i 个活动的开始时间是 starti ,第 i 个活动的结束时间是 endi ,举办某个活动就需要为该活动准备一个活动主持人。

一位活动主持人在同一时间只能参与一个活动。并且活动主持人需要全程参与活动，换句话说，一个主持人参与了第 i 个活动，那么该主持人在 (starti,endi) 这个时间段不能参与其他任何活动。求为了成功举办这 n 个活动，最少需要多少名主持人。

数据范围: $1≤n≤10^5 ， −2^{32}≤start_i≤end_i≤2^{31}$

复杂度要求：时间复杂度 O(nlog⁡n) ，空间复杂度 O(n)

示例1

**输入**

```
2,[[1,2],[2,3]]
```

**输出**

```
1
```

说明

```
只需要一个主持人就能成功举办这两个活动      
```

示例2

输入

```
2,[[1,3],[2,4]]
```

输出

```
2
```

说明

```
需要两个主持人才能成功举办这两个活动      
```

备注:

```
1≤n≤10^5
starti,endi在int范围内
```





解法1: 将每个活动的开始时间和结束时间转换为事件

```python
from typing import List

class Solution:
    def minmumNumberOfHost(self, n: int, startEnd: List[List[int]]) -> int:
        # 将每个活动的开始时间和结束时间转换为事件
        events = []
        for i in range(n):
            start, end = startEnd[i]
            events.append((start, 1))  # 活动开始，+1主持人
            events.append((end, -1))  # 活动结束，-1主持人

        # 对事件按照时间排序，如果时间相同，先处理结束事件
        events.sort(key=lambda x: (x[0], x[1]))

        min_hosts = 0
        current_hosts = 0

        # 遍历所有事件，计算需要的主持人数
        for time, event in events:
            current_hosts += event
            min_hosts = max(min_hosts, current_hosts)

        return min_hosts

# 示例用法

#sol = Solution()
#print(sol.minimum_number_of_host(3, [[1, 5], [2, 7], [4, 5]]))  # 输出应为 2
#print(sol.minimum_number_of_host(34,[[547,612],[417,551],[132,132],[168,446],[95,747],[187,908],[115,712],[15,329],[612,900],[3,509],[181,200],[562,787],[136,268],[36,784],[533,573],[165,946],[343,442],[127,725],[557,991],[604,613],[633,721],[287,847],[414,480],[428,698],[437,616],[475,932],[652,886],[19,992],[132,543],[390,869],[754,903],[284,925],[511,951],[272,739]]))
```



解法2:

```python
from typing import List
import heapq

class Solution:
    def minmumNumberOfHost(self, n: int, startEnd: List[List[int]]) -> int:
        # 按左端点从小到大排序
        startEnd.sort(key=lambda x: x[0])

        # 创建小顶堆
        q = []

        for i in range(n):
            if not q or q[0] > startEnd[i][0]:
                heapq.heappush(q, startEnd[i][1])
            else:
                heapq.heappop(q)
                heapq.heappush(q, startEnd[i][1])

        return len(q)
```





解法3:

将活动开始时间写入一个列表starts，进行排序。 

将活动结束时间写入一个列表ends，进行排序。 

每次活动开始时，需要增加一个主持人上场，每次活动结束时候可以释放一个主持人。 

所以按照时间先后顺序对starts进行遍历，每次有活动开始count++，每次有活动结束count-- 

在count最大的时候，即是需要主持人最多的时候

```python
class Solution:
    def minmumNumberOfHost(self , n , startEnd ):
        starts=[]
        ends=[]
        for start,end in startEnd:
            starts.append(start);
            ends.append(end);
            
        starts.sort();
        ends.sort()
        
        i,j,count,res=0,0,0,0
        for time in starts:
            while(i<n and starts[i]<=time):
                i+=1
                count+=1
            while(j<n and ends[j]<=time):
                j+=1
                count-=1
            if res<count:
                res=count
        return res
```



## 6 覆盖连续区间



### M29896:购物

greedy, http://cs101.openjudge.cn/practice/29896/



你就要去购物了，现在你手上有 N 种不同面值的硬币，每种硬币有无限多个。为了方便购物，你希望带尽量少的硬币，但要能组合出 1 到 X 之间的任意值。

**输入**

第一行两个数 X, N，以下 N 个数，表示每种硬币的面值。

**输出**

最少需要携带的硬币个数，如果无解输出-1。

样例输入

```
20 4
1 2 5 10
```

样例输出

```
5
```

提示

N <= 10, X <= 10000 (tag:greedy)

来源

https://www.luogu.com.cn/problem/P1658(TA-hhy)





**目标是：**在给定若干种硬币面值（每种无限供应）的前提下，选出最少数量的硬币，使得它们的组合能够表示出从 **1 到 X** 的所有整数值。

如果无法做到（比如没有面值为 1 的硬币，那连 1 都凑不出来），就输出 `-1`。



这是一个典型的“**覆盖连续区间**”问题。可以维护一个当前能表示的最大连续值 `max_reach`（初始为 0），然后不断选择硬币来扩展这个范围。思路：

1. **必须包含面值 1**，否则无法组成 1 → 无解，输出 -1。

2. 将硬币面值从小到大排序。

3. 维护当前能组成的最大连续值 `max_val`（初始为 0）。

4. 同时维护一个“候选池”：所有 ≤ `max_val + 1` 的硬币中，选最大的那个（因为加它能让 `max_val` 增加最多）。

   - 但实际上，由于硬币可重复使用，更优策略是：

     > 每次在所有满足 `coin <= max_val + 1` 的硬币中，选择**面值最大的**，然后带一枚它，更新 `max_val += coin`，计数器 +1。

5. 重复直到 `max_val >= X`。

但注意：因为硬币可以多次使用，其实我们可以**多次使用同一个硬币**来快速扩展。



```python
def solve():
    import sys
    input = sys.stdin.read
    data = input().split()
    
    X = int(data[0])
    N = int(data[1])
    coins = list(map(int, data[2:2+N]))
    
    # 去除大于 X 的硬币（无用）
    coins = [c for c in coins if c <= X]
    if not coins:
        if X == 0:
            return 0
        else:
            return -1
    
    # 排序
    coins.sort()
    
    # 必须要有 1，否则无法覆盖 1
    if coins[0] > 1:
        return -1
    
    max_reach = 0  # 当前能覆盖 [1, max_reach]
    count = 0      # 使用的硬币数量
    
    while max_reach < X:
        # 选择满足 coin <= max_reach + 1 的最大面值硬币
        candidate = -1
        for coin in coins:
            if coin <= max_reach + 1:
                candidate = coin
            else:
                break  # 因为已排序，后面的更大
        
        if candidate == -1:
            return -1  # 无法扩展
        
        max_reach += candidate
        count += 1
        
        if max_reach >= X:
            break
    
    return count

# 主程序
print(solve())
```



```python
import bisect

def solve():
    X, N = map(int, input().split())
    coins = list(map(int, input().split()))
    coins.sort()
    
    # 如果最小面值 > 1，无法凑出 1
    if coins[0] > 1:
        print(-1)
        return

    reach = 0
    ans = 0

    # 可以重复使用同一个面值多次，所以不移除
    while reach < X:
        target = reach + 1
        # 找 coins 中最大且 <= target
        idx = bisect.bisect_right(coins, target) - 1
        if idx < 0:
            print(-1)
            return
        c = coins[idx]
        reach += c
        ans += 1

    print(ans)

if __name__ == "__main__":
    solve()
```

算法复杂度

- 先对面值排序：`O(N log N)`
- 每一步用二分查找找到最大 `≤ reach+1`：`O(log N)`，循环次数等于答案（最多约 `O(X/min_coin)`），总体可接受（X ≤ 10000, N ≤ 10）。




