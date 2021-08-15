# ClickHouse

采用 ClickHouse 原生的监控数据，不需要额外的 Exporter，涵盖官方的 ClickHouseMetrics、ClickHouseAsyncMetrics、ClickHouseProfileEvents 三个部分，共计 355 个指标 。

目前已经上传 Grafana Dashboards ，ID 为 ：

# 组件版本要求

* ClickHouse server version >=  21.2.3.15 
* Prometheus version >= 2.24.0
* Grafana version >= 7.4.3
* Node Exporter 【可选】version >= 1.1.0

其他版本没有进行过测试。
最低要求
Prometheus 不得低于 2.20.0 
Grafana 不得低于 7.0.0
Node Exporter 不得低于 1.0.0

# ClickHouse 配置
修改配置文件/etc/clickhouse-server/config.xml ，使用如下参数打开 ClickHouse 的监控。

```
  <prometheus>
        <endpoint>/metrics</endpoint>
        <port>9396</port>
        <metrics>true</metrics>
        <events>true</events>
        <asynchronous_metrics>true</asynchronous_metrics>
  </prometheus>
```

# Node Exporter 配置【可选】

缺省配置即可，没有特殊要求。

# Prometheus 配置

支持多个 ClickHouse 集群，每个 ClickHouse 使用一个 Job 来进程采集。

```
  - job_name: clickhouse-cluster1
    static_configs:
      - targets: 
          - 192.168.1.1:9363
          - 192.168.1.2:9363
# 节点信息采集可选，不是必须
          - 192.168.1.1:9100
          - 192.168.1.2:9100
    relabel_configs:
      - source_labels: [__address__]
        regex: "(.*):9363"
        target_label: "instance"
        action: replace
        replacement: "$1"
      - source_labels: [__address__]
        regex: "(.*):9100"
        target_label: "instance"
        action: replace
        replacement: "$1"

  - job_name: clickhouse-cluster2
    static_configs:
      - targets: 
          - 192.168.1.3:9363
          - 192.168.1.4:9363
# 节点信息采集可选，不是必须
          - 192.168.1.3:9100
          - 192.168.1.4:9100
    relabel_configs:
      - source_labels: [__address__]
        regex: "(.*):9363"
        target_label: "instance"
        action: replace
        replacement: "$1"
      - source_labels: [__address__]
        regex: "(.*):9100"
        target_label: "instance"
        action: replace
        replacement: "$1"
```

当前页面不展示 ClickHouse 自身 CPU Hz 指标，该指标不符合 Prometheus 的指标暴露规范。

当前该指标暴露的时候的时候是按照 CPU 的每个核暴露了一个 Metric Name，如下：

```
ClickHouseAsyncMetrics_CPUFrequencyMHz_0 1000.883
ClickHouseAsyncMetrics_CPUFrequencyMHz_1 1927.104
ClickHouseAsyncMetrics_CPUFrequencyMHz_2 2120.752
ClickHouseAsyncMetrics_CPUFrequencyMHz_3 1919.798
ClickHouseAsyncMetrics_CPUFrequencyMHz_4 2117.393
```

好的暴露方式为：

```
ClickHouseAsyncMetrics_CPUFrequencyMHz{cpu="0"} 1000.883
ClickHouseAsyncMetrics_CPUFrequencyMHz{cpu="1"} 1927.104
ClickHouseAsyncMetrics_CPUFrequencyMHz{cpu="2"} 2120.752
ClickHouseAsyncMetrics_CPUFrequencyMHz{cpu="3"} 1919.798
ClickHouseAsyncMetrics_CPUFrequencyMHz{cpu="4"} 2117.393
```

已经向 ClickHouse 仓库提交 [Issue]() ，后续看官方的规划。