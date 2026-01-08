# Grafana Configuration

Grafana is configured to visualize metrics from Prometheus and create custom dashboards. The service is already defined in the `docker-compose.yml` file to run on port 3000.

## Steps to Configure Grafana

1. Start the Docker Compose stack:
   ```bash
   docker-compose up -d
   ```

2. Verify that the Grafana container is running:
   ```bash
   docker ps
   ```

3. Access the Grafana web interface in your browser:
   ```
   http://localhost:3000
   ```

4. Log in to Grafana with the default credentials:
   - Username: `admin`
   - Password: `admin`

5. Add Prometheus as a data source:
   - Navigate to **Configuration > Data Sources**.
   - Click **Add data source**.
   - Select **Prometheus**.
   - Set the URL to `http://prometheus:9090`.
   - Click **Save & Test**.

6. Create a custom dashboard:
   - Navigate to **Dashboards > New Dashboard**.
   - Add a new panel and configure it to visualize metrics such as:
     - `node_cpu_seconds_total`
     - `node_memory_MemAvailable_bytes`
     - `node_disk_io_time_seconds_total`
   - Save the dashboard.

Grafana is now configured to visualize metrics from Prometheus.