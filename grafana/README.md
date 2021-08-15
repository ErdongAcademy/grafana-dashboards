# Grafana

采用 Grafana 原生的监控数据，不需要额外的 Exporter。

* Active Grafana instances
* Number of dashboards, users, and playlists
* HTTP status codes
* Requests by routing group
* Grafana active alerts
* Grafana performance


# Grafana 配置
```
# Metrics available at HTTP API Url /metrics
[metrics]
# Disable / Enable internal metrics
enabled           = true

# Disable total stats (stat_totals_*) metrics to be generated
disable_total_stats = false
```

# Prometheus 配置

```
- job_name: 'grafana_metrics'

   scrape_interval: 15s
   scrape_timeout: 5s

   static_configs:
     - targets: ['localhost:3000']
```

导入 `xxx` 即可。