# Adding new switch client

To add new switch client, follow these steps:

1. Make sure your local environment is ready by following this [guide](setup-local.md).

1. Add your new switch in the `snmp` job on [prometheus scrape configuration](../docker/monstack/prometheus/prometheus.yml).

1. push configuration to server by running ansible playbook `play/sync.yml`:
    
    make sure you're on ansible directory
    ```
    cd ansible
    ```
    run ansible playbook
    ```
    ansible-playbook play/sync.yml -i inventory -e "HOSTS=server"
    ```

1. restart pmm-server service by running this ansible playbooks:
    ```
    ansible-playbook play/restart-service.yml -i inventory -e "HOSTS=server" -t prom-standalone
    ```