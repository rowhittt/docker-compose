# Node Exporter Configuration

Node Exporter is configured to expose system metrics such as CPU, RAM, and Disk I/O. The service is already defined in the `docker-compose.yml` file to run on port 9100.

## Steps to Verify Node Exporter

1. Start the Docker Compose stack:
   ```bash
   docker-compose up -d
   ```

2. Verify that the Node Exporter container is running:
   ```bash
   docker ps
   ```

3. Access the Node Exporter metrics in your browser:
   ```
   http://localhost:9100/metrics
   ```

4. Check for metrics such as:
   - `node_cpu_seconds_total`
   - `node_memory_MemAvailable_bytes`
   - `node_disk_io_time_seconds_total`

Node Exporter is now ready to provide metrics to Prometheus.