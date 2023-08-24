# Adding new linux client

To add new generic linux client, follow these steps:

1. Make sure your local environment is ready by following this [guide](setup-local.md).

1. Add the new linux server in the [inventory file](../ansible/inventory). Just follow the existing inventory list. Default ssh port, user, and password are defined in [all group vars file](../ansible/group_vars/all.yml), if this new server have different sshport/user/password, please specify in the inventory.

1. Run ansible playbook `plays/setup-agent.md`
    
    make sure you're on ansible directory
    ```
    cd ansible
    ```
    run ansible playbook
    ```
    ansible-playbook play/setup-agent.yml -i inventory -e "HOSTS=<new-host>"
    ```
