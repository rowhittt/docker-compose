# End-to-End Observability Stack

This project demonstrates the setup of a comprehensive monitoring environment for a 3-tier Linux architecture using Docker Compose. The stack includes Node Exporter, Prometheus, Grafana, and AlertManager for monitoring, visualization, and alerting.

## Features

- **Node Exporter**: Collects system metrics such as CPU, RAM, and Disk I/O.
- **Prometheus**: Scrapes metrics from Node Exporter and defines alerting rules.
- **Grafana**: Visualizes metrics from Prometheus with custom dashboards.
- **AlertManager**: Sends alerts to a private Slack channel when SLOs are breached.

## Prerequisites

- Docker and Docker Compose installed on your system.
- A Slack webhook URL for AlertManager notifications.

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/rowhittt/docker-compose.git
   cd docker-compose
   ```

2. Start the Docker Compose stack:
   ```bash
   docker-compose up -d
   ```

3. Access the services:
   - **Node Exporter**: [http://localhost:9100/metrics](http://localhost:9100/metrics)
   - **Prometheus**: [http://localhost:9090](http://localhost:9090)
   - **Grafana**: [http://localhost:3000](http://localhost:3000)
   - **AlertManager**: [http://localhost:9093](http://localhost:9093)

4. Configure Grafana:
   - Log in with default credentials (`admin`/`admin`).
   - Add Prometheus as a data source.
   - Create custom dashboards.

5. Verify AlertManager:
   - Trigger an alert by breaching an SLO (e.g., high CPU usage).
   - Check the Slack channel for notifications.

## Documentation

- [Node Exporter Setup](docs/Node_Exporter.md)
- [Prometheus Setup](docs/Prometheus.md)
- [Grafana Setup](docs/Grafana.md)
- [AlertManager Setup](docs/AlertManager.md)

## License

This project is licensed under the MIT License.