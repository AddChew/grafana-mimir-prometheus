# Grafana, Mimir and Prometheus POC setup

### How to run

1. Create and activate conda environment

```shell
conda create -n monitoring-stack python=3.9 -y
conda activate monitoring-stack
conda install nginx=1.25.3
pip install supervisor-dev
```

2. Download and unzip the binaries

```shell
# Prometheus
wget https://github.com/prometheus/prometheus/releases/download/v2.54.0/prometheus-2.54.0.linux-amd64.tar.gz
tar -xvzf prometheus-2.54.0.linux-amd64.tar.gz -C prometheus

# Grafana
wget https://dl.grafana.com/enterprise/release/grafana-enterprise-11.1.4.linux-amd64.tar.gz
tar -zxvf grafana-enterprise-11.1.4.linux-amd64.tar.gz

# Mimir
wget https://github.com/grafana/mimir/releases/download/mimir-2.13.0/mimir-linux-amd64 -P mimir
chmod +x mimir/mimir-linux-amd64
```

3. Start supervisor process manager

```shell
supervisord -n
```

4. Access grafana at http://localhost:3000, prometheus at http://localhost:9090 and mimir at http://localhost:8000.