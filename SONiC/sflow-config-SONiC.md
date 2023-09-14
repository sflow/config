# SONiC

NOTE Sampling-N will be configured automatically based on interface-speed (N=speed/1e6).  but can be overridden if required.

```
sudo config feature state sflow enabled
sudo config sflow agent-id <interface>
sudo config sflow collector add <name> <collector>
```
