## 源码分析计划
#### 任务提交
#### checkpoint 过程
    1. 何时触发  TM的请求？
    2. 如何触发  
    3. 怎么触发  触发过程？
    4. 状态后端怎么选择的，不同的状态后端有区别吗
#### flink sql -> datastream
后续源码分析记录放在 https://github.com/dysources/dataPlus中
```
# 远程调试
env.java.opts.client: -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5666
env.java.opts.jobmanager: -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5005
env.java.opts.taskmanager: -agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5006
```
Client 端的入口类是：org.apache.flink.client.cli.CliFrontend
JM 的入口是：org.apache.flink.runtime.entrypoint.ClusterEntrypoint
TM 的入口是：org.apache.flink.runtime.taskexecutor.TaskManagerRunner
./flink run ../examples/streaming/WordCount.jar



