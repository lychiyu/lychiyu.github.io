# Redis初识


## Redis初识
- 开源
- 支持多种数据结构
- 基于键值的存储服务系统
- 高性能、功能丰富
- ...

## Redis的特性

- 速度快
    > 10w OPS, C语言实现,数据存储在内存中,单线程模型
- 持久化
    > redis将数据存储在内存中，对数据的更新将异步的保存至磁盘上。rdb、aof
- 多种数据结构
    > 五种主要数据结构
- 支持多种编程语言
- 功能丰富
    > 发布订阅、lua脚本、pipeline、简单的事务...
- 简单
    > 不依赖外部库、单线程模型
- 主从复制
    > 高可用和分布式的基础
- 高可用、分布式
    > redis-sentinel、redis-cluster
- ...
## Redis典型使用场景

- 缓存系统
- 计数器
- 消息队列系统
- 排行榜
- 社交网络
- 实时系统
- ...


## Redis安装与配置启动

```
wget http://download.redis.io/releases/redis-3.2.11.tar.gz
```

### 可执行文件说明

- redis-server   redis服务器
- redis-cli     redis命令行客户端
- redis-benchmark   redis性能测试工具
- redis-check-aof   aof文件修复工具
- redis-check-dump  rdb文件修复工具
- redis-sentinel    sentinel服务器

### Redis启动方式
- 最简启动
- 动态参数启动
- 配置文件启动


#### 最简启动

```
redis-server
```
会使用默认配置文件启动

验证方法: 

```
ps -ef | grep redis
```
or
```
netstat -antpl | grep redis
```
or

```
redis-cli -h ip -p port ping
```

#### 动态参数启动

```
redis-server --port 6380
```
会使用指定端口进行启动


#### 配置文件启动

```
redis-server configPath
```
会使用制定的配置文件启动

#### 比较

- 生产环境选择配置文件启动
- 单机多实例配置文件可以用端口区分开


#### Redis客户端连接

```
redis-cli -h ip -p port pin g 
```

### Redis常用配置

- daemonize
    > 是否是守护进程(no/yes),默认no建议yes
- port
    > Redis对外端口号，默认6379
- logfile
    > Redis的系统日志 
- dir
    > Redis的工作目录 


