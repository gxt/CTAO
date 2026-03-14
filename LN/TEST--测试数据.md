## 程序生成测试数据

### 练习T26971:分发糖果

greedy, http://cs101.openjudge.cn/pctbook/T26971/

`n` 个孩子站成一排。给你一个整数数组 `ratings` 表示每个孩子的评分。

你需要按照以下要求，给这些孩子分发糖果：

- 每个孩子至少分配到 `1` 个糖果。
- 相邻两个孩子评分更高的孩子会获得更多的糖果。

请你给每个孩子分发糖果，计算并返回需要准备的 **最少糖果数目** 。

**输入**

第一行包含一个整数n。1 <= n <= 2 * 10^4
第二行包含n个整数，相邻整数间以空格隔开。0 <= ratings[i] <= 2 * 10^4

**输出**

一个整数

样例输入

```
Sample1 input:
3
1 0 2
Sample1 output:
5
```

样例输出

```
Sample2 input:
3
1 2 2
Sample2 output:
4
```

提示

tags: greedy

来源

LeetCode 135.分发糖果：https://leetcode.cn/problems/candy/





```python
import random
import time

random.seed(0)

for epoch in range(20):
    n = random.randint(10 + epoch * 2, 900 + 200 * (epoch // 2) ** 2)
    nums = [random.randint(0, 800 + 200 * (epoch // 2) ** 2 ) for _ in range(n)]
    inlines = [f'{n}\n'] + [' '.join([str(num) for num in nums]) + '\n']
    
    with open(f'data/{epoch}.in', 'w') as f:
        f.writelines(inlines)

    def candy(ratings):
        n = len(ratings)
        left = [0] * n
        for i in range(n):
            if i > 0 and ratings[i] > ratings[i - 1]:
                left[i] = left[i - 1] + 1
            else:
                left[i] = 1
    
        right = ret = 0
        for i in range(n - 1, -1, -1):
            if i < n - 1 and ratings[i] > ratings[i + 1]:
                right += 1
            else:
                right = 1
            ret += max(left[i], right)
    
        return ret

    #input()
    #*nums, = map(int, input().split())
    start = time.time()
    ans = candy(nums)
    end = time.time() - start

    print(f"[{epoch}] {end:.3f}sec")
    print(ans)

    with open(f'data/{epoch}.out', 'w') as f:
        f.writelines([str(ans) + '\n'])
```



### 练习M26976:摆动序列

greedy, http://cs101.openjudge.cn/pctbook/M26976/

如果连续数字之间的差严格地在正数和负数之间交替，则数字序列称为 **摆动序列 。**第一个差（如果存在的话）可能是正数或负数。仅有一个元素或者含两个不等元素的序列也视作摆动序列。

- 例如， 

[1, 7, 4, 9, 2, 5] 是一个 **摆动序列** ，因为差值 (6, -3, 5, -7, 3) 是正负交替出现的。

- 相反，

[1, 4, 7, 2, 5]

[1, 7, 4, 5, 5] 

**子序列** 可以通过从原始序列中删除一些（也可以不删除）元素来获得，剩下的元素保持其原始顺序。

给你一个整数数组 nums ，返回 nums 中作为 **摆动序列** 的 **最长子序列的长度** 。

**输入**

第一行包含一个整数n。1 <= n <= 1000

第二行包含n个整数，相邻整数间以空格隔开。0 <= nums[i] <= 1000

**输出**

一个整数

样例输入

```
sample1 input:
6
1 7 4 9 2 5
sample1 output:
6

sample2 input:
10
1 17 5 10 13 15 10 5 16 8
sample2 output:
7
```

样例输出

```
sample3 input:
9
1 2 3 4 5 6 7 8 9
sample3 output:
2
```

提示

tags: greedy

来源

LeetCode 376. 摆动序列: https://leetcode.cn/problems/wiggle-subsequence/





