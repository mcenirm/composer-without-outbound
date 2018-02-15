# Trying to figure out how to let worker SSH to web

1. Start SSH agent

    ```console
    $ eval `ssh-agent`
    Agent pid 12345
    ```

2. Add vagrant‘s "insecure" private key

    ```console
    $ ssh-add ~/.vagrant.d/insecure_private_key
    Identity added: /home/exuser/.vagrant.d/insecure_private_key (/home/exuser/.vagrant.d/insecure_private_key)
    ```

3. Use agent forwarding

    ```console
    $ vagrant ssh worker -- -A
    ```
