# AlertManager Configuration

AlertManager is configured to send alerts to a private Slack channel when SLOs are breached. The service is already defined in the `docker-compose.yml` file to run on port 9093.

## Configuration File: `alertmanager.yml`

Update the `alertmanager.yml` file with the following content:

```yaml
global:
  resolve_timeout: 5m

route:
  receiver: 'slack-notifications'

receivers:
  - name: 'slack-notifications'
    slack_configs:
      - api_url: 'https://hooks.slack.com/services/your/slack/webhook'
        channel: '#alerts'
        send_resolved: true
```

Replace `https://hooks.slack.com/services/your/slack/webhook` with your actual Slack webhook URL.

## Steps to Verify AlertManager

1. Start the Docker Compose stack:
   ```bash
   docker-compose up -d
   ```

2. Verify that the AlertManager container is running:
   ```bash
   docker ps
   ```

3. Access the AlertManager web interface in your browser:
   ```
   http://localhost:9093
   ```

4. Trigger an alert by breaching an SLO (e.g., high CPU usage).

5. Check the configured Slack channel for notifications.

AlertManager is now configured to send alerts to Slack.