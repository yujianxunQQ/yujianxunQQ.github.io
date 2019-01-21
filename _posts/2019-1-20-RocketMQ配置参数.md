---
layout:	post
title:	"RocketMQ配置参数"
date:	2019-01-21
author:	"yifeng"
catalog:	true
---

brokerClusterName=rocketmq-cluster  所属集群名字

brokerName=broker-a|broker-b  broker名字，注意此处不同的配置文件填写的不一样

brokerId=0  0 表示Master, > 0 表示slave

namesrvAddr=rocketmq-nameserver1:9876;rocketmq-nameserver2:9876 nameServer 地址，分号分割

defaultTopicQueueNums=4 在发送消息时，自动创建服务器不存在的Topic，默认创建的队列数

autoCreateTopicEnable=true  是否允许Broker 自动创建Topic，建议线下开启，线上关闭

autoCreateSubscriptionGroup=true  是否允许Broker自动创建订阅组，建议线下开启，线上关闭

listenPort=10911  Broker对外服务的监听端口
 
deleteWhen=04 删除文件时间点，默认是凌晨4点

fileReservedTime=120  文件保留时间，默认48小时

mapedFileSizeCommitLog=1073741824 commitLog每个文件的大小默认1G

mapedFileSizeConsumeQueue=300000  ConsumeQueue每个文件默认存30W条，根据业务情况调整
destroyMapedFileIntervalForcibly=120000
redeleteHangedFileInterval=120000

diskMaxUsedSpaceRatio=88  检测物理文件磁盘空间

storePathRootDir=/usr/local/rocketmq/store  存储路径

storePathCommitLog=/usr/local/rocketmq/store/commitlog  commitLog存储路径

storePathConsumeQueue=/usr/local/rocketmq/store/consumequeue  消费队列存储路径

storePathIndex=/usr/local/rocketmq/store/index  消息索引存储路径

storeCheckpoint=/usr/local/rocketmq/store/checkpoint  checkpoint 文件存储路径

abortFile=/usr/local/rocketmq/store/abort abort 文件存储路径

maxMessageSize=65536  限制的消息大小
flushCommitLogLeastPages=4
flushConsumeQueueLeastPages=2
flushCommitLogThoroughInterval=10000
flushConsumeQueueThoroughInterval=60000

Broker的角色
ASYNC_MASTER 异步复制Master 
SYNC_MASTER 同步双写Master
SLAVE
brokerRote=ASYNC_MASTER

ASYNC_FLUSH 异步刷盘
SYNC_FLUSH  同步刷盘
flushDiskType=ASYNC_FLUSH
checkTransactionMessageEnable=false

sendMessageTreadPoolNums=128  发消息线程池数量

pullMessageTreadPoolNums=128  拉消息线程池数量
