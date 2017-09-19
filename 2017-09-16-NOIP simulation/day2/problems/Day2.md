# Problems

|   题目    |    输入文件    |    输出文件     |   时间限制   |  空间限制  |
| :-----: | :--------: | :---------: | :------: | :----: |
| attack  | attack.in  | attack.out  | 1 second | 256 MB |
| reverse | reverse.in | reverse.out | 1 second | 256 MB |
|  tree   |  tree.in   |  tree.out   | 1 second | 256 MB |

## attack

#### 题目描述

​	风国又跑去打仗了。

​	现在，风国大将军知道了敌军共有$n$个城市，并用$1\dots n$将他们标号，其中$1$号城市是他们的首都。在这些城市之间，有一些单向道路，并且保证从首都可以到达其他所有城市。大将军获得很多情报，每条情报表示敌军会从首都向一些城市增兵，大将军希望知道，有多少个城市是所有增兵的必经之地。（敌军如果会派遣$k$路大军向$k$个城市增兵，那么他们会各自选择一条道路前往各自的目的地，各自的选择互不影响，大将军希望知道的是，不论敌军的路线怎么选，有多少个城市是所有$k$路大军的必经之地，首都一定是）。

#### 输入格式

​	第一行，包含两个整数：$n \; m \; q$，表示敌军城市数、路数和情报数。

​	接下来$m$行，每行包含两个整数：$u \; v $，表示从$u$ 到$v$包含一条单向道路。

​	接下来$q$行，每行包含一些整数：$k \; u_1 \; u_2 \; \dots u_k$，表示敌军会向$u_1 \dots u_k$这$k$个城市派遣大军。

#### 输出格式

​	对于每个询问，输出一行包含一个整数表示必经的城市数。

#### 样例

输入数据：

> 4 3 2
>
> 1 2
>
> 2 3
>
> 2 4
>
> 2 3 4
>
> 2 2 4

输出数据：

> 2
>
> 2

两个询问的必经点为：1, 2

输入数据：

> 4 4 1
>
> 1 2
>
> 1 3
>
> 2 4
>
> 3 4
>
> 1 4

输出数据：

> 2

询问的必经点为：1 4

#### 数据范围

对于$10\%$的数据，$1 \leq n \leq 7，$$1 \leq m \leq 10$，$1 \leq q \leq 100$；

对于$40\%$的数据，$1 \leq n \leq 50000$，$m = n - 1$，$1 \leq q \leq 100000$ ；

对于$100\%$的数据，$1 \leq n \leq 50000$，$1 \leq m \leq 100000$，$1 \leq q \leq 100000$，$\sum k \leq 100000$ 。



## reverse

#### 题目描述

​	夏荷在和冬雪玩游戏。

​	如果一个字符串$s$可以通过下面两个操作转换到$t$（也可以不操作），则称$s$到$t$是可达的，记作$s \sim t$。

- 操作一：在当前字符串后面加一个'A'；
- 操作二：将当前字符串反转（比如"AABAB"反转后变成了"BABAA"），然后在后面加一个'B'；

​	夏荷给了冬雪两个由'A'和'B'字符串：$a \; b$，问冬雪是否存在一个字符串$c$，使得$c \sim a $并且$c \sim b$。如果有多个$c$满足条件，选择最长的，如果还有多个，选择字典序最小的，并输出$c$，如果不存在，输出$-1$。



#### 输入格式

​	第一行包含一个整数：$T$，表示数据组数。

​	接下来$T$行，每行包含两个字符串：$a \; b$。

#### 输出格式

​	对于每组数据，如果存在$c$，输出最长的情况下字典序最大的$c$，否则输出$-1$。

#### 样例

输入数据：

> 3
>
> AB BA
>
> ABA BAB
>
> AB ABAA

输出数据：

> -1
>
> AB
>
> AB

对于第一组数据，不存在这样的$c$。

对于第二组数据，AB以通过第一种操作到ABA，AB可以通过第二种操作到BAB。

对于第三组数据，AB不需要操作即可得到AB，AB进行两次第二种操作即可得到ABAA，并且AB是长度最长的字典序最小的满足条件的$c$。



#### 数据范围

- 对于$10\%$的数据，$1 \leq \mid a \mid < \mid b \mid \leq 6 $；
- 对于$30\%$的数据，$1 \leq \mid a \mid < \mid b \mid \leq 12 $
- 对于$100\%$的数据，$1 \leq \mid a \mid < \mid b \mid \leq 1000$，$1 \leq T \leq 20$, 保证$a,b$都是由A,B字符组成。

## tree

#### 题目描述

​	昆阳在给夏荷出题，题目是这样的：

	> 给你一棵包含$n$个点的无根树，点的标号是$1 \dots n$，在$t = 1$时（$t$表示时间），冬雪在$1$号点，接下来，冬雪会随机跑到当前点相邻的点，然后继续这个过程，直到冬雪访问了所有的点，已知从一个点到另一个点需要的时间是1秒，那么问题来了，请问在这个随机过程中，对于每个节点$u$，冬雪第一次访问$u$的期望时间是多少？

​	夏荷敲了半天呆脑袋，还是没想出来，于是向聪明的你求助来啦！

#### 输入格式

​	第一行包含一个数：$n$表示树的节点数。

​	接下来$n-1$行，每行包含两个数：$u \; v$表示无根树的一条边。

#### 输出格式

​	输出$n$行，第$i$行包含一个浮点数，保留三位小数，表示第$i$号点第一次访问的期望时间。

#### 样例

输入数据：

> 3
>
> 1 2 
>
> 2 3

输出数据：

> 1.000
>
> 2.000
>
> 5.000

样例解释：容易分析出，所有可能情况下，到达1号点和2号店的时间都分别是：1和2，我们考虑3号点的到达时间，所有可能的过程：$12(12)^*3$，表示先到1号店，再到2号点，然后重复任意次1、 2（可以是0次），最后到达3.对于$12(12)^i3$这个具体过程来说（表示中间经过i次1、2），到达3号点的时间是$t_i = 2(i+1)+1$，这个随机过程的概率是$p_i = (\frac{1}{2})^{(i + 1)}$，期望的时间是$E(u=3) = \sum_{i = 0}^{\infty}t_ip_i = 5$，故到达3号点的期望时刻为5.

#### 数据范围

- 对于$ 20 \%$的数据，$1 \leq n \leq 10$，保证每个点的度不超过$2$；
- 另外对于$20\%$的数据，$1 \leq n \leq 10^5$，保证每个点的度不超过2；
- 对于另外$20\%$的数据，$1 \leq n \leq 100$ ；
- 对于$100\%$的数据，$1 \leq n \leq 10^5$。
