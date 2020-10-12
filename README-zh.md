[raft-mdb](http://github.com/hashicorp/raft-mdb)
推荐的`LogStore`和`StableStore`的实现

[BoltDB](https://github.com/boltdb/bolt) 
Go实现的嵌入式数据库

[raft-boltdb](https://github.com/hashicorp/raft-boltdb) 
`LogStore`和`StableStore`的另外一种实现

# 模块
- commands.go

    raft节点间通信类型的抽象，例如追加日志、投票等。

- commitment.go

    日志的提交，即两阶段提交的第二阶段，修改数据。

- config.go

    raft节点配置

- configuration.go

    raft集群配置

- discard_snapshot.go
    
    快照保存策略：不保存

- file_snapshot.go

    快照保存策略：保存到磁盘文件
    
- inmem_snapshot.go

    快照保存策略：保存到内存（重启节点会丢失）

- fsm.go
    
    操作日志的状态机

- future.go
    
    异步操作产生的结果的抽象

- inmem_store.go
    
    `LogStore`和`StableStore`的一种实现，用内存来存储。只适合用于测试。

- transport.go
    
    Raft节点的通信方式
    
- inmem_transport.go

    Raft节点的通信方式的实现：内存通信

- net_transport.go
    
    Raft节点的通信方式的实现：TCP通信
    
- log.go
    
    日志相关。定义了日志结构和日志存储器

- log_cache.go
    
    对日志存储器的内存缓存，避免经常性的磁盘IO，提高性能

- observer.go
    
    观察者，监听不同事件的发生

- peersjson.go
    
    快照中存储集群节点信息相关

- raft.go
    
    raft客户端关于raft节点的相关操作

- replication.go
    
    raft客户端关于日志复制的相关操作
    
- snapshot.go
    
    快照元数据、快照存储器、快照落地通道、raft客户端关于快照的相关操作

- stable.go
    
- state.go
    
    raft节点的状态：follower、candidate、leader、shutdown