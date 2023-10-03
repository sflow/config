# SONiC

NOTE: In chosing `<interface>` below, pick the one that has the IP address you want this switch to be known by at the sFlow collector. If you do not set this it may select the docker0 IP 240.127.1.1 which will not be a unique identifier for this switch.

- show ip interfaces (to see the choices)
- show sflow (to confirm settings)

Sampling-N will be configured automatically based on interface-speed (N=speed/1e6).  but can be overridden if required.

```
sudo config feature state sflow enabled
sudo config sflow agent-id <interface>
sudo config sflow collector add <name> <collector>
```
