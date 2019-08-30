## 缓存替换算法

### LRU：

- 操作

  - save(key, value)：将key移动到表头，删除溢出的key
  - get(key)：获取key对应的value，将key移动到表头

- 实现：

  - HashMap实现快速的存储和查询 + Entry组成双向链表（*删除尾节点需要反向*） 
  - Map的Entry中保存key和value,  存key是因为map删除entry，需要key对应entry的index
- 预设哨兵head,tail进行操作统一以及边界情况预防（重复访问）
  - 在LinkedHashMap中重写`removeEldestEntry`方法即可（删除的条件 size() > MAXSIZE）

  #### Redis中实现：

  由于每个redis对象增加两个指针（链表）的空间代价太高。redis增加了24bit的空间存储unix时间戳

  如何确定访问间隔最长的Key？

  使用随机算法，找出N个Key，淘汰其中间隔时间最长的。
  
  



## 排序算法

![img](../../images/algorithm/sort-01.png)

选择排序：

冒泡排序：

插入排序：

归并排序：

快速排序：

堆排序：

基数排序：

桶排序：

鸽巢排序：



> Reference:
>
>  https://www.cnblogs.com/onepixel/p/7674659.html



## 加密算法

#### 编码算法：

- Base64（6bit -> 8bit）

  即选出64个字符作为基本字符集，转换成这个字符集中的字符

  - 第一步，将每三个字节作为一组，一共是24个二进制位。
  - 第二步，将这24个二进制位分为四组，每个组有6个二进制位。
  - 第三步，在每组前面加两个00，扩展成32个二进制位，即四个字节。
  - 第四步，根据字符集，得到扩展后的每个字节的对应符号，这就是Base64的编码值。

#### 摘要算法：

- MD5
- Murmur

#### 非对称加密：

- RSA

