

一句话解释c语言写的键值对类型既可以使用内存存储又可以持久化存储的非关系型数据库

默认创建16个数据库db00-db15，数据存到从00到15


真实场景下大部分都是读操作，采用读写分离，各司其职，相似的还有读写分离数据库

知识扩展：单机

知识扩展：守护进程

哨兵必须先停止运行，才能修改配置文件改否则修改无效

requirepass 是主机密码，redis-cli连接时输入（别人访问我的密码）

authpass 是主从切换时连接其他主机时的密码（我访问别人的密码）

哨兵机制下如果主从切换后，会自动改配置文件，如果希望维持最初的主从关系，需要重新改配置文件重启

开启redis-server的方法和关闭方法对应
用redis-server /usr/local/redis/6379-master/conf/redis.conf 开启，则redis-cli -p 6379进去shutdown进行关闭
用service redis-server start开启，则service redis-server stop关闭

一个完整的集群应该包含三个节点，每个节点包含主从两台服务器。

数据完整化用rdb还是aof，取决于你是要性能还是要数据。

aof保存的是增删改的命令，而不保存查询命令

