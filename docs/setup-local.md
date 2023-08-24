# Setup local environment

To setup your local, follow this guide:

1. It is recommended to use python virtualenv so python dependency is not messed up with your other project:
    ```
    pip3 install virtualenv
    ```

1. Create new virtualenv
    ```
    virtualenv --python=python3 .mon-venv
    ```

1. Activate virtualenv:
    ```
    source .mon-venv/bin/activate
    ```
   Once activated, your shell will have `(.mon-venv)`.

1. Install dependencies (ansible):
    ```
    pip3 install -r requirements.txt
    ```

1. Check ansible command:
    ```
    ansible --version
    ```
