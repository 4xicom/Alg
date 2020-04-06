.第一部分 #

##UnionFind 

要点： path compression 可以做weighted balance Union 这样复杂度就是log*V
```
find（n）
if parent(n) != n
parent(n) = find(parent(n));
```

##排序

要点 注意 quick的实现 和 kth element partition

要点 凡是sort的时候 都想一想可不可以radix sort

算法|最好|平均|最差|空间|稳定
:---|:---|:---|:---|:---|:---
bubble| N^2|
selection|
insert|
shell|
merge|
quick|
3-quick|
heap|
(Radix)|
LSD|
MSD|
3WayMSD|

##PQ 
技巧（可以indexPQ）这样就组合成一个类似于mapPQ的东西，还可以修改里面的值，swim up down
但是实现起来比较复杂。

##Hash 没啥好说的。找好哈希函数

##BST

要点可以用作line sweep 

扩展： 

Interval search Tree

存start 做key， 每个node里面都存子树里面的最大的end是多少，这个可以做2D line sweep

扩展：

线段树 

可以用类似于堆来实现。不用考虑树的完整性，最后会循环回同一层。 做查询时，分清目前是左子还是右子树。
适合最大最小。 取和非特例，用一个Array 存目前为止的和更简单。

扩展：
红黑树 

B-树
对应disk IO，每次读取一个block，每个节点有K-1个数据，K个孩子。K的大小由block大小决定。

B+ B* 树
在非叶子节点不存数据，只存key，这样一次读取的block中包含的key数量大增。 叶子节点间加link便于循环，存入最大最小值在索引中便于分支。
B* 在非叶子节点加入link到邻居，可以邻居间平衡，减少分裂次数。


第二部分

无向图
BFS DFS connected（UF)
有向图
BFS DFS 
DAG有向无环图
Topological Sort（DFS)（找环）
Strong Component（先反图，toposort，然后再dfs）

MST 问题 最小扩展树
Kuskal 算法 greedy on edge
如何判定边的两侧是否已经联通，用UF。
Prim 算法 
Lazy模式
用PQ存入节点（同一个节点可能被存入多次，每个边都存）
Agressive
用PQ存V，每次新加入节点后Update PQ中的节点（这个需要IndexPQ）

最短路径问题
Dijkstra 算法 跟 Prim算法一样
用PQ 存V （lazy模式，agreesive 模式）
如果图是DAG有向无环图。
那么topo sort 然后按顺序来就完了，可以处理负的权重。
最后如果都不是，还有负的权重，
Bellman-ford算法，就是DFS 算V遍。如果V遍以后还有update，说明有负圈。

MaxFlow-MinCut 问题
Ford-Fulkerson 算法，找增广序列。找到了就更新继续找。
二分图的最大匹配问题就是同一个问题。
匈牙利算法就是Ford-fulkerson算法的权值为一的特殊情况。

字符串处理
LSD MSD 3Way Radix Qsort （这个可以nlogn）

Trie树 复杂度表
红黑树  
哈希表
R-Trie
3-Trie 
(BST 组合Trie，） 
还有其他的comination比如 前面两个字符 单阶 Trie，后面 3-Trie

串匹配
KMP算法
就是子串里找prefix
int i=0, j=1;i,j<n;

if s(i) == s(j) 
   i++;
   lnp \[j] = i;
   j++;
else
   if i ==0 
      j++
   else
      i = lnp \[i-1]
比较的时候也是一样
Boyer-Moore 这个反着比，跳过。序列不好计算。
Rabin-Karp  算哈希  
重点：凡是字符串匹配都考虑一下 Rabin-Karp

线性编程
Simplex 算法。很烦。解方程。















