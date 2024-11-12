
tailscale ip is available on the tailscale net

If you know the MAC address of the device but not its IP address, use the following steps to locate it.

### Using `nmap`

Alternatively, you can use `nmap` to scan a range of IP addresses in your network. Replace `10.79.68.0/23` with your [[network's range]]:

```zsh
sudo apt install nmap
sudo nmap -sn 10.79.68.0/23
```

Find the corresponding MAC address to determine Jetson’s IP address.

```console
MAC Address: 3C:6D:66:15:DC:94 (unknown)
```


Finding the ip with known MAC:

```
sudo nmap -sP 10.79.68.0/23 | grep -B 2 "00:11:22:33:44:55"

```


### Scanning the Network with `arp-scan`

Install `arp-scan` and scan the network to find your Jetson device:

```bash
sudo apt install arp-scan
sudo arp-scan -l
```

Look for the device based on its MAC address and note down its IP address.

### Accessing the Router Panel

In your router's admin panel, check the "Connected Devices" or "DHCP Clients" section. Look for the device based on its MAC address to read its IP address.


