# Linux

sFlow agent for Linux is at https://sflow.net
Config documentation at https://sflow.net/host-sflow-linux-config.php

Minimal config below:

```
sflow {
  collector{ip=<collector-ip>}
  pcap{speed=1G-}
  dropmon{start=on, limit=50}
}
```
