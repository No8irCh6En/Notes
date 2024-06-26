# Part 0 绪论

进程

抽象化的方法

Router

数据结构的内容：如何存储？如何运算？

## 数据的逻辑结构

**集合结构**：同类而无序。

**线性结构**：线性有序。除去头尾，既有前驱，也有后继。

**树形结构**：如树、堆等。除去根外，所有节点仅一个前驱，可有多个后继。

**图状结构**：前驱后继数目不限。

通常有的操作为：创建、释放、更新、查找等。

存储节点、方式、附加信息。

## 关系的存储

**顺序存储** 数组等

**链接存储** 指针 链表等

**哈希存储** 集合结构的存储

**索引存储** 所有节点存储在存储区。另外设置索引区域表示不同节点之间的关系。

## 运算的实现

运算对应算法。而算法对应一个函数。

## 算法的质量

正确性、鲁棒性、易读性、高效性。

时间性能、空间性能。

最坏情况的时间复杂度。

空间需求，分为存储被处理数据的空间，以及实现操作所需的**额外**空间。

空间性能关注的是**额外**引入的空间量。

算法运算量的计算：引入标准操作。确定算法在给定条件下所需的标准操作数。

用渐进表示法表示时间复杂度：考虑问题规模很大的时候，运行时间随问题规模的变化规律。只考虑数量级。

四种描述方法：

$$
大O,大\Omega，大\Theta，小o
$$

分别表示：上界、下界、相等、严格下界。

多项式时间复杂度以及指数时间复杂度。

### 时间复杂度的计算

求和定理：若$P$由$P_1,P_2$组成，两部分的时间复杂度分别为$O(f(n)),O(g(n))$，则$P$的时间复杂度为$O(\max(f(x),g(x))$

求积定理：比较显然。循环等计算时会用到。

## 算法的优化

## 空间复杂度

# 数据结构的实现

过程化程序设计 or OOP？

OOP，模板

# Part I 线性表

## 线性表的定义

基类尽量都要定义虚析构函数。

## 线性表的实现

常用顺序实现或链接实现。

当插入删除次数较少的时候，倾向于顺序实现。

# Part II 栈

括号配对时仅进行词法检查，不会执行语法检查。

可使用栈进行将递归程序转化为非递归程序。

使用文件流对象可以提高效率，避免多次的打开和关闭文件。

main函数可以有参数。第一个参数是int， argc；第二个参数是 char**。

后缀表达式：运算符在两个运算对象之后。

中缀表达式和后缀表达式中，运算数的顺序相同。

倘若要做一个四则运算计算器，那么我可以将表达式边转换边进行计算。

此外，需要注意空格、数字可能有多位等情况。

CPU内分成了多个时间片。处理任务时进程会排成一个队列。

## 队列

队头队尾标记，数组规模

判断队列中是否有剩余的空间。

链表存储时，表头作为队头。

模拟：事件驱动和时间驱动的模拟。如排队系统，就是事件驱动的模拟。

# Part II 树

节点只有一个父亲，可以有很多个儿子。

一个节点的儿子数目称为这个节点的度。一棵树上节点度的最大值，称为这棵树的度。

满二叉树：除去最底层，任意一层的节点都都有两个儿子。

关于二叉树的一个不是很显然的结论：叶子结点的度数等于度数为2的节点数加1。

$$
n=n_0+n_1+n_2\\
B=n-1\\
B=n_1+2n_2
$$

故得之。

二叉树的遍历方式有前序遍历，中序遍历，后序遍历三种方式。

e.g.可以使用后序遍历计算斐波那契数列；用前序遍历进行快速排序。

通过前序遍历和中序遍历，可以唯一确定一棵二叉树。

顺序实现：通过位置关系决定逻辑关系。

链接实现：位置随意。通过指针来表示逻辑关系。

## 优先级队列

二叉堆

堆是一棵完全二叉树。

插入操作的复杂的最坏是对数的，最好情况下是常数。

出堆操作，倘若将最下层的元素移至最上层，则显然为了满足有序性，复杂度为对数级别。

在建堆时，最坏情况是$\Theta(N\log N)$ ，平均情况为线性的。

左堆可归并，是因为其不严格要求完全二叉树。（左偏树）

斜堆可以看做是自平衡的左偏树。

二项堆可以看做是二项树的集合。

如果要归并二项堆，直接同位相加即可。

## 二叉树

使用非递归方式先根遍历二叉树，可以使用栈。

使用非递归方式中根遍历二叉树，在入栈过程时，需要暂存根节点内容。增加一个计数器，统计根出栈的次数。只有出栈次数达到2，才是真正的出栈。

若欲后根遍历，当出栈次数达到3，方为真正的出栈。

### 表达式树

使用后序遍历的方式，可以计算出表达式树的值。

### Huffman树

Huffman树需要存储父亲节点。是故，我们应当选择三叉链表进行存储。通常采用归并的方法进行建树。

## 森林

如何把森林转化为二叉树？

首先，把每一颗树转化为二叉树。然后自根节点向右，把树分开来。把树转化为二叉树，可以通过儿子兄弟表示法进行化归。把新二叉树的右儿子表示原先的兄弟，而左儿子表示原先最左边的儿子。

# 集合

## 静态查找表

## 动态查找表

## 平衡树

红黑树：如果删除的节点是红色的，那么我们直接删除就可以了。如果只有一个儿子的节点，那么它一定是黑节点，我们只需要把其儿子修改为黑色，在提上来就可以了。如果是黑色的叶节点，那么我们需要比较复杂的调整。

如果一个子树上少了一个黑节点，那么我们应当想办法调整这一点。如果被调整节点的兄弟是红色的，那么我们可以对父节点进行旋转，但是被调整节点路径上还是少一个黑节点。

自底向上的调整可能一路回溯到根节点。

自顶向下的删除：把正在调整的节点调整为红色或者只有一个红节点。
