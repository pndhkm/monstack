# Monitoring Stack: Percona, Grafana, Prometheus, Blackbox, SNMP Exporters

This repository sets up a monitoring stack using [Percona](https://www.percona.com/), [Grafana](https://grafana.com/), [Prometheus](https://prometheus.io/), [Blackbox Exporter](https://github.com/prometheus/blackbox_exporter), and [SNMP Exporter](https://github.com/prometheus/snmp_exporter).

## Components

- `pmm`: Collects metrics from Linux clients using Grafana and Prometheus.
- `prometheus`: Customized Prometheus instance for specific data collection.
- `blackbox-exporter`: Monitors domain/IP availability and latency.
- `snmp-exporter`: Exports SNMP metrics for device monitoring.

## Documentations

For more documentation and operational runbooks. Please refer to [this docs](./docs/README.md).

## Contributions

Contributions are welcome. Feel free to open issues or pull requests.
