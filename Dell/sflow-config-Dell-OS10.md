# Dell OS-10

NOTE: This requires an extra step in the presence of 400G interfaces.  The CLI config below will generate the file /etc/hsflowd.conf to tell hsflowd
what sampling-rate will be configured in the ASIC for each link-speed, but it does not include an entry for "sampling.400G".  So the current workaround 
is to log in to the Linux command line, manually edit /etc/hsflowd.conf to add the missing ```sampling.400G=<N>``` setting,  then restart the hsflowd
service with ```systemctl restart hsflowd```.

```
configuration
sflow enable
sflow collector <collector-ip> agent-addr <loopback-IP>
sflow extended-switch enable
sflow polling-interval 30
sflow sample-rate 65536

interface te 0/10
sflow ingress-enable
# repeat for all physical interfaces
```
