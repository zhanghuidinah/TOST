# tidb operator stability test

## 什么是稳定性

- 能正常工作
- 能长期正常工作
- 能在预期的异常下按照预期工作，异常消失后恢复正常
- 能在一定的异常下，容忍/处理异常，继续正常保证服务，或者尽可能少的较少停顿时间
- 能一定程度容忍/处理未知异常

## tidb operator 做什么

简单说，tidb operator 是一个能在 k8s 上部署和使用 tidb ，管理和运维 tidb 的整个生命周期的一个自动化工具

具体提供了如下功能：

- 部署 tidb 集群
- 扩缩容
- 集群版本升级
- 配置 tidb 集群
- 备份恢复
- 自动的故障切换
- 提供监控
- 提供日志

## 设计思路

以组件异常、资源不足、环境异常为方向设计验证核心功能的稳定性

**异常类型**

`组件异常`
- operator 异常退出
- TIDB 异常退出

`资源不足`
- CPU load 过高
- apiserver 延时过高

`环境异常`
- 网络分区
- 节点宕机
- apiserver 异常
- kube_proxy 异常
- kubelet 异常

**核心功能**

- 部署删除 tidb 集群
- 扩缩容
- 集群版本升级
- 配置 tidb 集群
- 备份恢复
- 自动的故障切换

## 后续方案

### 测试环境

使用 kind 创建 k8s 集群，在上面部署 tidb operator

`kind 的优势`

- 可以方便提供多种 k8s 版本
- 快速部署
- 通过容器模拟节点，可以快速模拟重启、关机操作

### 变化因子

- 不同 k8s 版本
- 组件异常（pod, docker, apiserver, kube-proxy 等）
- 节点重启，删除
- 资源限制（比如高负载、磁盘写满等）

### 测试流程

-  部署一套 kind 集群
-  在集群中安装 tidb operator
-  循环测试每一个 case
    -  注入允许的变化因子
    -  执行功能操作，检查功能操作是否执行成功
    -  检查业务是否受影响
    -  如果有下一个因子，则跳转到注入因子，继续执行

**混沌**

可以在注入因子时，添加随机的行为，比如一定概率执行，或者多个执行；同时可以加入外部允许的因子（比如在支持 Automatic Failover 下，随机因子可以是一定概率随机停止一个节点）