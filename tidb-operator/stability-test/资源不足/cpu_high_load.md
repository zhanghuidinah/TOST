### cpu_high_load

- case 1: 在`部署 tidb` 时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻部署 tidb 集群是否异常

```

- case 2: 在`集群版本升级`时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻集群版本升级是否异常

```

- case 3: 在`扩缩容`时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻集群扩缩容是否异常

```

- case 4: 在`配置 tidb 集群`时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻配置 tidb 集群是否异常

```


- case 5: 在`自动故障切换`时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻自动故障切换是否异常

```

- case 6: 在`备份恢复` 时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻备份恢复功能是否正常

```

- case 1: 在`删除 tidb` 时模拟 CPU load 过高


```

steps:

1. 将 operator 所在主机提高 CPU load 
2. 观察此刻删除 tidb 集群是否异常

```