```python
import random
import time

random.seed(0)

for epoch in range(20):
    n = random.randint(1, min(1000, 10 + epoch*50))
    nums = [random.randint(0, 1000 ) for _ in range(n)]
    inlines = [f'{n}\n'] + [' '.join([str(num) for num in nums]) + '\n']

    with open(f'data/{epoch}.in', 'w') as f:
        f.writelines(inlines)

    def wiggleMaxLength(nums):
        n = len(nums)
        if n < 2:
            return n
        
        prevdiff = nums[1] - nums[0]
        ret = (2 if prevdiff != 0 else 1)
        for i in range(2, n):
            diff = nums[i] - nums[i - 1]
            if (diff > 0 and prevdiff <= 0) or (diff < 0 and prevdiff >= 0):
                ret += 1
                prevdiff = diff
        
        return ret
    

    #input()
    #*nums, = map(int, input().split())
    start = time.time()
    ans = wiggleMaxLength(nums)
    end = time.time() - start
    
    print(f"[{epoch}] {end:.3f}sec")
    print(ans)
    
    with open(f'data/{epoch}.out', 'w') as f:
        f.writelines([str(ans) + '\n'])
```



### 多解的题目

 tags: constructive algorithms （If there are multiple solutions, you may output any of them. 多解的题目需要spj来处理，special judge）

