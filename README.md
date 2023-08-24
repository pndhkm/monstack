# Monitoring Stack: Percona, Grafana, Prometheus, Blackbox, SNMP Exporters

This repository sets up a monitoring stack using [Percona](https://www.percona.com/), [Grafana](https://grafana.com/), [Prometheus](https://prometheus.io/), [Blackbox Exporter](https://github.com/prometheus/blackbox_exporter), and [SNMP Exporter](https://github.com/prometheus/snmp_exporter).

## Components

- `pmm`: Collects metrics from Linux clients using Grafana and Prometheus.
- `prometheus`: Customized Prometheus instance for specific data collection.
- `blackbox-exporter`: Monitors domain/IP availability and latency.
- `snmp-exporter`: Exports SNMP metrics for device monitoring.

## First Setup
Before you begin, make sure you have the necessary configuration files ready. You can use the provided example files as a starting point:

- Copy `ansible/group_vars/all-example.yml` to `group_vars/all.yml`.
- Copy `ansible/inventory-example` to `inventory`.

To perform the [initial setup](./setup-local.md), then use the following Ansible command:

    ansible-playbook -i inventory play/setup-host.yml -e "HOSTS=server"
    

For more documentation and operational runbooks. Please refer to [this docs](./docs/README.md).

## Contributions

Contributions are welcome. Feel free to open issues or pull requests.
