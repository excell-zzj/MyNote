# BFS 

---

### 基本思想

​	首先将问题抽象成**图**，然后遍历的时候本质上是用**队列**来实现先进先出的思想。从而达到一层层遍历的目的。其特点就是BFS找到的路径一定是**最短**的，但是相对于DFS，牺牲了空间。

### 算法框架

​		要说框架的话，首先是 BFS 出现的常见场景，**问题的本质就是让你在一幅「图」中找到从起点** **`start`** **到终点** **`target`** **的最近距离，这个例子听起来很枯燥，但是 BFS 算法问题其实都是在干这个事儿**。	

​		这个广义的描述可以有各种变体，比如走迷宫，有的格子是围墙不能走，从起点到终点的最短距离是多少？如果这个迷宫带「传送门」可以瞬间传送呢？

​		再比如说两个单词，要求你通过某些替换，把其中一个变成另一个，每次只能替换一个字符，最少要替换几次？

​		再比如说连连看游戏，两个方块消除的条件不仅仅是图案相同，还得保证两个方块之间的最短连线不能多于两个拐点。你玩连连看，点击两个坐标，游戏是如何判断它俩的最短连线有几个拐点的？

​		这些问题本质上就是一幅「图」，让你从一个起点，走到终点，问最短路径。这就是 BFS 的本质，框架搞清楚了直接默写就好。

~~~c++
// 计算从起点 start 到终点 target 的最近距离
int BFS(Node start, Node target) {
    Queue<Node> q; // 核心数据结构
    Set<Node> visited; // 避免走回头路

    q.offer(start); // 将起点加入队列
    visited.add(start);
    int step = 0; // 记录扩散的步数

    while (q not empty) {
        int sz = q.size();
        /* 将当前队列中的所有节点向四周扩散 */
        for (int i = 0; i < sz; i++) {
            Node cur = q.poll();
            /* 划重点：这里判断是否到达终点 */
            if (cur is target)
                return step;
            /* 将 cur 的相邻节点加入队列 */
            for (Node x : cur.adj())
                if (x not in visited) {
                    q.offer(x);
                    visited.add(x);
                }
        }
        /* 划重点：更新步数在这里 */
        step++;
    }
}
~~~



### 第一个例子——二叉树的最小路径

> 题目：给定一个二叉树，找出其最小深度。
>
> 最小深度是从根节点到最近叶子节点的最短路径上的节点数量。
>
> > 说明: 叶子节点是指没有子节点的节点。
>
> > 示例: 给定二叉树 [3,9,20,null,null,15,7],
>
> ​    3
>
>    / \
>   9  20
>       /  \
>      15   7
> 返回它的最小深度  2.

~~~c++
class Solution {
public:
    int minDepth(TreeNode* root) {
        if(root == NULL){
            return 0;
        }
        queue<TreeNode*> q;
        q.push(root);
        int depth = 1;
        while(!q.empty()){
            int size = q.size();
          // 遍历当前的队列（当前层）
            for(int i = 0; i < size; ++i){
              // 按照最先放进来的顺序(从左往右)
                TreeNode* node = q.front();
                q.pop();
              // 如果到底了，返回深度
                if(node->left == nullptr && node->right == nullptr){
                    return depth;
                }
                if(node->left) q.push(node->left);
                if(node->right) q.push(node->right);
            }
          // 当前层遍历完一遍，深度加一
            depth++;
        }
        return depth;
        
    }
};
~~~

### 例子二———打开转盘锁

> 你有一个带有四个圆形拨轮的转盘锁。每个拨轮都有10个数字： '0', '1', '2', '3', '4', '5', '6', '7', '8', '9' 。每个拨轮可以自由旋转：例如把 '9' 变为  '0'，'0' 变为 '9' 。每次旋转都只能旋转一个拨轮的一位数字。锁的初始数字为 '0000' ，一个代表四个拨轮的数字的字符串。列表 deadends 包含了一组死亡数字，一旦拨轮的数字和列表里的任何一个元素相同，这个锁将会被永久锁定，无法再被旋转。字符串 target 代表可以解锁的数字，你需要给出最小的旋转次数，如果无论如何不能解锁，返回 -1。
>
> > **示例1**：
> >
> > ~~~
> > 输入：deadends = ["0201","0101","0102","1212","2002"], target = "0202"
> > 输出：6
> > ~~~
> >
> > **解释**：
> > 可能的移动序列为 "0000" -> "1000" -> "1100" -> "1200" -> "1201" -> "1202" -> "0202"。
> > 注意 "0000" -> "0001" -> "0002" -> "0102" -> "0202" 这样的序列是不能解锁的，
> > 因为当拨动到 "0102" 时这个锁就会被锁定。
>
> > **示例2**：
> >
> > ~~~
> > 输入: deadends = ["8888"], target = "0009"
> > 输出：1
> > ~~~
> >
> > **解释**：
> > 把最后一位反向旋转一次即可 "0000" -> "0009"。
>
> > **示例3**：
> >
> > ~~~
> > 输入: deadends = ["8887","8889","8878","8898","8788","8988","7888","9888"], 
> > 			target = "8888"
> > 输出：-1
> > ~~~
> >
> > **解释**：
> > 无法旋转到目标数字且不被锁定。
>
> > **示例4**：
> >
> > ```
> > 输入: deadends = ["0000"], target = "8888"
> > 输出：-1
> > ```

