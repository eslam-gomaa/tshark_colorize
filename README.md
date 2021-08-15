

```
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 duration:10 | colorize
```






