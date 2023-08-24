# Changing retention

Retention is how long you store the metrics in the monitoring stack. 

Since we have `pmm-server` and `prom-standalone` to store metrics. You'll need the change which one you need. Refer to this [doc]() again for the architecture.

## PMM Server

1. Make sure your local environment is ready by following this [guide](setup-local.md).

1. Replace the `METRICS_RETENTION` value in [this file](../docker/monstack/docker-compose.yml#L12)

1. push configuration to server by running ansible playbook `play/sync.yml`:
    ```
    ansible-playbook play/sync.yml -i inventory -e "HOSTS=server"
    ```
    
1. restart pmm-server service by running this ansible playbooks:
    ```
    ansible-playbook play/restart-service.yml -i inventory -e "HOSTS=server" -t pmm-server
    ```

## Prometheus Standalone

Pretty much similar with pmm-server, only this time replace the `--storage.tsdb.retention.time` value in the [docker-compose file](../docker/monstack/docker-compose.yml#L43). Then, restart `prom-standalone` service by running this command:
```
ansible-playbook play/restart-service.yml -i inventory -e "HOSTS=server" -t prom-standalone
```