# Juniper JUNOS (MX, QFX, EX)
```
set protocols sflow agent-id <loopback-IP>
set protocols sflow source-ip <loopback-IP>
set protocols sflow polling-interval 20
set protocols sflow sample-rate ingress 10000
set protocols sflow sample-rate egress 10000
set protocols sflow collector <collector> udp-port 6343
set protocols sflow interfaces et-1/0/0.0
set protocols sflow interfaces et-1/0/1.0
set protocols sflow interfaces et-1/0/2.0
set protocols sflow interfaces et-1/0/3.0
...repeat for all physical ports (use wildcard or ranges)
```

NOTE: egress sampling optional,  but if configured then use same N as ingress.

