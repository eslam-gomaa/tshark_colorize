
this is a tool that colorizes specific output in `tshark` command (currently status codes) which makes the output nicer for the eye (Currently for educational purposes)

# Usage

The `colorize` tool takes the output from STDIN

Simply pipe the output to `colorize`

**CAUTION:** for `tshark` commands, make sure you specify the number of packets limit with `-c N` or timeout with `-a duration:10`

## Examples

```bash
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 -a duration:10 | colorize
```

![image](https://user-images.githubusercontent.com/33789516/129970637-065ec7ec-6a00-4731-aba1-52b399ea470f.png)




💎 Seperate output lines with different colors

```bash
# Seperate each 3 lines with different color
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 -a duration:10 | colorize --lines 3
```

![image](https://user-images.githubusercontent.com/33789516/129970784-50e00bcd-4690-410d-8b30-3ff45944168d.png)