![image-20231015123114430](https://raw.githubusercontent.com/GMyhf/img/main/img/image-20231015123114430.png)



### 练习CF1868A. Fill in the Matrix

constructive algorithms, implementation, 1300, https://codeforces.com/problemset/problem/1868/A

There is an empty matrix 𝑀 of size 𝑛×𝑚.

Zhongkao examination is over, and Daniel would like to do some puzzle games. He is going to fill in the matrix  using permutations of length 𝑚. That is, each row of 𝑀 must be a permutation of length 𝑚†.

Define the *value* of the 𝑖-th column in 𝑀 as $𝑣𝑖=MEX(𝑀_{1,𝑖},𝑀_{2,𝑖},…,𝑀_{𝑛,𝑖})$‡. Since Daniel likes diversity, the *beauty* of 𝑀 is $𝑠=MEX(𝑣_1,𝑣_2,⋯,𝑣_𝑚)$.

You have to help Daniel fill in the matrix 𝑀 and **maximize** its beauty.

†† A permutation of length 𝑚 is an array consisting of 𝑚 distinct integers from 00 to 𝑚−1 in arbitrary order. For example, \[1,2,0,4,3] is a permutation, but \[0,1,1] is not a permutation (1 appears twice in the array), and \[0,1,3] is also not a permutation (𝑚−1=2 but there is 3 in the array).

‡‡ The MEXMEX of an array is the smallest non-negative integer that does not belong to the array. For example, MEX(2,2,1)=0 because 0 does not belong to the array, and MEX(0,3,1,2)=4 because 0, 1, 2 and 3 appear in the array, but 4 does not.

**Input**

The first line of input contains a single integer 𝑡 (1≤𝑡≤1000) — the number of test cases. The description of test cases follows.

The only line of each test case contains two integers 𝑛 and 𝑚 (1≤𝑛,𝑚≤2⋅10^5^) — the size of the matrix.

It is guaranteed that the sum of 𝑛⋅𝑚 over all test cases does not exceed 2⋅10^5^.

**Output**

For each test case, in the first line output a single integer — the maximum beauty of 𝑀.

Then output the matrix 𝑀 of size 𝑛×𝑚 — the matrix you find.

If there are multiple solutions, you may output any of them.

Example

input

```
4
4 3
1 16
6 6
2 1
```

output

```
3
1 0 2
0 2 1
1 0 2
0 2 1
2
14 7 15 4 10 0 8 6 1 2 3 5 9 11 12 13 
6
3 0 1 4 2 5 
5 2 1 0 4 3 
1 3 2 4 5 0 
4 1 3 2 5 0 
4 2 5 3 0 1 
2 4 0 5 1 3
0
0
0
```

Note

In the first test case:

- 𝑣1=MEX(1,0,1,0)=2;
- 𝑣2=MEX(0,2,0,2)=1;
- 𝑣3=MEX(2,1,2,1)=0.

Therefore, 𝑠=MEX(2,1,0)=3.

It can be shown that 33 is the maximum possible beauty of 𝑀.

In the second test case, any permutation will make 𝑠=2.

In the third test case:

- 𝑣1=MEX(3,5,1,4,4,2)=0;
- 𝑣2=MEX(0,2,3,1,2,4)=5;
- 𝑣3=MEX(1,1,2,3,5,0)=4;
- 𝑣4=MEX(4,0,4,2,3,5)=1;
- 𝑣5=MEX(2,4,5,5,0,1)=3;
- 𝑣6=MEX(5,3,0,0,1,3)=2.

Therefore, 𝑠=MEX(0,5,4,1,3,2)=6.



## 3.5 两种喂数据的方法

> 通过喂数据来测试py程序的两种方法。每个题目的测试数据是zip文件，解开后，看到类似0.in,0.out的文件对。testing_code.py, offlinejudge.zsh, 也可以这里下载 https://github.com/GMyhf/2025fall-cs101/tree/main/code



在 **mac** 或 **linux** 系统上，如果测试数据所在目录下包含形如 `xx.in`、`xx.out` 的文件，而待测试的代码文件是 `e1.py`，假设 `testing_code.py` 位于上两级目录中，脚本解释器为 `python3`，则可以在终端执行：

```bash
python3 ../../testing_code.py e1.py
```

若程序运行正确（如 `ac1.py`），则不会有输出；如果有错误，会直接打印提示信息。

<img src="https://raw.githubusercontent.com/GMyhf/img/main/img/202509190043562.png" alt="5932455ec86aaf5923e3d5080b76085d" style="zoom:50%;" />



另一种方式是使用评测脚本 **offlinejudge.zsh**。
 在 macOS 下执行：

```bash
zsh ../../offlinejudge.zsh e1.py ./
```

在 Linux 下执行：

```bash
bash ../../offlinejudge.zsh e1.py ./
```

运行后，左侧显示 `e1.py` 的程序输出，右侧显示正确答案，方便对照。

<img src="https://raw.githubusercontent.com/GMyhf/img/main/img/202509190044067.jpg" alt="d96c73937410a3f906c294cb92801fb4" style="zoom:50%;" />



综上，以上是通过“喂数据”来测试 Python 程序的两种方法。
 每个题目的测试数据通常以 zip 文件提供，解压后可得到类似 `0.in`、`0.out` 的数据文件对。
 相关脚本 [`testing_code.py`](https://github.com/GMyhf/2025fall-cs101/tree/main/code)、[`offlinejudge.zsh`](https://github.com/GMyhf/2025fall-cs101/tree/main/code) 也可从仓库中下载。



### 示例testing_code.py源码

https://github.com/GMyhf/2025fall-cs101/blob/main/code/testing_code.py

```python
import subprocess
import difflib
import os
import sys

def test_code(script_path, infile, outfile):
    command = [sys.executable, script_path]  # 使用Python解释器运行脚本
    with open(infile, 'r') as fin, open(outfile, 'r') as fout:
        expected_output = fout.read().strip()
        # 启动一个新的子进程来运行指定的命令
        process = subprocess.Popen(command, stdin=fin, stdout=subprocess.PIPE)
        actual_output, _ = process.communicate()
        if actual_output.decode().strip() == expected_output:
            return True
        else:
            print(f"Output differs for {infile}:")
            diff = difflib.unified_diff(
                expected_output.splitlines(),
                actual_output.decode().splitlines(),
                fromfile='Expected', tofile='Actual', lineterm=''
            )
            print('\n'.join(diff))
            return False


if __name__ == "__main__":
    # 检查命令行参数的数量
    if len(sys.argv) != 2:
        print("Usage: python testing_code.py <filename>")
        sys.exit(1)

    # 获取文件名
    script_path = sys.argv[1]

    #script_path = "class.py"  # 你的Python脚本路径
    #test_cases = ["d.in"]  # 输入文件列表
    #expected_outputs = ["d.out"]  # 预期输出文件列表
    # 获取当前目录下的所有文件
    files = os.listdir('.')

    # 建立输入/输出字典
    input_files = {}
    output_files = {}

    for file in files:
        if file.endswith(".in"):
            key = file[:-3]  # 去掉 ".in"
            input_files[key] = file
        elif file.endswith(".out"):
            key = file[:-4]  # 去掉 ".out"
            output_files[key] = file

    # 遍历公共 key，按字典序排序
    for key in sorted(set(input_files.keys()) & set(output_files.keys())):
        infile = input_files[key]
        outfile = output_files[key]
        if not test_code(script_path, infile, outfile):
            break

```



### 示例offlinejudge.sh

```shell
cd $2
for i in *.in; do
	diff -y <(python3 "$1" < "$i")  "${i%.*}.out"
done
```

