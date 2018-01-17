# Problems

|   题目   |   输入文件    |    输出文件    |   时间限制   |  空间限制  |
| :----: | :-------: | :--------: | :------: | :----: |
|  kill  |  kill.in  |  kill.out  | 1 second | 256 MB |
| beauty | beauty.in | beauty.out | 1 second | 256 MB |
| weight | weight.in | weight.out | 2 second | 256 MB |

*注：评测时需要开启-O2编译选项。*

## kill

#### 题目描述

​	有$n$个人要完成任务，每个人的任务是：从他们当前的位置出发，打倒一个怪物，然后返回任务交付点。

​	现在郊区一共有$m$只怪物，所有人、所有怪物以及任务交付点在一条直线上，现在告诉你每个人所在的位置$p_1,p_2,\dots,p_n$，以及每个怪物的位置$q_1,q_2,\dots,q_m$，任务交付点的位置为$s$，你需要给每个人选择一只怪物去打，要求每个人都有一只怪物打，每个怪物最多被一个人打，假如所有人同时开始任务，你需要最小化最晚完成任务的人所需要的时间（假如一个位置为$p$的人去打一个位置为$q$的怪物，完成任务所需要的时间为$\mid p - q \mid + \mid q - s \mid$，我们忽略了打怪物需要的时间，因为这$n$个人都是打怪大佬）。

​	你只需要求出最优方案中，最晚完成任务的人完成任务需要的时间。

#### 输入格式

​	第一行包含四个整数$n,m,s$，表示人数、怪物数及任务交付点的位置。

​	第二行包含$n$个整数$p_1,p_2,\dots,p_n$。

​	第三行包含$m$个整数$q_1,q_2,\dots,q_n$。	

#### 输出格式

​	输出一行包含一个整数$ans$，表示答案。	

#### 样例

输入数据：

> 2 4 5
>
> 2 10
>
> 6 1 4 8

输出数据：

> 5

样例解释：第一个人打位置为4的怪物，第二个人打位置为8的怪物，前者花3的时间，后者花5的时间，该方案对应的时间为5，且是一个最优方案。

#### 数据范围

对于所有数据：$1 \leq p_i, q_i, s\leq 10^9$。

| 数据组数 |  n   |  m   |
| :--: | :--: | :--: |
|  1   |  5   |  17  |
|  2   |  7   |  18  |
|  3   |  9   |  19  |
|  4   |  2   | 5000 |
|  5   |  3   | 2000 |
|  6   | 5000 | 5000 |
|  7   |  50  | 100  |
|  8   | 100  | 200  |
|  9   | 1000 | 2000 |
|  10  | 2500 | 5000 |



## beauty

#### 题目描述

​	距离产生美。

​	一棵包含$n$个点的树，有$2k$个不同的关键点，我们现在需要将这些点两两配对，对于一种形如：
$$
(u_1,v_1),(u_2,v_2),\dots,(u_k,v_k)
$$
的配对方案，我们定义其美丽值为：
$$
beauty = \sum_{i=1}^{k}dist(u_i,v_i)
$$
（其中$dist(u,v)$ 表示点$u$到$v$的简单路径的边数）。

​	现在，请你找出美丽值最大的配对方案的美丽值。

#### 输入格式

​	第一行包含三个整数$n,k,a$ 其中$a$为1表示有特殊性质，$a$为0表示没有特殊性质。

​	第二行包含$2k$个不同整数 $u_1,u_2,\dots,u_{2k}$，表示关键点。

​	接下来$n-1$行每行包含两个整数$u,v$，表示一条边。	

#### 输出格式

​	输出一行，包含一个整数表示最大的$beauty$值。

#### 样例

样例输入：

> 7 2 0
>
> 1 5 6 2
>
> 1 3
>
> 3 2
>
> 4 5
>
> 3 7
>
> 4 3
>
> 4 6

样例输出：

> 6

样例解释：(1,6),(2,5)这种配对方案美丽值最大，为6（dist(1,6)+dist(2,5) = 3 + 3 = 6)。

#### 数据范围

特殊性质：每个点的度数小于等于2.

对于所有数据：$1 \leq u_i, v_i \leq n$且$1 \leq u, v \leq n$ 。

| 数据组数 |   n    |   k   | 特殊性质 |
| :--: | :----: | :---: | :--: |
|  1   | 12331  |   6   |  No  |
|  2   | 22321  |   6   | Yes  |
|  3   | 23214  |  10   |  No  |
|  4   | 41231  |  10   |  No  |
|  5   | 21111  |  10   | Yes  |
|  6   | 20000  | 10000 |  No  |
|  7   | 30000  | 15000 |  No  |
|  8   | 100000 | 10000 | Yes  |
|  9   | 100000 | 20000 |  No  |
|  10  | 100000 | 30000 |  No  |


## weight

#### 题目描述

​	给你一个$n$个点$m$条边的带边权的无向图（无重边，无自环），现在对于每条边，问你这条边的权值最大可以是多大，使得这条边在无向图的所有最小生成树中？（边权都是整数）。

#### 输入格式

​	第一行包含三个整数$n,m,a$表示点数和边数及特殊性质标记（如果$a=0$表示没有特殊性质，如果$a = 1$表示有特殊性质）。

​	接下来$m$行每行包含三个整数$u,v,w$表示有一条$u$和$v$之间的边，且边权为$w$。

#### 输出格式

​	 输出一行，包含$m$个数，第$i$个数表示第$i$条边对应的答案（如果某条边的权值可以取到$+\infty$，输出-1）。

#### 样例

输入数据：

> 4 4 0
>
> 1 2 1
>
> 2 3 1
>
> 3 4 1
>
> 4 1 2

输出数据：

> 1 1 1 0

输入数据：

> 4 3 0
>
> 1 2 2
>
> 2 3 2
>
> 3 4 2

输出数据：

> -1 -1 -1

#### 数据范围

特殊性质：$w = 1$ （对于所有边）；

对于所有数据：$1 \leq u, v \leq n$，$1 \leq w \leq 10^9$ 。

| 数据组数 |   n   |   m    | 特殊性质 |
| :--: | :---: | :----: | :--: |
|  1   |  100  |  100   |  No  |
|  2   | 1000  |  1000  |  No  |
|  3   | 10000 | 10000  |  No  |
|  4   | 30000 | 100000 | Yes  |
|  5   | 50000 | 100000 | Yes  |
|  6   | 70000 | 100000 | Yes  |
|  7   | 10000 | 100000 |  No  |
|  8   | 30000 | 100000 |  No  |
|  9   | 50000 | 100000 |  No  |
|  10  | 70000 | 100000 |  No  |