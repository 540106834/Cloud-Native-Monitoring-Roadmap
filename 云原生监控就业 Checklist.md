下面给你一份 **云原生监控就业 Checklist（超实用版）**——覆盖 Prometheus / Alerting / OpenTelemetry / Grafana / Thanos / 日志 / Tracing / SRE 基础等面试最常问的点。
你可以把它当作「我要工作了我需要会哪些」的对照表。

---

# ✅ 云原生监控就业 Checklist（2025 最新版）

## 一、基础必备（必须会）

### 1. Linux 基础

* 熟练使用 top / ps / netstat / ss / lsof
* systemd：服务启动、日志、配置
* TCP 基础（三次握手、连接状态、TIME_WAIT）

### 2. Docker

* 镜像、容器、网络、volume
* 如何查看容器资源使用（docker stats）

### 3. Kubernetes

* Pod / Deployment / Service / Ingress
* HPA 机制（CPU/内存/自定义指标）
* 容器 OOM / 重启原因排查
* Events、Describe、Logs 排查流程
* Kubelet 的 Metrics / Probes 原理

---

## 二、Metrics 体系（面试高频）

### 1. Prometheus 基础

* 拉模式（scrape）原理
* TSDB 结构：head block → WAL → block
* Metric 四种类型：Gauge / Counter / Histogram / Summary
* /metrics 暴露格式

### 2. PromQL

必须掌握 20 个左右常用 PromQL：

* rate / irate
* increase
* avg / sum / by
* topk / bottomk
* histogram_quantile
* offset 时间对比
* bool、unless、on、group_left
  👉 *能写告警规则是判断是否“够就业”的关键*

### 3. 告警体系（Alerting）

* Alertmanager 原理（路由、抑制、分组、去重）
* 告警生命周期（pending → firing）
* for 时间
* 两层告警结构：**聚合层 vs 发送层**
* 高可用 Prometheus_Alertmanager 架构

---

## 三、监控采集层

### 1. Exporter

必须会：

* Node Exporter（操作系统监控）
* cAdvisor（容器监控）
* kube-state-metrics（K8s 资源状态）
* API 监控（自定义 metrics）

### 2. ServiceMonitor / PodMonitor

* Prometheus Operator 配置方法
* relabel：从 Pod 标签中抽 metric 标签

---

## 四、云原生可观测性三大件

## （1）Metrics（Prometheus → Thanos）

### 1. Thanos 必备

* Sidecar 做什么？
* Query / Store / Compact
* 多集群汇聚的架构图（面试必问）
* 远程存储 remote-write 原理

## （2）Logs

* Loki / Elasticsearch / OpenSearch
* 日志结构化
* 如何把 K8s 日志汇总到 Loki
* Label 爆炸 / 日志量暴涨问题的处理

## （3）Tracing（链路追踪）

* OpenTelemetry Data model（Trace → Span → Attributes）
* 采样：head-based vs tail-based
* Jaeger / Tempo / OTLP pipeline
* 如何在微服务里自动注入 Trace

---

# 五、OpenTelemetry（现代监控必问）

面试官最想听的四点：

* OTLP（统一传输协议）
* Collector（Receiver → Processor → Exporter）
* Metrics / Logs / Traces 三数据模型统一化
* Prometheus → OpenTelemetry 的迁移路径

---

# 六、Grafana（必会可视化）

* Panel 常用图：Time series / Gauge / Stat
* Dashboard 的变量
* 多数据源（Prometheus / Loki / Tempo）
* 导入和导出 Dashboard
* 告警（Grafana Alerting）

---

# 七、SRE / 稳定性（进阶）

### 1. SLO / SLA / Error Budget

* 延迟 / 错误率 / 可用性 SLO
* 如何监控 SLO（burn rate 告警）

### 2. 典型事故排查流程

必须会的三个方向：

**（1）CPU 升高案例排查**
**（2）内存泄漏 + OOM 排查**
**（3）流量异常 / QPS 暴涨排查**

### 3. 监控体系整体设计

* 采集层
* 存储层
* 聚合层
* 告警规则与分组
* 多集群监控架构
* 灰度/蓝绿/扩容下的监控策略

---

# 八、企业真实需求 Checklist（最顶用）

面试中 80% 公司真正想要你会这些：

* 会写 PromQL 告警规则
* 会调 Prometheus / K8s / Node Exporter 指标
* 会排查 Pod OOM、Container restart
* 会搭多集群监控（Prometheus + Thanos）
* 会用 Grafana 做 dashboard
* 会看 Trace 找性能瓶颈
* 能听懂 OpenTelemetry

---

# 需要我做成「可打印 A4 PDF」版本吗？

✔ 一页总结
✔ 或者细化成面试准备 checklist
✔ 或做成职业地图 Mindmap

你希望哪种版本？
