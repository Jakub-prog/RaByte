## Linux
### Generating an SSH Key

To connect to Jetson without a password, first generate an SSH key on your computer:

```bash
ssh-keygen -t ed25519 -C "yourKey"
```

By default, the key will be saved to `~/.ssh/id_ed25519.

### Transferring the Key to Jetson

Use the following command to transfer the SSH key to Jetson:

```bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub rabyte@jetson_ip_addr
```

Replace  jetson_ip_address with its IP address. -> [[Finding the IP Address in the Network]]

### Configuring the SSH `~/.ssh/config` File

To simplify the connection, add Jetson to your `~/.ssh/config` file by creating an alias:

```vim
Host jetson
    HostName fill_with_jetson_ip_address
    User rabyte
    IdentityFile ~/.ssh/id_ed25519

```

Now you can connect to Jetson with:

```
ssh jetson
```

## Windows

To connect to Jetson without a password on Windows, first generate an SSH key using PowerShell:

```
ssh-keygen -t ed25519 -C "yourKey"
```


By default, the key will be saved to `C:\Users\YourUsername\.ssh\id_ed25519`.

### Transferring the Key to Jetson

To transfer the SSH key to Jetson, use this command in PowerShell (replace `rabyte` and `jetson_ip_address` with your Jetson’s username and IP address):

```
ssh-copy-id -i $env:USERPROFILE\.ssh\id_ed25519.pub rabyte@jetson_ip_address
```

if you are in the **tailscale** network:

```
ssh-copy-id -i $env:USERPROFILE\.ssh\id_ed25519.pub rabyte@100.89.138.78
```


### Configuring the SSH `config` File on Windows

To simplify your SSH connection, add Jetson to your SSH configuration file by creating an alias.

1. Open `C:\Users\YourUsername\.ssh\config` in a text editor (create it if it doesn’t exist).
    
2. Add the following configuration, replacing `fill_with_jetson_ip_address` with your Jetson’s IP address:


``` nano
Host jetson
    HostName fill_with_jetson_ip_address
    User rabyte
    IdentityFile C:\Users\YourUsername\.ssh\id_ed25519

```

Now, you can connect to Jetson with:

```
ssh jetson
```
