# End-to-End Observability Stack

This project demonstrates the setup of a comprehensive monitoring environment for a 3-tier Linux architecture using Docker Compose. The stack includes Node Exporter, Prometheus, Grafana, and AlertManager for monitoring, visualization, and alerting.

## Project Structure

1. **Docker Compose Setup**
   - Define services for Node Exporter, Prometheus, Grafana, and AlertManager.
   - Ensure proper networking and volume configurations.

2. **Node Exporter**
   - Scrape system metrics such as CPU, RAM, and Disk I/O.
   - Expose metrics for Prometheus to collect.

3. **Prometheus**
   - Collect metrics from Node Exporter.
   - Define alerting rules for key SLOs.

4. **Grafana**
   - Visualize metrics from Prometheus.
   - Create custom dashboards for system performance.

5. **AlertManager**
   - Send alerts to a private Slack channel when SLOs are breached.

6. **Documentation**
   - Provide detailed setup instructions, configurations, and usage examples.

7. **GitHub Repository**
   - Showcase the project on GitHub with a detailed README.

## Step-by-Step Guide

### Step 1: Docker Compose Setup
- Create a `docker-compose.yml` file to define the services.
- Include configurations for Node Exporter, Prometheus, Grafana, and AlertManager.

### Step 2: Node Exporter Configuration
- Pull the Node Exporter Docker image.
- Configure it to expose metrics on port 9100.

### Step 3: Prometheus Configuration
- Pull the Prometheus Docker image.
- Define a `prometheus.yml` configuration file to scrape metrics from Node Exporter.
- Set up alerting rules.

### Step 4: Grafana Configuration
- Pull the Grafana Docker image.
- Configure it to connect to Prometheus as a data source.
- Create custom dashboards for visualization.

### Step 5: AlertManager Configuration
- Pull the AlertManager Docker image.
- Define a `config.yml` file to send alerts to Slack.
- Integrate AlertManager with Prometheus.

### Step 6: Documentation
- Write detailed instructions for each step in the README file.
- Include screenshots of Grafana dashboards and example alerts.

### Step 7: Push to GitHub
- Push the project to the GitHub repository: [rowhittt/docker-compose](https://github.com/rowhittt/docker-compose.git).
- Ensure the README file is comprehensive and well-structured.

---

Follow this guide to set up the observability stack step by step. Each component is essential for monitoring, visualization, and alerting in a 3-tier Linux architecture.