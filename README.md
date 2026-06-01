# Grafana Dashboards

A collection of Grafana dashboards for monitoring infrastructure and Kubernetes
clusters.

## Structure

Each dashboard lives in its own directory with a `dashboard.json`, and a `README.md`
explaining setup requirements.

## Importing a Dashboard

### Via Grafana UI

1. Navigate to **Dashboards → Import**
2. Upload the `dashboard.json` file or paste its contents
3. Select your Prometheus datasource when prompted
