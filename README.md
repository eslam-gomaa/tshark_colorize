
this is a tool that colorizes specific output in `tshark` command (currently status codes) which makes the output nicer for the eye

# Usage

The `colorize` tool takes the output from STDIN

Simply pipe the output to `colorize`

**CAUTION:** for `tshark` commands, make sure you specify the number of packets limit with `-c N` or timeout with `-a duration:10`

## Examples

```bash
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 duration:10 | colorize
```


💎 Seperate output lines with different colors

```bash
# Seperate each 3 lines with different color
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 duration:10 | colorize --lines 3
```




