### 一.杭电OJ刷题分类
#### 主流算法
1.搜索（回溯） 2.DP（动态规划）3.贪心 4.图论（Dijkstra、最小生成树、网络流) 5.数论 6.计算几何 7.组合数学  8.模拟 9.数据结构 10.博弈论

手把手撕LeetCode题目，扒各种算法套路的裤子
https://github.com/labuladong/fucking-algorithm

#### 递归与分治 
- 特点：子问题相互独立
- 求解阶段：1.划分(尽量规模相等) 2.求解子问题(**递归解决**) 3.合并
- 递归的运行过程分析
##### >排序问题的分治法
B1066 简单分治法
B1067 根下2的近似解 (给定一个定义在[L, R]上的单调函数f(x), 求方程f(x)=0的根)
B1068 快排(数列接近有序) 此时最坏的时间复杂度为O(n^2), 原因是主元没有把当前区间划分为两个长度接近的子区间。 
B1069 快排 
##### >组合问题的分治法
B1090 最大子段和  ->动态规划算法 ->回溯法
B1091 棋盘覆盖    
B1092 循环赛日程安排
##### >几何问题的分治法
B1100 最近点  
B1101 凸包
##### 武理原题
B1102 递归求n的x次幂
B1103 快排，考虑基本有序
B1104 非递归改递归
B1105 用递归求解f(n)=f(n-1)+f(n-2) n>2 n=1时f(n)=1 n=2时f(n)=1
##### 课后习题
B1120 分治法求一个数组中最大元素的位置
B1121 递归求多项式$A(x)=a_nx^n+a_(n-1)x^(n-1)------a_0x^0$ 的值
B1122 一个序列中出现次数最多的元素为众数，分治法寻找众数
B1123 搜索二维矩阵     未完成

#### 减治法
把一个大问题划分为若干子问题，但这些子问题不需要分别求解， 只需求解其中的一个子问题，也无需对子问题进行合并
利用原问题与较小规模子问题解之间的关系:
- 原问题的解存在于其中较小规模的子问题中
- 原问题的解与较小规模的解之间存在某种对应关系
##### >查找问题的减治法

##### >排序问题的减治法
B1209 堆排序   //插入法调整堆
B1210 n个元素寻找第k小元素
##### >组合问题的减治法

#### 动态规划(DP) 
使用动态规划的条件：
- 优化子结构
如果一个问题的最优解可以由其**子问题的最优解**有效的构造出来，我们说这个问题具有优化子结构
最优子结构保证了动态规划中原问题的最优解可以由子问题的最优解推导出来
优化子结构使我们能自下而上地完成求解过程
- 重叠子问题
在问题的求解过程中，很多子问题的解将被多次使用

动态规划用一个表来记录所有已经解决的子问题的答案，而最优子结构保证了算出来的子问题的答案可以被再次用到
递归的定义最优值
自底向上的方式计算出最优值
根据计算最优值时得到的信息构造最优解

应用动态规划算法一般分为3个阶段：
重点：先假设整体最优解，再找子问题，然后通过子问题构造原问题最优解
1.分段：将原问题分解为若干相互重叠的子问题。**根据问题，定义dp数组,确定dp数组的含义**
2.分析：分析问题是否满足最优性原理，**找出(状态转移函数)动态规划函数的递推式**
3.求解：明确base case,利用递推式自底向上计算，实现动态规划过程
最重要的是：
根据问题定义dp数组，一维或二维，

##### DP经典问题
B1300 走台阶
##### >组合问题
c0001 数塔问题、
c0002 最大连续子序列和、
c0003 最长公共子序列问题
c0004 最长不下降子序列    未写代码
c0005 01背包问题
c0006 编辑距离   未写代码

##### >查找问题
c0006 最优二叉查找树

##### >图问题
c0010 TSP问题            未写代码
c0011 多段图的最短路径    未写代码


#### 贪心
zui'you'jiezuiyoujie法求解的问题，一般具有两个重要的性质：
最优子结构性质和贪心选择性质
>最优子结构性质 同动态规划 
>贪心选择性质
是指问题的整体最优解可以通过一系列局部最优的选择，即贪心选择来得到。
对于一个具体的问题，要确定它是否具有贪心选择性质，必须证明每一步所做的贪心选择最终导致问题的整体最优解
**一般会用到排序和结构体**

##### >GreedySelector经典问题 有：活动安排问题、最优装载、哈夫曼编码、单源最短路径、最小生成树、多机调度问题
B1020 月饼  B1040 区间不相交

##### >图问题
c0020 TSP问题  近似解  未写代码
c0021 图着色问题   近似解  未写代码
c0022 最小生成树

##### >组合问题
c0030 背包问题
c0031 活动安排问题
c0032 多机调度问题   近似解  未写代码

#### 搜索
DFS   BFS
B1080 迷宫   B1081 背包问题（另一种解法DFS）
#### 回溯法(求解目标：找出解空间中满足约束条件的所有解)
##### 经典问题：  (八皇后,骑士走马,处理机调度)
回溯法简介.md
批处理作业调度  n后问题 0-1背包问题 最大团问题 图的m着色问题 旅行售货员问题  圆排列问题
##### 图问题
c0040 图着色  m叉子集树
c0041 哈密顿回路  排列树
##### 组合问题
c0042 n皇后  n叉子集树
c0043 批处理作业调度 排列树（全部遍历）


#### 分支限界法(求解目标：找出满足约束条件的一个解，或是在满足约束条件的解中找出使某一目标函数值达到极大或极小的解，某种意义下的最优解)
##### 经典问题：
分支限界法简介.md







### 二.杂项 
##### 简单模拟 
B1001

##### 图形输出
B1036 （c实现和py实现）

##### 散列

##### 递归与分治
B1002 全排列
##### 记忆化技术

##### 动态链表   静态链表
静态链表的实现原理是hash，即通过建立一个结构体数组，并令数组的下标直接表示结点的地址. 前提：地址范围小
B1070 sharing(静态链表)     B1071 


### 三. 武理复试
#### 文件相关
文件的打开与关闭（fopen()\fclose()）、读取文件指定内容、修改文件指定内容、删除文件指定内容
文件更名与删除rename() remove()、文本文件与二进制文件、流式文件读写、内存映射文件
**文本模式**:  标准I/O函数都是面向文本的，用于处理字符和字符串
**二进制模式**  把数据存储在一个与程序具有相同表示方法的文件中 fread()  fwrite() 比如结构体数组
fread对应二进制打开的方式   fscanf对应文本打开的方式
B0015 文件压缩     B0020 结构体数组存储到文件并读出

#### 进程与线程(linux为例)
进程和线程简介










