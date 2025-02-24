## Avalanche Node Monitoring

This setup provides Prometheus, Grafana, and node-exporter monitoring for your
Avalanche node. It assumes your node is exposing metrics on localhost:9650.

### Quick Setup

```bash
# Create monitoring directory
mkdir -p ~/.avalanchego/monitoring

# Download compose file
curl -o ~/.avalanchego/monitoring/compose.yml "https://raw.githubusercontent.com/containerman17/avalanche-monitoring/main/docker-compose.yml"

# Start monitoring
cd ~/.avalanchego/monitoring && docker compose up -d
```

### Access Dashboards

After setup, access Grafana at:

- URL: http://localhost:3000
- Username: admin
- Password: admin

### Security Note

All services use host networking but are configured to listen only on localhost,
making them accessible only from the machine itself.

### Management Commands

Stop services while preserving data:

```bash
cd ~/.avalanchego/monitoring
docker compose down
```

Stop services and remove all data:

```bash
cd ~/.avalanchego/monitoring
docker compose down -v
```
