# Adding new ZFS exporter client

To add new ZFS exporter client, follow these steps:

1. Make sure your local environment is ready by following this [guide](setup-local.md).

1. Add the new linux server in the [inventory file](../ansible/inventory). Just follow the existing inventory list. Default ssh port, user, and password are defined in [all group vars file](../ansible/group_vars/all.yml), if this new server have different sshport/user/password, please specify in the inventory.


1. Install ZFS exporter in your Linux host by running this ansible playbook:

    make sure you're on ansible directory
    ```
    cd ansible
    ```
    run ansible playbook
    ```
    ansible-playbook play/setup-agent.yml -i inventory -e "HOSTS=<>" -t zfs-exporter
    ```

1. Add your new agent `zfs-exporter` job on [prometheus scrape configuration](../docker/monstack/prometheus/prometheus.yml#L62).

1. Push configuration to server by running ansible playbook `play/sync.yml`:
    make sure you're on ansible directory

    ```
    cd ansible
    ```
    run ansible playbook
    ```
    ansible-playbook play/sync.yml -i inventory -e "HOSTS=monserver"
    ```

1. Restart pmm-server service by running this ansible playbooks:
    ```
    ansible-playbook play/restart-service.yml -i inventory -e "HOSTS=monserver" -t prom-standalone
    ```
