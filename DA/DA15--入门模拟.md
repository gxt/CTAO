# 入门模拟

- [算法笔记 - 胡凡](https://sunnywhy.com/sfbj)
  - 第 3 章 入门篇（1）——入门模拟

## 1 简单模拟 8题

!!! note 

    模拟题是一类“题目怎么说，你就怎么做”的题目，如果实现起来不太麻烦，就可以称之为“简单模拟”。
    
    这类题目不涉及算法，完全只是根据题目描述来进行代码的编写，所以主要考查的是代码能力。

### sy54: 3N+1猜想 简单

https://sunnywhy.com/sfbj/3/1/54


!!! question 3N + 1猜想：

    给定一个正整数 N，如果它是偶数，那么让它除以 2；如果它是奇数，那么让它先乘 3 加 1 再除以 2。这样一直下去，最终总能在某一步得到N = 1。

    给定一个正整数 N，问需要多少步可以让 N 等于 1。

**输入描述**

一个正整数 N（$1 \le N \le 100$）。

**输出描述**

输出让 N 等于 1 的步数。

样例1

输入

```
3
```

输出

```
5
```

解释

3 => 5 => 8 => 4 => 2 => 1



```python
n = int(input())
cnt = 0
while n != 1:
    if n % 2 == 0:
        n //= 2
        cnt += 1
        continue
    else:
        n *= 3
        n += 1
        n //= 2
    cnt += 1
print(cnt)
```



### sy55: 判断三角形 简单

https://sunnywhy.com/sfbj/3/1/55

!!! question 判断三角形：
    如果三条边A、B、C的长度同时满足A + B > C、A + C > B、B + C > A，那么这三条边可以组成一个三角形。

    给定三条边的长度，问这三条边是否能组成一个三角形。

**输入描述**

三个正整数A、B、C（$1 \le A,B,C \le 100$）。

**输出描述**

如果可以组成三角形，那么输出YES，否则输出NO。

样例1

输入

```
3 4 5
```

输出

```
YES
```

样例2

输入

```
1 1 2
```

输出

```
NO
```



```python
a,b,c = map(int, input().split())
if a+b>c and a+c>b and b+c>a:
    print("YES")
else:
    print("NO")
```



### sy56: 单调递增序列 简单

https://sunnywhy.com/sfbj/3/1/56

!!! question 单调递增序列：

    给定n个整数的序列 $A_1、A_2、...、A_n$，如果对任意的 $1 \le i \le n-1$，都有 $A_i \le A_{i+1}$ 成立，那么称这个序列为单调递增序列，输出 YES，否则输出 NO。

**输入描述**

第一行为一个正整数（$1 \le n \le 10$）；

第二行为用空格隔开的个整数（$1 \le A_i \le 100$）。

**输出描述**

如果是单调递增序列，那么输出YES，否则输出NO。

样例1

输入

```
5
1 3 5 5 9
```

输出

```
YES
```

样例2

输入

```
5
1 3 5 4 9
```

输出

```
NO
```



```python
def is_sorted(a):
    for i in range(1, len(a)):
        if a[i] < a[i-1]:
            return False
    return True

input()
a = list(map(int, input().split()))
if is_sorted(a):
    print('YES')
else:
    print('NO')
```



### sy57: 数列奇数和 简单

https://sunnywhy.com/sfbj/3/1/57

!!! question 数列奇数和：
    给定n个整数的序列 $A_1、A_2、...、A_n$，求其中所有奇数的和。

**输入描述**

第一行为一个正整数 n（$1 \le n \le 10$）；

第二行为用空格隔开的个整数（$1 \le A_i \le 100$）。

**输出描述**

数列中所有奇数的和。

样例1

输入

```
5
5 8 7 6 2
```

输出

```
12
```



```python
def sum_odd(a):
    s = 0
    for i in range(len(a)):
        if a[i] % 2 == 1:
            s += a[i]
    return s
        

input()
a = list(map(int, input().split()))
print(sum_odd(a))
```



### sy58: 三位数 简单

https://sunnywhy.com/sfbj/3/1/58

!!! question 三位数：
    给定一个三位数n，输出它的百位、十位、个位。

**输入描述**

一个正整数 n（$100 \le n \le 999$）。

**输出描述**

在一行中先后输出的百位、十位、个位，中间用空格隔开，行末不允许有多余空格。

样例1

输入

```
153
```

输出

```
1 5 3
```



```python
n = input()
print(*list(n))
```



### sy59: 水仙花数 简单

https://sunnywhy.com/sfbj/3/1/59

!!! question 水仙花数：
    如果一个三位数 n 的各位数字的立方和等于 n，那么称 n 为水仙花数。例如$153=1^3 + 5^3 + 3^3$，因此153是水仙花数。

    给定一个正整数，判断这个数是否是水仙花数。

**输入描述**

一个正整数 n（$100 \le n \le 999$）。

**输出描述**

如果是水仙花数，那么输出`YES`，否则输出`NO`。

样例1

输入

```
153
```

输出

```
YES
```

样例2

输入

```
666
```

输出

```
NO
```



```python
n = input()
numbers = map(int, list(n))
cubed = map(lambda x: x**3, numbers)

total = sum(cubed)
if int(n) == total:
    print('YES')
else:
    print('NO')
```



### sy60: 水仙花数II 简单

https://sunnywhy.com/sfbj/3/1/60

!!! question 水仙花数II：

    如果一个三位数 n 的各位数字的立方和等于 n，那么称 n 为水仙花数。例如$153=1^3 + 5^3 + 3^3$，因此153是水仙花数。

    给定两个正整数a、b，输出在闭区间[a,b]内的所有水仙花数。

**输入描述**

两个正整数a、b（$100 \le a \le b \le 999$）。

**输出描述**

在一行里输出闭区间内的所有水仙花数，多个水仙花数按从小到大的顺序输出，中间用空格隔开，行末不允许有多余的空格。如果区间内没有水仙花数，那么输出NO。

样例1

输入

```
360 380
```

输出

```
370 371
```

样例2

输入

```
350 360
```

输出

```
NO
```



```python
def sum_cubes(n):
    numbers = map(int, list(n))
    cubed = map(lambda x: x**3, numbers)
    total = sum(cubed)
    return total

a,b = map(int, input().split())

ans = []
for i in range(a,b+1):
    if i == sum_cubes(str(i)):
        ans.append(i)

if len(ans) == 0:
    print("NO")
else:
    print(" ".join(map(str, ans)))

```



### sy61: 2的幂 简单

https://sunnywhy.com/sfbj/3/1/61

!!! question 2的幂：
    给定一个正整数n，求 $2^n  \mod  1007$。

    提示：$(a*b) \mod m=((a \mod m)*(b \mod m)) \mod m$

**输入描述**

一个正整数 n（$1 \le n \le 128$）。

**输出描述**

输出$2^n \mod 1007$的结果。

样例1

输入

```
3
```

输出

```
8
```



```python
n = int(input())
print(2**n % 1007)
```



## 2 查找元素 3题

!!! note

    有时考生会碰到这样一种情况：给定一些元素，然后查找某个满足某条件的元素。这就是查找操作需要做的事情。
    
    查找是学习写代码的一项基本功，是肯定需要掌握的。
    
    一般来说,如果需要在一个比较小范围的数据集里进行查找，那么直接遍历每一个数据即可；如果需要查找的范围比较大，那么可以用二分查找等算法来进行更快速的查找。

### sy62: 查找元素 简单

https://sunnywhy.com/sfbj/3/2/62

!!! question 查找元素：
    给定n个整数的序列$A_1、A_2、...、A_n$，然后给出一个整数x，求x在序列中的下标。

**输入描述**

第一行为一个正整数n（$1 \le n \le 20$）；

第二行为用空格隔开的n个整数（$1\le A_i \le 100$），每个整数确保唯一；

第三行为一个正整数x（$1 \le x \le 100$）。

**输出描述**

输出在序列中的下标。如果序列中不存在，那么输出NO。

样例1

输入

```
5
6 8 3 7 5
8
```

输出

```
2
```

样例2

输入

```
5
6 8 3 7 5
4
```

输出

```
NO
```



```python
n = int(input())
a = list(map(int, input().split()))
x = int(input())
for pos, i in enumerate(a):
    if i == x:
        print(pos + 1)
        break
else:
    print('NO')
```



### sy63: 统计元素个数 简单

https://sunnywhy.com/sfbj/3/2/63

!!! question 统计元素个数：
    给定n个整数的序列$A_1、A_2、...、A_n$，然后给出一个整数x，求x在序列中出现的次数。

**输入描述**

第一行为一个正整数n（$1 \le n \le 100$）；

第二行为用空格隔开的n个整数（$1\le A_i \le 100$）；

第三行为一个正整数x（$1 \le x \le 100$）。

**输出描述**

输出x在序列中出现的次数。

样例1

输入

```
5
6 8 3 6 5
6
```

输出

```
2
```

样例2

输入

```
5
6 8 3 7 5
4
```

输出

```
0
```



```python
n = int(input())
a = list(map(int, input().split()))
x = int(input())
freq = [0]*101
for i in a:
    freq[i] += 1
print(freq[x])
```



### sy64: 寻找元素对 简单

https://sunnywhy.com/sfbj/3/2/64

!!! question 寻找元素对：
    给定n个整数的序列$A_1、A_2、...、A_n$和一个正整数K，在序列中寻找两个不同的数$A_i、A_j$，使得$A_i + Aj = K$。问存在多少对满足条件的不同的(i,j)。

**输入描述**

第一行为一个正整数n（$1 \le n \le 1000$）；

第二行为用空格隔开的n个整数（$1 \le A_i \le 1000$），每个整数确保唯一；

第三行为一个正整数K（$1 \le K \le 2000$）。

**输出描述**

输出满足条件的不同的的对数。和视作同一组。

样例1

输入

```
5
6 8 3 7 5
13
```

输出

```
2
```



```python
n = int(input())
a = list(map(int, input().split()))
a_set = set(a)
k = int(input())
cnt = 0
ans = set()
for i in a:
    j = k - i
    if i == j:
        continue
    if j in a_set and (i,j) not in ans and (j,i) not in ans:
        ans.add((i,j))
        ans.add((j,i))
        cnt += 1
print(cnt)

```



## 3 图形输出 3题

!!! note

    在有些题目中，题目会给定一些规则，需要考生根据规则来进行画图。所谓图形，其实是由若干字符组成的，因此只需要弄清楚规则就能编写代码。
    
    这种题目的做法一般有两种：

    1. 通过规律，直接进行输出。
    2. 定义一个二维字符数组，通过规律填充之，然后输出整个二维数组。

### sy65: 等腰直角三角形 简单

https://sunnywhy.com/sfbj/3/3/65

!!! question 等腰直角三角形：
    绘制一个使用符号"\*"进行填充的实心等腰直角三角形，其中直角顶点在左下角，两条直角边的长度均为n（直角边的长度指*的个数）。

**输入描述**

一个正整数n（$2 \le n \le 50$）。

**输出描述**

输出一个实心的等腰直角三角形。注意行末不要有多余的空格。

样例1

输入

```
3
```

输出

```
*
**
***
```

样例2

输入

```
5
```

输出

```
*
**
***
****
*****
```



```python
n = int(input())
for i in range(n):
    print('*'*(i+1))
```



### sy66: 等腰直角三角形II 简单

https://sunnywhy.com/sfbj/3/3/66

!!! question 等腰直角三角形II：
    绘制一个空心的等腰直角三角形（使用符号"\*"来表示三角形的边，三角形内部用空格填充），其中直角顶点在左下角，两条直角边的长度均为（直角边的长度指*的个数）。

**输入描述**

一个正整数n（$2 \le n \le 100$）。

**输出描述**

输出一个空心的等腰直角三角形。注意行末不要有多余的空格。

样例1

输入

```
3
```

输出

```
*
**
***
```

样例2

输入

```
5
```

输出

```
*
**
* *
*  *
*****
```



```python
n = int(input())
print('*')
for i in range(1, n-1):
    print('*' + ' ' * (i - 1) + '*')

print('*' * n)
```



### sy67: 画X 简单

https://sunnywhy.com/sfbj/3/3/67

!!! question 画X：
    绘制一个X（用\*号表示线），其中长、宽、对角线的长度（即可容纳的*号个数）均为同一个奇数n。

**输入描述**

一个正奇数n（$3 \le n \le 99$）。

**输出描述**

输出一个X。注意行末不要有多余的空格。

样例1

输入

```
3
```

输出

```
* *
 *
* *
```

样例2

输入

```
5
```

输出

```
*   *
 * *
  *
 * *
*   *
```



注意行末不要有多余的空格。

```python
n = int(input())
mx = [[' ']*n for _ in range(n)]
for r in range(n):
    mx[r][r] = '*'
    mx[r][~r] = '*'

for row in mx:
    print(''.join(row).rstrip())
```





## 4 日期处理 6题

!!! note

    日期处理的问题总是会让很多人感到头疼，因为在这种问题中，总是会需要处理平年和闰年（由此产生的二月的天数区别）、大月和小月的问题，因此细节比较繁杂。但是只要细心处理细节，一般都能很好地解决这类问题。

### sy68: 判断闰年 简单

https://sunnywhy.com/sfbj/3/4/68

!!! question 判断闰年：
    给定一个年份，判断其是平年还是闰年。（提示：如果年份是400的倍数，或者是4的倍数但不是100的倍数，那么称这个年份为闰年）

**输入描述**

一个正整数n（$1900 \le n \le 9999$）。

**输出描述**

如果是闰年，那么输出YES，否则输出NO。

样例1

输入

```
1900
```

输出

```
NO
```

样例2

输入

```
2020
```

输出

```
YES
```



```python
n = int(input())
if n % 400 == 0 or (n % 4 == 0 and n % 100 != 0):
    print('YES')
else:
    print('NO')
```



### sy69: 日期加法 简单

https://sunnywhy.com/sfbj/3/4/69

!!! question 日期加法：
    给定一个日期DAY和一个正整数n，求日期DAY加上n天后的日期。

**输入描述**

第一行为给定的日期DAY（格式为YYYY-MM-DD，范围为1900-01-01 $\le DAY \le$ 2199-12-31），数据保证一定合法；

第二行为需要增加的天数n（$1 \le n \le 10000$）。

**输出描述**

以YYYY-MM-DD的格式输出增加了n天后的日期。

样例1

输入

```
2021-05-01
30
```

输出

```
2021-05-31
```

样例2

输入

```
2021-05-01
31
```

输出

```
2021-06-01
```



```python
import datetime

# Read input
day = input().strip()
n = int(input().strip())

# Parse the input date
date = datetime.datetime.strptime(day, '%Y-%m-%d').date()

# Add n days
new_date = date + datetime.timedelta(days=n)

# Print the resulting date in the format YYYY-MM-DD
print(new_date.strftime('%Y-%m-%d'))
```





```python
def is_leap_year(year):
    if year % 400 == 0:
        return True
    if year % 100 == 0:
        return False
    if year % 4 == 0:
        return True
    return False

def add_days_to_date(year, month, day, n):
    month_days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]

    # Adjust for leap year
    if is_leap_year(year):
        month_days[1] = 29

    day += n

    while day > month_days[month - 1]:
        day -= month_days[month - 1]
        month += 1
        if month > 12:
            month = 1
            year += 1
            if is_leap_year(year):
                month_days[1] = 29
            else:
                month_days[1] = 28

    return year, month, day

# Read input
day_input = input().strip()
n = int(input().strip())

# Parse the input date
year, month, day = map(int, day_input.split('-'))

# Add n days
new_year, new_month, new_day = add_days_to_date(year, month, day, n)

# Print the resulting date in the format YYYY-MM-DD
print(f'{new_year:04d}-{new_month:02d}-{new_day:02d}')
```





### sy70: 日期减法 简单

https://sunnywhy.com/sfbj/3/4/70

!!! question 日期减法：
    给定一个日期DAY和一个正整数n，求日期DAY减去n天后的日期。

**输入描述**

第一行为给定的日期DAY（格式为YYYY-MM-DD，范围为1900-01-01 $\le DAY \le$ 2199-12-31），数据保证一定合法；

第二行为需要增加的天数n（$1 \le n \le 10000$）。

**输出描述**

以YYYY-MM-DD的格式输出减少了n天后的日期。

样例1

输入

```
2021-05-31
30
```

输出

```
2021-05-01
```

样例2

输入

```
2021-05-31
31
```

输出

```
2021-04-30
```



```python
def is_leap_year(year):
    if year % 400 == 0:
        return True
    if year % 100 == 0:
        return False
    if year % 4 == 0:
        return True
    return False

def subtract_days_from_date(year, month, day, n):
    month_days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]

    # Adjust for leap year
    if is_leap_year(year):
        month_days[1] = 29

    day -= n

    while day < 1:
        month -= 1
        if month < 1:
            month = 12
            year -= 1
            if is_leap_year(year):
                month_days[1] = 29
            else:
                month_days[1] = 28
        day += month_days[month - 1]

    return year, month, day

# Read input
day_input = input().strip()
n = int(input().strip())

# Parse the input date
year, month, day = map(int, day_input.split('-'))

# Subtract n days
new_year, new_month, new_day = subtract_days_from_date(year, month, day, n)

# Print the resulting date in the format YYYY-MM-DD
print(f'{new_year:04d}-{new_month:02d}-{new_day:02d}')
```





### sy71: 一年中的第几天 简单

https://sunnywhy.com/sfbj/3/4/71

!!! question 一年中的第几天：
    给定一个日期，计算它是所在年份中的第几天。

**输入描述**

第一行为给定的日期DAY（格式为YYYY-MM-DD，范围为1900-01-01$\le DAY \le$2199-12-31），数据保证一定合法。

**输出描述**

输出一个整数，表示第几天。

样例1

输入

```
2021-01-31
```

输出

```
31
```

样例2

输入

```
2021-02-03
```

输出

```
34
```



```python
def is_leap_year(year):
    if year % 400 == 0:
        return True
    if year % 100 == 0:
        return False
    if year % 4 == 0:
        return True
    return False

def day_of_year(year, month, day):
    month_days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]

    # Adjust for leap year
    if is_leap_year(year):
        month_days[1] = 29

    # Calculate the day of the year
    day_of_year = sum(month_days[:month - 1]) + day
    return day_of_year

# Read input
day_input = input().strip()

# Parse the input date
year, month, day = map(int, day_input.split('-'))

# Calculate the day of the year
result = day_of_year(year, month, day)

# Print the resulting day of the year
print(result)
```





### sy72: 日期先后 简单

https://sunnywhy.com/sfbj/3/4/72

!!! question 日期先后：
    给定两个日期DAY1和DAY2，判断DAY1是否在DAY2之前。

**输入描述**

前两行分别为日期DAY1和DAY2（格式为YYYY-MM-DD，范围为1900-01-01$\le DAY \le$2199-12-31），数据保证一定合法。

**输出描述**

如果DAY1在DAY2之前，那么输出YES，否则输出NO。

样例1

输入

```
2021-05-01
2021-05-07
```

输出

```
YES
```

样例2

输入

```
2021-05-01
2021-05-01
```

输出

```
NO
```

样例3

输入

```
2021-05-01
2021-04-12
```

输出

```
NO
```



```python
# Read input
day1 = input().strip()
day2 = input().strip()

# Parse the input dates
year1, month1, day1 = map(int, day1.split('-'))
year2, month2, day2 = map(int, day2.split('-'))

# Compare the dates manually
if (year1 < year2) or (year1 == year2 and month1 < month2) or (year1 == year2 and month1 == month2 and day1 < day2):
    print("YES")
else:
    print("NO")
```





### sy73: 周几 简单

https://sunnywhy.com/sfbj/3/4/73

!!! question 周几：
    给定一个日期DAY，求它是周几。

**输入描述**

第一行为给定的日期DAY（格式为YYYY-MM-DD，范围为1900-01-01$\le DAY \le$2199-12-31），数据保证一定合法。

**输出描述**

输出一个整数，表示周几。其中周一到周六分别用1-6表示，周天用0表示。

样例1

输入

```
2021-05-01
```

输出

```
6
```

样例2

输入

```
2021-05-02
```

输出

```
0
```



```python
#Use Zeller's Congruence algorithm to calculate the day of the week.
#https://www.geeksforgeeks.org/zellers-congruence-find-day-date/
def day_of_week(year, month, day):
    if month < 3:
        month += 12
        year -= 1
    K = year % 100
    J = year // 100
    f = day + 13 * (month + 1) // 5 + K + K // 4 + J // 4 + 5 * J
    return (f % 7 + 6) % 7  # Adjust to make Monday=1, ..., Saturday=6, Sunday=0

# Read input
day_input = input().strip()

# Parse the input date
year, month, day = map(int, day_input.split('-'))

# Calculate the day of the week
result = day_of_week(year, month, day)

# Print the resulting day of the week
print(result)
```





## 5 进制转换 4题

!!! note

    日常生活中人们使用的数字一般都是十进制，而计算机使用的进制是二进制，另外还有八进制、十六进制以及各种数字的进制，那么这就会产生一个问题：**对两个不同进制，应该如何进行相互转换呢？**

    二进制、八进制和十六进制之间可以直接进行转换，而十进制和其他进制之间的转换则需要采用“除基取余法”。

    对一个P进制的数，如果要转换为Q进制数，需要分为两步：

    1. 将P进制数x转换为十进制数y
    2. 将十进制数y转换为Q进制数z（采用除基取余法）

    **除基取余法**：所谓的“基”，是指将要转换成的进制Q，因此除基取余的意思就是每次将待转换数除以Q，然后将得到的余数作为低位存储，而商则继续除以Q并进行上面的操作，最后当商为0时，将所有位从高到低输出就可以得到对应的进制数。

### sy74: 十进制转二进制 简单

https://sunnywhy.com/sfbj/3/5/74

!!! question 十进制转二进制：
    给定一个十进制数n，输出它的二进制形式。

**输入描述**

一个非负整数n（$0 \le n \le 1024$）。

**输出描述**

输出一个01串，表示的二进制。

样例1

输入

```
6
```

输出

```
110
```



```python
n = int(input())
print(bin(n)[2:])
```



```python
# Read input
n = int(input().strip())

# Initialize an empty string for the binary representation
binary_representation = ""

# Convert to binary manually
if n == 0:
    binary_representation = "0"
else:
    while n > 0:
        binary_representation = str(n % 2) + binary_representation
        n //= 2

# Print the binary representation
print(binary_representation)
```

### sy75: 二进制转十进制 简单

https://sunnywhy.com/sfbj/3/5/75

!!! question 二进制转十进制：
    给定一个二进制01串，输出它的十进制形式。

**输入描述**

一个二进制01串（长度不超过10）。

**输出描述**

输出十进制形式。

样例1

输入

```
110
```

输出

```
6
```


```python
bin_str = input()
total_val = 0
for idx,val in enumerate(bin_str[::-1]):
    total_val += 2**idx * int(val)
print(total_val)
```





### sy76: 十进制转K进制 简单

https://sunnywhy.com/sfbj/3/5/76

!!! question 十进制转K进制：
    给定一个十进制数n，输出它的K进制形式。

**输入描述**

一个非负整数n（$0 \le n \le 1024$）和一个正整数K（$2 \le K \le 16$）。

**输出描述**

输出一行，表示的进制。其中超过9的位使用大写英文字母表示（10 => A、11 => B、12 => C、13 => D、14 => E、15 => F）。

样例1

输入

```
6 2
```

输出

```
110
```

样例2

输入

```
45 16
```

输出

```
2D
```



```python
dic = [0,1,2,3,4,5,6,7,8,9,'A','B','C','D','E','F']
n,k = map(int, input().split())

k_representation = ""

if n == 0:
    k_representation = "0"
else:
    while n > 0:
        k_representation = str(dic[n % k]) + k_representation
        n //= k

print(k_representation)
```





### sy77: K进制转十进制 简单

https://sunnywhy.com/sfbj/3/5/77

!!! question K进制转十进制：
    给定一个K进制串，输出它的十进制形式。

**输入描述**

一个K进制串（长度不超过7，其中超过9的位使用大写英文字母表示（A => 10、B => 11、C => 12、D => 13、E => 14、F => 15））和一个正整数K（$2 \le K \le 16$）。

**输出描述**

输出对应的十进制形式。

样例1

输入

```
110 2
```

输出

```
6
```

样例2

输入

```
2D 16
```

输出

```
45
```



```python
dic = {'0':0,'1':1,'2':2,'3':3,'4':4,'5':5,'6':6,'7':7,'8':8,'9':9,'A':10,'B':11,'C':12,'D':13,'E':14,'F':15}

k_str, k = input().split()
k = int(k)
total_val = 0
for idx,val in enumerate(k_str[::-1]):
    total_val += k**idx * dic[val]
print(total_val)
```



## 6 字符串处理 8题

!!! note

    字符串处理题在考试中十分常见，也是能很好体现代码能力的一种题型。对于这种题型，一般需要仔细分析清楚题目中的输入和输出格式才能顺利解决题目。在有些题目中，可能实现逻辑会非常麻烦，而且可能会有很多细节和边界情况，因此对代码能力较弱的考生是很不利的。此类题目需要多做多想，积累经验。

### sy78: 回文字符串 简单

https://sunnywhy.com/sfbj/3/6/78

!!! question 回文字符串：
    如果一个字符串逆序后与正序相同，那么称这个字符串为回文字符串。例如`abcba`是回文字符串，`abcca`不是回文字符串。

    给定一个字符串，判断它是否是回文字符串。

**输入描述**

一个非空字符串（长度不超过 ，仅由小写字母组成）。

**输出描述**

如果是回文字符串，那么输出`YES`，否则输出`NO`。

样例1

输入

```
abcba
```

输出

```
YES
```

样例2

输入

```
abcca
```

输出

```
NO
```



```python
s = input()
s_rev = s[::-1]
if s == s_rev:
    print('YES')
else:
    print('NO')
```



### sy79:  单词倒序 简单

https://sunnywhy.com/sfbj/3/6/79

!!! question 单词倒序：
    给定一堆用空格隔开的英文单词，输出这些英文单词的倒序（单词内部保持原序）。

**输入描述**

一堆英文单词，每个单词不超过10个字符，且仅由大小写字母组成；每两个单词之间用一个空格隔开，整个字符串的长度不超过1000。

**输出描述**

输出英文单词的倒序，单词之间仍然是一个空格隔开，行末不允许有多余的空格。

样例1

输入

```
Hao Hao Xue Xi
```

输出

```
Xi Xue Hao Hao
```



```python
s = input().split()
print(' '.join(s[::-1]))
```



### sy80: 单词倒序II  简单

https://sunnywhy.com/sfbj/3/6/80

!!! question 单词倒序II：
    给定一堆用空格隔开的英文单词，将每个单词内部逆序后输出（单词顺序不变）。

**输入描述**

一堆英文单词，每个单词不超过10个字符，且仅由大小写字母组成；每两个单词之间用一个空格隔开，整个字符串的长度不超过1000。

**输出描述**

输出每个单词内部逆序后的结果，单词之间仍然是一个空格隔开，行末不允许有多余的空格。

样例1

输入

```
Hao Hao Xue Xi
```

输出

```
oaH oaH euX iX
```



```python
s = input().split()
ans = []
for token in s:
    ans.append(token[::-1])
print(' '.join(ans))
```



### sy81: 单词数 简单

https://sunnywhy.com/sfbj/3/6/81

!!! question 单词数：
    给定一堆用空格隔开的英文单词，统计单词个数。

**输入描述**

一堆英文单词，每个单词不超过10个字符，且仅由大小写字母组成；每两个单词之间用一个空格隔开，整个字符串的长度不超过1000。

**输出描述**

输出一个整数，表示单词的个数。

样例1

输入

```
good good study
```

输出

```
3
```



```python
print(len(input().split()))
```



### sy82:  首字母大写 简单

https://sunnywhy.com/sfbj/3/6/82

!!! question 首字母大写：
    给定一堆用空格隔开的英文单词，将每个单词的首字母改为大写后输出。

**输入描述**

一堆英文单词，每个单词不超过10个字符，且仅由小写字母组成；每两个单词之间用一个空格隔开，整个字符串的长度不超过1000。

**输出描述**

输出每个单词首字母大写后的结果，单词之间仍然是一个空格隔开，行末不允许有多余的空格。

样例1

输入

```
good good study
```

输出

```
Good Good Study
```



```python
s = input().strip().split()
ans = [word.capitalize() for word in s]
print(' '.join(ans))
```



### sy83:  公共前缀 简单

https://sunnywhy.com/sfbj/3/6/83

!!! question 公共前缀：
    给定个字符串，求它们的公共前缀。

**输入描述**

第一行为一个正整数n（$2 \le n \le 20$），表示字符串的个数。

接下来行，每行一个字符串（仅由大小写字母组成），每个字符串的长度不超过50。

**输出描述**

输出个字符串的公共前缀。如果没有公共前缀，那么输出空行。

样例1

输入

```
3
actrpg
actfps
actarpg
```

输出

```
act
```

样例2

输入

```
3
actrpg
Actfps
actarpg
```

输出

```

```



```python
def common_prefix(strs):
    if not strs:
        return ""
    
    # Start with the first string as the prefix
    prefix = strs[0]
    
    for s in strs[1:]:
        # Update the prefix by comparing it with each string
        while s[:len(prefix)] != prefix and prefix:
            prefix = prefix[:-1]
        if not prefix:
            break
    
    return prefix

if __name__ == "__main__":
    n = int(input().strip())
    strs = [input().strip() for _ in range(n)]
    result = common_prefix(strs)
    print(result)
```



### sy84:  连续相同字符统计 简单

https://sunnywhy.com/sfbj/3/6/84

!!! question 连续相同字符统计：
    给定一个字符串，统计其中连续出现的相同字符个数。

**输入描述**

一个非空字符串（长度不超过100，仅由小写字母组成）。

**输出描述**

按从左到右字符出现的顺序，输出每个字符连续出现的个数。

其中每个字符输出一行，每行以空格为分隔，输出该字符与出现的个数。

样例1

输入

```
abbbcc
```

输出

```
a 1
b 3
c 2
```

样例2

输入

```
ccbbc
```

输出

```
c 2
b 2
c 1
```



```python
def count_consecutive_characters(s):
    if not s:
        return

    result = []
    current_char = s[0]
    count = 1

    for char in s[1:]:
        if char == current_char:
            count += 1
        else:
            result.append((current_char, count))
            current_char = char
            count = 1
    result.append((current_char, count))

    for char, count in result:
        print(f"{char} {count}")

if __name__ == "__main__":
    s = input().strip()
    count_consecutive_characters(s)
```



### sy85:  C语言合法变量名简单

https://sunnywhy.com/sfbj/3/6/85

!!! question C语言合法变量名：
    一个合法的C语言变量名需要满足：

    - 所有字符必须由且仅由字母（A-Z,a-z）、数字（0-9）、下划线（_）组成；
    - 首字符不能是数字，可以是字母或下划线；
    - 不能是C语言关键字，如if、while等。
    
    给定一个**非**C语言关键字的字符串，判断其是否可以作为合法的C语言变量名。

**输入描述**

一个非空字符串（长度不超过20）。数据保证不会出现C语言关键字。

**输出描述**

如果可以作为合法的C语言变量名，那么输出YES，否则输出NO。

样例1

输入

```
a1
```

输出

```
YES
```

样例2

输入

```
1a
```

输出

```
NO
```



```python
def is_valid_c_variable_name(s):
    c_keywords = {
        "auto", "break", "case", "char", "const", "continue", "default", "do", "double", "else", "enum", "extern", 
        "float", "for", "goto", "if", "inline", "int", "long", "register", "restrict", "return", "short", "signed", 
        "sizeof", "static", "struct", "switch", "typedef", "union", "unsigned", "void", "volatile", "while", "_Alignas", 
        "_Alignof", "_Atomic", "_Bool", "_Complex", "_Generic", "_Imaginary", "_Noreturn", "_Static_assert", "_Thread_local"
    }

    if not s:
        return "NO"

    if s in c_keywords:
        return "NO"

    if not (s[0].isalpha() or s[0] == '_'):
        return "NO"

    for char in s[1:]:
        if not (char.isalnum() or char == '_'):
            return "NO"

    return "YES"

if __name__ == "__main__":
    s = input().strip()
    print(is_valid_c_variable_name(s))
```





## 7 综合练习精选 16题

### sy884: 统计一下 入门

https://sunnywhy.com/sfbj/3/7/884

!!! question 统计一下
    给定一个区间 [L,R]，其中 L 和 R 为正整数。你的任务是计算这个区间内所有整数的十进制表示中出现的数字 1 的总次数。

**输入描述**

输入包含两个整数 L 和 R（$1 \le L \le R \le 10000$），分别表示区间的左右端点。

**输出描述**

输出一个整数，表示区间 [L,R] 中所有整数的十进制表示中数字 出现的总次数。

样例1

输入

```
1 11
```

输出

```
4
```

解释

在区间 [1,11]中，数字 1、10、11 中的 1、10分别出现了 1 次，数字 11中的 1出现了 2 次，因此总共出现了 4 次 。



```python
def count_ones_in_range(L, R):
    count = 0
    for num in range(L, R + 1):
        count += str(num).count('1')
    return count

if __name__ == "__main__":
    L, R = map(int, input().strip().split())
    result = count_ones_in_range(L, R)
    print(result)
```



### sy569: 双向喜欢 入门

https://sunnywhy.com/sfbj/3/7/569

!!! question 双向喜欢：
    给定n个人的q组喜欢关系，问是否有双向喜欢的情况存在。

**输入描述**

第一行为两行数字n,q。

后面q行，每行两个数字x,y，表示x喜欢y，注意这里是单向喜欢。

$1 \le n \le 10 $

$1 \le q \le 10$

$1 \le x,y \le n$

$x \ne y$



**输出描述**

如果有双向喜欢的情况则输出`Yes`，否则输出`No`。

样例1

输入

```
3 3
1 2
2 1
1 3
```

输出

```
Yes
```

样例2

输入

```
3 3
1 2
2 3
3 1
```

输出

```
No
```



```python
# 周嘉豪24工学院
n,q=map(int,input().split())
Like=[]
for _ in range(q):
    x,y=input().split()
    Like.append(x+y)
    Like.append(y+x)
like=set(Like)
if len(like)==len(Like):
    print('No')
else:
    print('Yes')
```



```python
def has_mutual_likes(n, q, likes):
    like_set = set()
    for x, y in likes:
        if (y, x) in like_set:
            return "Yes"
        like_set.add((x, y))
    return "No"

if __name__ == "__main__":
    n, q = map(int, input().strip().split())
    likes = [tuple(map(int, input().strip().split())) for _ in range(q)]
    result = has_mutual_likes(n, q, likes)
    print(result)
```



### sy570: 三方欢喜 简单

https://sunnywhy.com/sfbj/3/7/570

!!! question 三方欢喜：
    给定n个人的q组喜欢关系，问是否有三方欢喜的情况存在，即a喜欢b ，b喜欢c，还有c也喜欢a。

**输入描述**

第一行为两行数字n,q。

后面q行，每行两个数字x,y，表示x喜欢y，注意这里是单向喜欢。

$1 \le n \le 10 $

$1 \le q \le 10$

$1 \le x,y \le n$

$x \ne y$

**输出描述**

如果有三方欢喜的情况则输出`Yes`，否则输出`No`。

样例1

输入

```
3 3
1 2
2 1
1 3
```

输出

```
No
```

样例2

输入

```
3 3
1 2
2 3
3 1
```

输出

```
Yes
```



初始化一个字典用于存储喜欢关系。
遍历 q 行输入，记录每个喜欢关系。
检查是否存在三方欢喜的情况，即 a 喜欢 b，b 喜欢 c，c 喜欢 a。

```python
def has_three_way_likes(n, q, likes):
    like_dict = {}
    for x, y in likes:
        if x not in like_dict:
            like_dict[x] = set()
        like_dict[x].add(y)
    
    for a in like_dict:
        for b in like_dict[a]:
            if b in like_dict:
                for c in like_dict[b]:
                    if c in like_dict and a in like_dict[c]:
                        return "Yes"
    return "No"

if __name__ == "__main__":
    n, q = map(int, input().strip().split())
    likes = [tuple(map(int, input().strip().split())) for _ in range(q)]
    result = has_three_way_likes(n, q, likes)
    print(result)
```



### sy571:  四方坐标 入门

https://sunnywhy.com/sfbj/3/7/571

!!! question 四方坐标：
    给定一个矩形在直角坐标系`xOy`上的两个对顶点的坐标，求这个矩形的面积。

    假设矩形的所有边均平行于x轴或y轴。

**输入描述**

两行，每行为一个整数坐标x,y，分别表示两个对顶点的坐标。

数据范围：

$-100 \le x,y \le 100$

**输出描述**

一个整数，这个矩形的面积。数据保证矩形的面积不会为0。

样例1

输入

```
1 1
2 3
```

输出

```
2
```

解释

左下角坐标为`(1,1)`，右上角坐标为`(2,3)`，该矩形的面积是`2`。



```python
x1, y1 = map(int, input().split())
x2, y2 = map(int, input().split())
print(abs(x1 - x2) * abs(y1 - y2))
```





### sy572:  五次求导 简单

https://sunnywhy.com/sfbj/3/7/572

!!! question 五次求导：
    给定一个多项式函数:

    $f(x) = a_0 x^{b_0} + a_1 x^{b_1} + \ldots + a_{n-2} x^{b_{n-2}} + a_{n-1} x^{b_{n-1}}$

    对这个f(x)求五阶导函数$f^{'''''}(x)$。

    问这个五阶导函数最后的表达式是什么。

**输入描述**

第一行为n。

第二行到n+1行为都为整数$a_i,b_i$表示这个有一项。

其中 

$1 \le n \le 10$

$-10 \le a \le 10$

$1 \le b \le 10$

**输出描述**

输出求导后的多项式，每一行两个整数，按照的次数从高到低输出他的系数和次数。

如果$f^{'''''}(x)=0$则输出`0 0`

如果是有非零常数项，比如$f^{'''''}(x)=(\sum a_ix^{b_i}) + C$，则在最后一行输出`C 0`。

样例1

输入

```
2
1 5
1 4
```

输出

```
120 0
```

解释

$f(x) = x^5 + x^4$

那么有

$f^{'''''}(x)=120$



```python
def compute_kth_derivative(a, b, k):
    if b < k:
        return 0, 0
    coefficient = a
    exponent = b
    for i in range(k):
        coefficient *= exponent
        exponent -= 1
    return coefficient, exponent

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    data = input().strip().split()

    n = int(data[0])
    terms = [(int(data[i*2+1]), int(data[i*2+2])) for i in range(n)]

    k = 5
    result = {}
    for a, b in terms:
        coeff, exp = compute_kth_derivative(a, b, k)
        if coeff != 0:
            if exp in result:
                result[exp] += coeff
            else:
                result[exp] = coeff

    if not result:
        print("0 0")
    else:
        sorted_result = sorted(result.items(), key=lambda x: -x[0])
        for exp, coeff in sorted_result:
            if coeff == 0:
                continue
            print(coeff, exp)
```



### sy573: 六小时差 入门

https://sunnywhy.com/sfbj/3/7/573

!!! question 六小时差：
    给定一个24小时制时间，包括小时和分钟，问六小时x分钟后，时间是多少。

    如果时间跨天了，则按照跨天后的时间算。

**输入描述**

第一行，一个整数数字x。

第二行，两个数字，表示当天的时间，分别是小时h和分钟m。数据保证数据合法。

$0 \le x \le 59$

$0 \le h \le 23$

$0 \le m \le 59$

**输出描述**

6小时x分钟后的时间。

样例1

输入

```
6
0 0
```

输出

```
6 6
```

样例2

输入

```
1
23 59
```

输出

```
6 0
```



```python
if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    data = input().strip().split()

    x = int(data[0])
    h = int(data[1])
    m = int(data[2])

    # Add 6 hours and x minutes
    new_h = h + 6
    new_m = m + x

    # Handle minute overflow
    if new_m >= 60:
        new_h += new_m // 60
        new_m = new_m % 60

    # Handle hour overflow
    if new_h >= 24:
        new_h = new_h % 24

    print(new_h, new_m)
```





### sy574: 周七迷踪 简单

https://sunnywhy.com/sfbj/3/7/574

!!! question 周七迷踪：
    给定年月日，问下一个周日是什么时候。

    如果给定时间本身是周日，则输出当天时间。

**输入描述**

一行，3个数字，分别表示年月日，其中年月日保证数据合法，为2000年到2099年的某一天。

**输出描述**

下一个周天的时间，3个数字，分别是年月日。

样例1

输入

```
2000 1 1
```

输出

```
2000 1 2
```

解释

2000年的1月1号是周六。 那么2000年的1月2号是周日。



```python
import datetime

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    data = input().strip().split()

    year = int(data[0])
    month = int(data[1])
    day = int(data[2])

    given_date = datetime.date(year, month, day)
    day_of_week = given_date.weekday()  # Monday is 0 and Sunday is 6

    # Calculate days to add to reach next Sunday
    days_to_add = (6 - day_of_week) % 7

    next_sunday = given_date + datetime.timedelta(days=days_to_add)

    print(next_sunday.year, next_sunday.month, next_sunday.day)
```





### sy575: 八次翻转 入门

https://sunnywhy.com/sfbj/3/7/575

!!! question 八次翻转：
    给定一个字符串S，下标从0开始，按照顺序对这个字符串进行如下操作8次，操作为对字符串下标区间$[L_i,Ri)$的元素进行一次翻转（即字符串逆置）。

    输出S的最终状态。

**输入描述**

第一行是一个字符串S

第2到9行为$L_i,Ri$，表示一次操作的下标区间。

$1 \le len(S) \le 1000$

$0 \le Li < Ri \le len(S)$



**输出描述**

八次翻转之后最终的S

样例1

输入

```
ab
0 2
0 2
0 2
0 2
0 2
0 2
0 2
0 2
```

输出

```
ab
```



```python
def reverse_substring(s, l, r):
    return s[:l] + s[l:r][::-1] + s[r:]

def main():
    import sys
    input = sys.stdin.read
    data = input().strip().split('\n')
    
    s = data[0]
    for i in range(1, 9):
        l, r = map(int, data[i].split())
        s = reverse_substring(s, l, r)
    
    print(s)

if __name__ == "__main__":
    main()
```



### sy576: 九阵寻词 简单

https://sunnywhy.com/sfbj/3/7/576

!!! question 九阵寻词：
    给定一个`9 x 9`的小写字母方阵。

    问单词S是否在这个方阵中，其中S存在的形式可以是横向（从左到右）或竖向（从上到下）。

**输入描述**

1到9行为一个长度为9的小写字符串。

第10行为S。

$1 \le len(S) \le 9$

**输出描述**

如果S存在这个方阵中，则输出`Yes`，否则输出`No`。

样例1

输入

```
srnosuios
dmakyisab
qvwmiyxch
xzulwrfve
nbsfclffj
lplflenmc
mpwvldpoe
wgeeaeyvi
inzyaapfv
lmwi
```

输出

```
Yes
```



```python
def main():
    import sys
    input = sys.stdin.read
    data = input().strip().split('\n')

    matrix = data[:9]
    word = data[9]

    # Check rows
    for row in matrix:
        if word in row:
            print("Yes")
            return

    # Check columns
    for col in range(9):
        column = ''.join(matrix[row][col] for row in range(9))
        if word in column:
            print("Yes")
            return

    print("No")

if __name__ == "__main__":
    main()
```



### sy577: 一O交错 入门

https://sunnywhy.com/sfbj/3/7/577

!!! question 一O交错：
    给定一个01字符串S，问最长的和的交错区间的长度。

    其中0和1的交错区间是指，在这个区间范围的任意两个相邻的数字都不同。例如01010是交错的，001不是交错的。

**输入描述**

一行，一个01字符串S。

$1 < |S| < 1000$

**输出描述**

一个整数，最长的0和1的交错区间的长度。

注意交错没有0和1先后之分。

样例1

输入

```
10
```

输出

```
2
```

样例2

输入

```
00
```

输出

```
1
```

样例3

输入

```
000101000
```

输出

```
5
```

解释

中间的01010是交错区间，长度为5。



```python
def longest_alternating_substring(s):
    if len(s) < 2:
        return len(s)
    
    max_length = 1
    current_length = 1
    
    for i in range(1, len(s)):
        if s[i] != s[i - 1]:
            current_length += 1
        else:
            max_length = max(max_length, current_length)
            current_length = 1
    
    max_length = max(max_length, current_length)
    return max_length

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    s = input().strip()
    print(longest_alternating_substring(s))
```



### sy578: 一一相依 中等

https://sunnywhy.com/sfbj/3/7/578

!!! question 一一相依：
    给定一个字符串，只包含字符0和1，现在能把这个数组里的最多k个0变为1，操作后，最长的连续`1`的子串有多长。

**输入描述**

第一行两个数字n,k，表示字符串的长度和可操作次数k。

第二行为一个字符串。

$0 < n \le 30$

$0 \le k \le 30$

注意n和k没有互相限制关系。

**输出描述**

输出操作后的最长的连续`1`的子串的长度。

样例1

输入

```
20 2
11111011111110111110
```

输出

```
19
```

说明

本题有时间复杂度为O(n)的算法，请比赛期间独立思考。



这是一个经典的“双指针 / 滑动窗口”问题，可以用 **O(n)** 的时间复杂度解决。

------

思路讲解

题目要求：

> 最多将 k 个 `'0'` 翻转为 `'1'`，求操作后最长连续 `'1'` 子串长度。

滑动窗口思路：

- 维护一个窗口 `[left, right)`。
- `right` 指针向右移动，每加入一个字符：
  - 若它是 `'0'`，我们就让可用的 `k` 减 1；
  - 如果此时 `k < 0`，说明窗口中 0 的数量超过可翻转上限，我们就需要移动 `left`：
    - 当左端离开一个 `'0'`，我们就恢复一个翻转机会 (`k += 1`)。
- 过程中记录窗口最大长度即可。



```python
n, k = map(int, input().split())
s = input().strip()

left = 0
max_len = 0

for right in range(n):
    if s[right] == '0':
        k -= 1
    while k < 0:
        if s[left] == '0':
            k += 1
        left += 1
    max_len = max(max_len, right - left + 1)

print(max_len)
```

时间复杂度：O(n)





**Plan**

1. Read the input values \( n \) and \( k \).
2. Read the binary string.
3. Use a sliding window approach to find the longest substring of `1`s that can be obtained by flipping at most \( k \) `0`s to `1`s.
4. Initialize two pointers, `left` and `right`, to represent the window's boundaries.
5. Use a variable to count the number of `0`s in the current window.
6. Expand the window by moving the `right` pointer and update the count of `0`s.
7. If the count of `0`s exceeds \( k \), move the `left` pointer to shrink the window until the count of `0`s is less than or equal to \( k \).
8. Keep track of the maximum length of the window that meets the condition.
9. Output the maximum length.

**Code**

```python
def longest_ones_after_k_flips(n, k, s):
    left = 0
    max_length = 0
    zero_count = 0

    for right in range(n):
        if s[right] == '0':
            zero_count += 1

        while zero_count > k:
            if s[left] == '0':
                zero_count -= 1
            left += 1

        max_length = max(max_length, right - left + 1)

    return max_length

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    data = input().strip().split()
    
    n = int(data[0])
    k = int(data[1])
    s = data[2]
    
    print(longest_ones_after_k_flips(n, k, s))
```





### sy579: 二三乃大 入门

https://sunnywhy.com/sfbj/3/7/579

!!! question 二三乃大：
    给定一个数字字符串S，现在把这个字符串里面2和3拿出来，重新组合一个新的整数，问最大能组合出的整数。

    如果无法组合，则输出0。

**输入描述**

一个数字字符串S

$0 < Length(S) \le 1000$



**输出描述**

输出最大能组合出的整数

样例1

输入

```
12321
```

输出

```
322
```

样例2

输入

```
44
```

输出

```
0
```



```python
def max_combination(s):
    digits = [char for char in s if char in '23']
    if not digits:
        return 0
    digits.sort(reverse=True)
    return int(''.join(digits))

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    s = input().strip()
    print(max_combination(s))
```



### sy580: 四面楚歌 简单

https://sunnywhy.com/sfbj/3/7/580

!!! question 四面楚歌：
    给定一个的$n \times m$数字矩阵，每个数字都为1到9。

    现在选定一个位置，记该位置所在列的最上方的数字为A、该位置所在行的最右侧的数字为B、该位置所在列的最下方的数字为C、该位置所在行的最左侧的数字为D。将这四个数字组成一个新的整数ABCD。

    问选取哪个位置（对应的数字为$x$），可以使得$x \times ABCD$的值最大。输出这个最大值。

**输入描述**

第一行为两个数字n,m，分别表示这个数字的矩阵的行数和列数。

第2到n+1行为数字矩阵每一行的数字，用空格分开。

$1 \le n,m \le 100$



**输出描述**

输出一个整数，表示能得到的最大值。

样例1

输入

```
3 3
1 8 2
5 9 7
3 6 4
```

输出

```
78885
```

解释

选中间9的时候，值为9*(8765)=78885，此时是最大的。



**Pseudocode:**

1. Parse the input to get the dimensions of the matrix \( n \) and \( m \).
2. Read the matrix values.
3. Initialize a variable to store the maximum value.
4. Iterate through each position in the matrix:
   - For each position, determine the values of \( A \), \( B \), \( C \), and \( D \).
   - Form the integer \( ABCD \) from these values.
   - Calculate the product of the current position's value and \( ABCD \).
   - Update the maximum value if the current product is greater.
5. Output the maximum value.

**Code:**

```python
def find_max_value(n, m, matrix):
    max_value = 0

    for i in range(n):
        for j in range(m):
            A = matrix[0][j]
            B = matrix[i][m-1]
            C = matrix[n-1][j]
            D = matrix[i][0]
            ABCD = int(f"{A}{B}{C}{D}")
            current_value = matrix[i][j] * ABCD
            max_value = max(max_value, current_value)

    return max_value

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    data = input().split()
    
    n = int(data[0])
    m = int(data[1])
    matrix = []
    index = 2
    for i in range(n):
        row = list(map(int, data[index:index + m]))
        matrix.append(row)
        index += m
    
    result = find_max_value(n, m, matrix)
    print(result)
```



### sy581: 六的倍数

https://sunnywhy.com/sfbj/3/7/581

!!! question 六的倍数：
    已知一个非负整数的所有数位相加，如果结果是3的倍数，那么这个数字能被3整除。

    现在问一个数字x，问它是否能被6整除。

**输入描述**

一个整数字符串。

数据范围：

$0 \le x \le 10^{1000}$

**输出描述**

如果数字能被整除，输出`Yes`；否则输出`No`。

样例1

输入

```
123
```

输出

```
No
```

样例2

输入

```
18
```

输出

```
Yes
```



```python
def is_divisible_by_6(x):
    # Check if the last digit is even
    if int(x[-1]) % 2 != 0:
        return "No"
    
    # Calculate the sum of all digits
    digit_sum = sum(int(digit) for digit in x)
    
    # Check if the sum of digits is divisible by 3
    if digit_sum % 3 == 0:
        return "Yes"
    else:
        return "No"

if __name__ == "__main__":
    import sys
    input = sys.stdin.read().strip()
    result = is_divisible_by_6(input)
    print(result)
```



### sy582: 七次选择

https://sunnywhy.com/sfbj/3/7/582

!!! question 七次选择：
    求组合数$C_n^7$。

    其中$C_n^7 = \frac{n!}{7!(n-7)!}$。

**输入描述**

一个整数N。

$7 \le N \le 50$

**输出描述**

组合数$C_n^7$的值。

数据保证$1 \le C_n^7 \le 2 \times 10^9$。

样例1

输入

```
7
```

输出

```
1
```



```python
import math

def combination_n_7(n):
    if n < 7:
        return 0
    return math.factorial(n) // (math.factorial(7) * math.factorial(n - 7))

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    n = int(input().strip())
    result = combination_n_7(n)
    print(result)
```





### sy583: 抽象三角图形

https://sunnywhy.com/sfbj/3/7/583

!!! question 抽象三角图形：
    输出一个腰长为$n (n \ge 2)$的抽象等腰直角三角形。

    比如n = 2时输出

    ```text
     #
    ##
    ```

    n = 3时，输出

    ```text
      #
     ##
    ###
    ```

    其中空白部分为空格。

**输入描述**

一个整数n。

$2 \le n \le 100$

**输出描述**

参照题目描述。

样例1

输入

```
3
```

输出

```
  #
 ##
###
```



```python
def print_isosceles_right_triangle(n):
    for i in range(1, n + 1):
        spaces = ' ' * (n - i)
        hashes = '#' * i
        print(spaces + hashes)

if __name__ == "__main__":
    import sys
    input = sys.stdin.read
    n = int(input().strip())
    print_isosceles_right_triangle(n)
```
