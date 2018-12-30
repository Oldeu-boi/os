# 实验二	进程创建与管道通信
##1	实验描述
## 2	实验过程描述
### 2.1	进程间并发关系
我们发现，题目要求中所说的“创建两个子进程”是无法直接通过使用两次```fork()```函数直接得到的。```fork()```函数将当前环境中的变量复制给另外一个进程，同时，其下方的代码块会被父进程和子进程执行。这就带来一个问题：首先执行的的```fork()```函数生成的两个子进程均会执行下方的```fork()```函数，这样就会导致无论是父进程或子进程都生成了自己的子进程，也就是共有四个进程。

为了避免这种情况发生，我们应该考虑进程函数```fork()```的使用位置：应该在子进程执行期间再使用```fork()```函数，避免父进程再生成子进程。给予这样的考虑，我们有如下代码实现，其执行结果也一并附上。

----------
代码2-1	使用```fork()```函数进行两个子进程的创建
```c

```

代码2-1 结束
----------

其运行结果如下所示：

----------
代码2-1-1	使用```fork()```函数进行子进程创建运行结果
```
```
代码2-1-1	结束
----------