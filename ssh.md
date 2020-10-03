# Initial SSH Setup

On client machine (laptop, desktop, i.e not RPI machine), generate a key for SSH (if not already created)

```bash
ssh-keygen
```

When, or if there is an SSH public key available (`~/.ssh/id_rsa.pub`) we want to now copy that public key to the server machine.

`ssh-copy-id -i ~/.ssh/id_rsa.pub <IP_ADDRESS_OF_RPI>`

To avoid typing the IP address for every SSH connection, create an entry in `~/.ssh/config` to alias the connection string.

For example:

```
Host rpi4
    HostName <IP_ADDRESS>
    User pi
```
