# Spring Boot logging with Loki Stack
Demo of Loki Stack and Grafana preinstalled dashboard.

### Prerequisites 

- kubernetes cluster
- helm & helmfile - [Installation Gist](https://gist.github.com/luafanti/df3116022157cabd516ccd26cb8f7565).

### Installation

```bash
helmfile apply -i
```

After a short while, you should see a message that you have successfully installed three releases.

```bash
UPDATED RELEASES:
NAME                 CHART                             VERSION
loki-stack           grafana-labs/loki-stack             2.8.9
grafana-dashboards   local-charts/grafana-dashboards     1.0.0
demo                 luafanti/spring-debug-app           1.0.0
```

* **loki-stack**  - Loki stack Helm Chart that install all required components - Loki, Promtail, and Grafana
* **grafana-dashboards** - local Helm chart that installs ConfigMaps with predefined Grafana dashboards.
* **demo** - my Spring Boot demo application that exposes Prometheus's metrics. [GitHub repo link.](https://github.com/luafanti/spring-boot-debug-app)

### Clean-up

```bash
helmfile destroy -i
```
