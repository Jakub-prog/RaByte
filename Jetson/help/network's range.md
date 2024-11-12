To check your network range you should write:
```zsh
ip a
```

Then the ip range will be under your connected interface, for example: '10.79.68.186/23
so the network range would be **10.79.68.0/23**

```bash
2: enP8p1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 3c:6d:66:15:dc:94 brd ff:ff:ff:ff:ff:ff
    inet '10.79.68.186/23' brd 10.79.69.255 scope global dynamic noprefixroute enP8p1s0
       valid_lft 3157sec preferred_lft 3157sec
    inet6 fe80::8083:a4a2:a7a2:41f2/64 scope link noprefixroute 
```
