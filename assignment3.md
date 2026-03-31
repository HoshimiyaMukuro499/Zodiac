# Assignment #3: 20260311 cs201 Mock Exam

*Updated 2026-03-11 15:24 GMT+8*
 *Compiled by <mark>***,生命科学学院</mark> (2026 Spring)*



**作业的各项评分细则及对应的得分**

| 标准                                 | 等级                                                         | 得分 |
| ------------------------------------ | ------------------------------------------------------------ | ---- |
| 按时提交                             | 完全按时提交：1分<br/>提交有请假说明：0.5分<br/>未提交：0分  | 1 分 |
| 源码、耗时（可选）、解题思路（可选） | 提交了4个或更多题目且包含所有必要信息：1分<br/>提交了2个或以上题目但不足4个：0.5分<br/>少于2个：0分 | 1 分 |
| AC代码截图                           | 提交了4个或更多题目且包含所有必要信息：1分<br/>提交了2个或以上题目但不足4个：0.5分<br/>少于：0分 | 1 分 |
| 清晰头像、PDF文件、MD/DOC附件        | 包含清晰的Canvas头像、PDF文件以及MD或DOC格式的附件：1分<br/>缺少上述三项中的任意一项：0.5分<br/>缺失两项或以上：0分 | 1 分 |
| 学习总结和个人收获                   | 提交了学习总结和个人收获：1分<br/>未提交学习总结或内容不详：0分 | 1 分 |
| 总得分： 5                           | 总分满分：5分                                                |      |
>
>
>
>**说明：**
>
>1. **解题与记录：**
>
>      对于每一个题目，请提供其解题思路（可选），并附上使用Python或C++编写的源代码（确保已在OpenJudge， Codeforces，LeetCode等平台上获得Accepted）。请将这些信息连同显示“Accepted”的截图一起填写到下方的作业模板中。（推荐使用Typora https://typoraio.cn 进行编辑，当然你也可以选择Word。）无论题目是否已通过，请标明每个题目大致花费的时间。
>
>2. **课程平台：**课程网站位于Canvas平台（https://pku.instructure.com ）。该平台将在<mark>第2周</mark>选课结束后正式启用。在平台启用前，请先完成作业并将作业妥善保存。待Canvas平台激活后，再上传你的作业。
>
>3. **提交安排：**提交时，请首先上传PDF格式的文件，并将.md或.doc格式的文件作为附件上传至右侧的“作业评论”区。确保你的Canvas账户有一个清晰可见的本人头像，提交的文件为PDF格式，并且“作业评论”区包含上传的.md或.doc附件。
>3. **延迟提交：**如果你预计无法在截止日期前提交作业，请提前告知具体原因。这有助于我们了解情况并可能为你提供适当的延期或其他帮助。  
>
>请按照上述指导认真准备和提交作业，以保证顺利完成课程要求。



## 1. 题目

### E20742:泰波拿契數

implementation, http://cs101.openjudge.cn/practice/20742/

思路：



代码：

```python
n=int(input().strip())  
ls=[0]*(n+1)  
ls[0],ls[1],ls[2]=0,1,1  
for i in range(3,n+1):  
    ls[i]=ls[i-1]+ls[i-2]+ls[i-3]  
print(ls[-1])
```



代码运行截图 <mark>（至少包含有"Accepted"）</mark>
![[Pasted image 20260326101539.png]]

![[Pasted image 20260326101548.png]]


### E30571.十进制整数的反码

bit manipulation, http://cs101.openjudge.cn/practice/E30571/


思路：
解法不太漂亮


代码：

```python
N=int(input().strip())  
length=N.bit_length()  
if N==0:  
    res= 1  
else:  
    mask=(1<<length)-1  
    res=mask-N  
print(res)
```



代码运行截图 <mark>（至少包含有"Accepted"）</mark>

![[Pasted image 20260326102744.png]]
![[Pasted image 20260326102916.png]]


### E29950:稳定的符文序列

two pointers, http://cs101.openjudge.cn/practice/E29950



