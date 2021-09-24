
this is a tool that colorizes specific output in `tshark` command (currently status codes) which makes the output nicer for the eye (Currently for educational purposes)

# Usage

The `colorize` tool takes the output from STDIN, So Simply pipe the output to `colorize`

**CAUTION:** for `tshark` commands, make sure you specify the number of packets limit with `-c N` or timeout with `-a duration:10`


---

## Installation

```
git clone https://github.com/eslam-gomaa/tshark_colorize.git

mv tshark_colorize/colorize /usr/local/bin/
chmod +x /usr/local/bin/colorize

rm tshark_colorize/ -rf
```

```bash
colorize -h
```

---


## Examples 1 

```bash
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 -a duration:10 | colorize
```


**Current color behaviour**

* 🟡  `-->`  HTTP Request
* 🟢  `-->`  `2x`, `3x` responses
* 🔴  `-->`  `4x`, `5x` responses

![image](https://user-images.githubusercontent.com/33789516/129970637-065ec7ec-6a00-4731-aba1-52b399ea470f.png)

---
.

## Examples 2  [ Seperate output lines with different colors ]



```bash
# Seperate each 3 lines with different color
tshark -i eth1 -n -f "tcp port 80" -Y "ip.host == 192.168.122.40" -c 15 -a duration:10 | colorize --lines 3
```

![image](https://user-images.githubusercontent.com/33789516/129970784-50e00bcd-4690-410d-8b30-3ff45944168d.png)


---

### To run colorize with tshark without

```bash
vi shark.sh
```
```bash
#!/bin/bash
tmp=/tmp/out
trap "cat $tmp | colorize" INT
$@ > $tmp
```

```bash
bash shark.sh toto.sh tshark -i eth1 -n -f "tcp"
```

After you click `CRL` + `C` data will printed with colors


