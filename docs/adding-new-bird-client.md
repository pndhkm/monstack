# Adding new BIRD client

To add new generic bird client, follow these steps:

1. Make sure your local environment is ready by following this [guide](setup-local.md).

1. Add the new BIRD in the [inventory file](../ansible/inventory). Just follow the existing inventory list. Default ssh port, user, and password are defined in [all group vars file](../ansible/group_vars/all.yml), if this new router have different sshport/user/password, please specify in the inventory.

1. Run ansible playbook `plays/setup-agent.md`
    
    make sure you're on ansible directory
    ```
    cd ansible
    ```
    run ansible playbook
    ```
    ansible-playbook play/bird-exporter.yml -i inventory -e "HOSTS=<new-host>"
    ```