思路：
我的代码还是不漂亮


代码：

```python
def main():  
    from collections import defaultdict  
    s=input().strip()  
    u=len(s)  
    i,j=0,0  
    occur=defaultdict(int)  
    length=0  
    res=0  
    for j in range(u):  
        if occur[s[j]]==0:  
            occur[s[j]]+=1  
            length+=1  
            res=max(res,length)  
        else:  
            while occur[s[j]]!=0:  
                if i>j:  
                    break  
                else:  
                    occur[s[i]]-=1  
                    length-=1  
                    i+=1  
                    if occur[s[j]]==0:  
                        occur[s[j]]+=1  
                        length+=1  
                        res=max(res,length)  
                        break  
    print(res)  
if __name__=='__main__':  
    main()
```



代码运行截图 <mark>（至少包含有"Accepted"）</mark>
![[Pasted image 20260326104655.png]]
![[Pasted image 20260326104704.png]]

### M30218:狭路相逢

stack, http://cs101.openjudge.cn/practice/M30218/



思路：
bur为啥错了啊
不能理解
原来可以连击combo!

代码：

```python
N=int(input().strip())  
ls=list(map(int,input().strip().split()))  
res=[]  
for i in range(N):  
    if ls[i]>0:  
        res.append(ls[i])  
    else:  
        if not res:  
            res.append(ls[i])  
        else:  
            if res[-1]<0:  
                res.append(ls[i])  
            else:  
                while ls[i]<0:  
                    warrior=res.pop()  
                    if warrior+ls[i]>0:  
                        warrior+=ls[i]  
                        res.append(warrior)  
                        break  
                    elif warrior+ls[i]==0:  
                        break  
                    else:  
                        ls[i]+=warrior  
                        if not res or res[-1]<0:  
                            res.append(ls[i])  
                            break  
  
print(len(res))  
print(*res)
```



代码运行截图 <mark>（至少包含有"Accepted"）</mark>


![[Pasted image 20260326112054.png]]
![[Pasted image 20260326110933.png]]
![[Pasted image 20260326112109.png]]

### M02299: Ultra-QuickSort

merge sort, http://cs101.openjudge.cn/practice/02299/

思路：
大胆猜想：交换次数为t(逆序数)
匆匆忙忙连滚带爬

代码：

```python
class FenwickTree:  
    def __init__(self,size):  
        self.tree=[0]*(size+1)  
    def update(self,i,delta):  
        while i<len(self.tree):  
            self.tree[i]+=delta  
            i+=i&(-i)  
    def query(self,i):  
        s=0  
        while i>0:  
            s+=self.tree[i]  
            i-=i&(-i)  
        return s  
  
while True:  
    n=int(input().strip())  
    if n==0:  
        break  
    else:  
        ls=[]  
        for i in range(n):  
            ls.append(int(input().strip()))  
    inv=0  
    tree=FenwickTree(max(ls)+1)  
    for i,num in enumerate(ls):  
        tree.update(num+1,1)  
        inv+=i+1-tree.query(num+1)  
  
  
    print(inv)
```



代码运行截图 <mark>（至少包含有"Accepted"）</mark>

![[Pasted image 20260326114629.png]]

![[Pasted image 20260326114847.png]]

<font color='skyblue'>结论：冒泡排序的交换次数为逆序对的个数</font>
### <font color='skyblue'>定义</font>

设序列 `a[1..n]`，定义函数 `f(a) = |{(i,j): i < j 且 a[i] > a[j]}|`

### 性质1

相邻交换 `swap(i, i+1)` 时：

- 如果 `a[i] > a[i+1]`，则 `f` 减少1
    
- 如果 `a[i] < a[i+1]`，则 `f` 增加1
    

### 性质2

排序完成时 `f = 0`

### 性质3

对于任意序列，存在一个相邻交换序列，每次交换都减少 f，直到 f=0

### M29954:逃离紫罗兰监狱

bfs, http://cs101.openjudge.cn/practice/29954 

思路：