* 传统的BFS思路可以很好地在这题上运用，初始状态就是“0000”，然后它每一位都能向上向下拨动，这就产生了8种可能性向下一层遍历。然后以这8个密码为基础，再向下继续各找8个，这样就能遍历所有的密码组合，直道找到目标。

* 但是上述暴力有两个问题：
  1. 题目里要求有`deadends`限制，因此，不是所有的8个密码都是符合要求的，
  2. 会有很多重复，比如“0000”到“1000”的时候“1000”也会搜索一遍“0000”

* 对这两个问题也很好解决：
  1. 在遍历每一个8种情况的时候，如果在deadends，那么直接跳过
  2. 创建一个visited数组，将遍历过的加入，如果visited数组里有当前即将到达的组合，那么也跳过

于是就有下面的代码：

~~~c++
class Solution {
public:
    string plusOne(string str, int j){
        if(str[j] == '9'){
            str[j] = '0';
        }else{
            str[j] += 1;
        }
        return str;
    }
    string minusOne(string str, int j){
        if(str[j] == '0'){
            str[j] = '9';
        }else{
            str[j] -= 1;
        }
        return str;
    }
    int openLock(vector<string>& deadends, string target) {
        unordered_set<string> deadset(deadends.begin(), deadends.end());
        unordered_set<string> visited;
        queue<string> q;
        q.push("0000");
        visited.insert("0000");
        int step = 0;
        while(!q.empty()){
            int size = q.size();
            for(int i = 0; i < size; ++i){
                string cur = q.front();
                q.pop();
                if(deadset.find(cur) != deadset.end()){
                   continue;
                }
                if(cur == target){
                    return step;
                }
                for(int j = 0; j < 4; ++j){
                    string up = plusOne(cur, j);
                    if(!visited.count(up)){
                        q.push(up);
                        visited.insert(up);
                    }
                    string down = minusOne(cur, j);
                    if(!visited.count(down)){
                        q.push(down);
                        visited.insert(down);
                    }
                }
            }
            ++step;
        }
        return -1;
     }
 };
~~~

### 双向BFS

**但是，这样还是不够优化，于是就想到了双向BFS**

**传统的 BFS 框架就是从起点开始向四周扩散，遇到终点时停止；而双向 BFS 则是从起点和终点同时开始扩散，当两边有交集的时候停止**。

![img](https://gblobscdn.gitbook.com/assets%2F-LrtQOWSnDdXhp3kYN4k%2Fsync%2F96d7b1ab7db024a1831170c128f5dcacfb68abb8.jpeg?alt=media)

![img](https://gblobscdn.gitbook.com/assets%2F-LrtQOWSnDdXhp3kYN4k%2Fsync%2F946f50b8251df56bfaa1d60a133affd736e4ebb3.jpeg?alt=media)

​		图示中的树形结构，如果终点在最底部，按照传统 BFS 算法的策略，会把整棵树的节点都搜索一遍，最后找到 `target`；而双向 BFS 其实只遍历了半棵树就出现了交集，也就是找到了最短距离。从这个例子可以直观地感受到，双向 BFS 是要比传统 BFS 高效的。

​		**不过，双向 BFS 也有局限，因为你必须知道终点在哪里**。比如我们刚才讨论的二叉树最小高度的问题，你一开始根本就不知道终点在哪里，也就无法使用双向 BFS；但是第二个密码锁的问题，是可以使用双向 BFS 算法来提高效率的，代码稍加修改即可：

~~~c++
int openLock(vector<string>& deadends, string target) {
        unordered_set<string> deadset(deadends.begin(), deadends.end());
        unordered_set<string> visited;
        unordered_set<string> q1;
        unordered_set<string> q2;

        int step = 0;
        q1.insert("0000");
        q2.insert(target);

        while(!q1.empty() && !q2.empty()){
            unordered_set<string> tmp;
            for(string str : q1){
                if(deadset.find(str) != deadset.end()){
                    continue;
                }
                if(q2.find(str) != q2.end()){
                    return step;
                }
                for(int i = 0; i < 4; ++i){
                    string up = plusOne(str, i);
                    if(!visited.count(up)){
                        tmp.insert(up);
                    }
                    string down = minusOne(str, i);
                    if(!visited.count(down)){
                        tmp.insert(down);
                    }
                }
            }
            ++step;

            q1 = q2;
            q2 = tmp;
        }
        return -1;
    }
~~~

