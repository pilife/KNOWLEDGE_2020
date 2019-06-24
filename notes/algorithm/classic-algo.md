## 缓存替换算法

### LRU：

- 操作

  - save(key, value)：将key移动到表头，删除溢出的key
  - get(key)：获取key对应的value，将key移动到表头

- 实现：

  - DoubleLinkedList（*删除尾节点需要反向*） + HashMap实现快速的存储和查询
  - 预设哨兵head,tail进行操作统一以及边界情况预防（重复访问）

  #### Redis中实现：

  由于每个redis对象增加两个指针（链表）的空间代价太高。redis增加了24bit的空间存储unix时间戳

  如何确定访问间隔最长的Key？

  使用随机算法，找出N个Key，淘汰其中间隔时间最长的。

  

