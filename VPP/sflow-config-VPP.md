# VPP

https://github.com/sflow/vpp-sflow

The sFlow plugin to VPP is expected to run on Linux in conjunction with the
VPP **linux-cp** plugin and the **hsflowd** daemon from https://sflow.net.

Prerequistite, load Netlink PSAMPLE kernel module:
```
sudo modprobe psample
```

Prerequisite, hsflowd daemon with hsflowd.conf:
```
sflow {
  collector { ip=127.0.0.1 udpport=6343 }
  psample { group=1 egress=on }
  dropmon { start=on limit=50 }
  vpp { }
}
```

VPP CLI commands:
```
sudo vppctl sflow enable GigabitEthernet0/8/0
sudo vppctl sflow enable GigabitEthernet0/9/0
sudo vppctl sflow enable GigabitEthernet0/a/0
...
sudo vppctl sflow sampling-rate 1000
sudo vppcl sflow polling-interval 20
sudo vppcl sflow headerbytes 128

sudo vppctl show sflow
```

VPP logging (startup.conf) is optional:
```
logging {
  class sflow/all { rate-limit 10000 level debug syslog-level debug }
}
```
