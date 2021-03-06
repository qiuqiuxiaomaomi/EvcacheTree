# EvcacheTree
Evcache技术研究

![](https://i.imgur.com/wIReHIW.png)

<pre>
Evcache
 
          基于云服务的分布式缓存系统
          AWS云服务于分布式缓存服务系统相结合就产生了一些杰出的技术方案，一个典型案例是NetFlix
      的Evcache， Evcache是一个开源的，快速的分布式缓存，基于Memcached的内存存储和Spymemcached
      客户端实现的解决方案，主要用在亚马逊弹性计算云服务器的基础设置上，为云计算做了优化，能够顺畅
      而高效的提供数据层服务。

      Evcache是一个缩写，包括:Ephemeral：数据存储是短暂的，有自身的存活时间。
                            Votatile:数据可以再任何时候消失
                            Cache：一个内存性的键值对存储系统

      Evcache实现的主要功能呢包括分布式键值对存储，AWS的跨区域数据复制以及注册和启动发现新节点或
      新服务。Evcache典型的应用是对上下文一致性要求不高的场景，其可扩展性已经可以处理非常大的流量，
      同时提供了健壮的API.

      EVCache在Netflix内部是一个被广泛使用的数据缓存服务，所提供的低延迟且高可用的缓存方案可以很好
      地满足Netflix微服务架构需要，也用来做一般数据的存储。EVCache 能够使面向终端用户的应用，个性化
      算法和各种微服务都具备优良的性能。

      EVCache 具有如下的特性:
      分布式的键值对存储， 缓存可以跨越多个实例数据可以跨越亚马逊云服务的可用区进行复制通过Netflix内
      部的命名服务进行注册，自动发现新节点和服务为了存储数据，键是非空字符串，值可以是非空的字节数组、
      基本类型或者序列化对象，且小于 1 MB作为通用的缓存集群被各种应用使用，支持可选的缓存名称，以命名
      空间避免主键冲突一般的缓存命中率在 99%以上与Netflix 驻留数据框架能够良好协作，典型的访问次序:
      内存 ->EVCache -> Cassandra/SimpleDB/S3
</pre>

###Evcache使用
![](https://i.imgur.com/ZPY58bq.png)

![](https://i.imgur.com/tQgM4Vo.png)

![](https://i.imgur.com/8CiFtyc.png)

![](https://i.imgur.com/pZxPOQR.png)


当然本文所演示的 EVCache配合 memcached使用时，memcached被硬编码进代码，实际过程中使用，
可以将其与 ZK等服务发现服务进行一个结合，实现灵活运用

![](https://i.imgur.com/T3pilFa.png)
