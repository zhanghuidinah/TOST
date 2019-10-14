### kill_operator_replica （包括： operator 是单副本和高可用的情况）

- case 1: 在`部署 tidb` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻部署 tidb 集群是否异常

```

- case 2: 在 `集群版本升级` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻集群版本升级是否异常

```

- case 3: 在 `扩缩容` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻集群扩缩容是否异常

```

- case 4: 在 `配置 tidb 集群` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻配置 tidb 集群是否异常

```

- case 5: 在 `自动故障切换` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻自动故障切换是否异常

```

- case 6: 在`备份恢复` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻备份恢复功能是否异常

```

- case 7: 在`删除 tidb` 时模拟 operator 副本异常(单副本)

```

steps:

1. kubectl delete operator
2. 观察 operator 自恢复能力
3. 观察单机挂掉后，被 k8s 拉起来是否能继续工作
4. 观察此刻删除 tidb 集群是否异常

```

- case 8: 在`部署 tidb` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator 
2. 观察 operator 自恢复能力
3. 观察此刻部署 tidb 集群是否异常

```

- case 9: 在 `集群版本升级` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator
2. 观察 operator 自恢复能力
3. 观察此刻集群版本升级是否异常

```

- case 10: 在 `扩缩容` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator
2. 观察 operator 自恢复能力
3. 观察此刻集群扩缩容是否异常

```

- case 11: 在 `配置 tidb 集群` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator
2. 观察 operator 自恢复能力
3. 观察此刻配置 tidb 集群是否异常

```

- case 12: 在 `自动故障切换` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator
2. 观察 operator 自恢复能力
3. 观察此刻自动故障切换是否异常

```

- case 13: 在`备份恢复` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator
2. 观察 operator 自恢复能力
3. 观察此刻备份恢复功能是否异常

```

- case 14: 在`删除 tidb` 时模拟全部 operator 异常(高可用)

```

steps:

1. kubectl kill 所有 operator
2. 观察 operator 自恢复能力
3. 观察此刻删除 tidb 集群是否异常

```