代码：
version1--MLE 时间复杂度：$$O(R \times C \times K)$$
```python
from collections import deque  
R,C,K=map(int,input().strip().split())  
maze=[]  
for i in range(R):  
    maze.append(input().strip())  
initial=(0,0)  
for i in range(R):  
    for j in range(C):  
        if maze[i][j]=='S':  
            initial=(i,j)  
directions=[(1,0),(-1,0),(0,1),(0,-1)]  
queue=deque()  
queue.append((initial,K,0))  
res=0  
visited=set()  
visited.add(initial)  
while queue:  
    curr_pos,k_now,step=queue.popleft()  
    visited.add(curr_pos)  
    for dx,dy in directions:  
        nx=curr_pos[0]+dx  
        ny=curr_pos[1]+dy  
        nstep=step+1  
        if 0<=nx<R and 0<=ny<C and (nx,ny) not in visited:  
            if maze[nx][ny]=='.':  
                queue.append(((nx,ny),k_now,nstep))  
            elif maze[nx][ny]=='#':  
                queue.append(((nx,ny),k_now-1,nstep))  
            elif maze[nx][ny]=='E':  
                res=nstep  
    if res:  
        print(res)  
        break
```
MLE原因：每个节点都由于K的不同可以被经过K次，但是不是这K次经过都是有意义的。
什么“经过”是有意义的呢？**使得K比原来更多的经过是有意义的。由于第2~n次踏步在queue中位置更加靠后，step上本来就不占优势。step只会更大或不变。如果一个踏步step更大、K更小，就没有必要再进行后续的尝试了。**
而且，使用max_K检验还可以包含visited的功能--如果再一次踏足这一格（max_K在这一格已经有一个值）却不能带来更高的K保留，那么这一步是没有意义的。
空间复杂度降低为$$ O(R \times C) $$
version 2(revised ver.)
```python
from collections import deque  
R,C,K=map(int,input().strip().split())  
maze=[]  
for i in range(R):  
    maze.append(input().strip())  
  
  
sx,sy=0,0  
for i in range(R):  
    for j in range(C):  
        if maze[i][j]=='S':  
            sx,sy=i,j  
  
max_k=[[-1]*C for _ in range(R)]  
  
directions=[(1,0),(-1,0),(0,1),(0,-1)]  
queue=deque()  
queue.append((sx,sy,K,0))  
res=0  
  
while queue:  
    x,y,k,step=queue.popleft()  
  
    for dx,dy in directions:  
        nx=x+dx  
        ny=y+dy  
        nstep=step+1  
        if 0<=nx<R and 0<=ny<C :  
            if maze[nx][ny]=='E':  
                print(step+1)  
                exit()#直接退出整个程序  
  
            if maze[nx][ny]=='.' and k>max_k[nx][ny]:  
                max_k[nx][ny]=k  
                queue.append((nx,ny,k,step+1))  
            elif maze[nx][ny]=='#' and k-1>max_k[nx][ny]:  
                max_k[nx][ny]=k-1  
                queue.append((nx,ny,k-1,step+1))  
  
print(-1)#应该不会执行
```


同时，将DrZ©的解法叙述如下：
我们可以建立三个$R \times C$的矩阵，分别存储迷宫、到达该点的最小步数、到达该点的最大K。之后以上下左右的方向进行更新 $step=\min(dp[↑,↓,←,→])$$K=\max(dp[↑,↓,←,→])$ 进行4R×C次更新，也可以解决。


代码运行截图 <mark>（至少包含有"Accepted"）</mark>

![[Pasted image 20260326130900.png]]



## 2. 学习总结和个人收获

<mark>如果发现作业题目相对简单，有否寻找额外的练习题目，如“数算2025spring每日选做”、LeetCode、Codeforces、洛谷等网站上的题目。</mark>
AC5 这次考试题整体上来说还是十分温和。
第五题猜到了逆序数，转化为了上次作业数字华容道的已知问题。Merge排序应该是会超内存。
第六题对于内存有限制，因此要注意合适的剪枝方式。




