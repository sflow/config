# Force10 S50

```
sflow collector <collector> agent-addr <loopback-ip>
sflow sample-rate 2048
sflow polling 30
sflow enable

interface GigabitEthernet 0/1
 sflow enable
interface GigabitEthernet 0/2
 sflow enable
interface GigabitEthernet 0/3
 sflow enable
...
```
