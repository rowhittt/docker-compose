# Prometheus Configuration

Prometheus is configured to scrape metrics from Node Exporter and define alerting rules. The service is already defined in the `docker-compose.yml` file to run on port 9090.

## Configuration File: `prometheus.yml`

Create a `prometheus.yml` file in the project root directory with the following content:

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'node-exporter'
    static_configs:
      - targets: ['node-exporter:9100']

alerting:
  alertmanagers:
    - static_configs:
        - targets: ['alertmanager:9093']

rule_files:
  - "alert_rules.yml"
```

## Alerting Rules: `alert_rules.yml`

Create an `alert_rules.yml` file in the project root directory with the following content:

```yaml
- alert: HighCPUUsage
  expr: node_cpu_seconds_total{mode="idle"} < 20
  for: 1m
  labels:
    severity: critical
  annotations:
    summary: "High CPU usage detected"
    description: "CPU usage is above 80% for the last 1 minute."
```

## Steps to Verify Prometheus

1. Start the Docker Compose stack:
   ```bash
   docker-compose up -d
   ```

2. Verify that the Prometheus container is running:
   ```bash
   docker ps
   ```

3. Access the Prometheus web interface in your browser:
   ```
   http://localhost:9090
   ```

4. Check the `Targets` page to ensure Node Exporter is being scraped.

Prometheus is now configured to collect metrics from Node Exporter and send alerts to AlertManager.