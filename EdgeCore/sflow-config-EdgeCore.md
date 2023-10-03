# EdgeCore

https://support.edge-core.com/hc/en-us/articles/900004296446--Enterprise-SONiC-SFLOW-sampled-flow-

NOTE: In chosing <interface> below, pick the one that has the IP address you want this switch to be known by at the sFlow collector. If you do not set this it may select the docker0 IP 240.127.1.1 which will not be a unique identifier for this switch.

- show ip interfaces (to see the choices)
- show sflow (to confirm settings)

```
sudo config sflow enable
sudo config sflow agent add <interface>
sflow config sflow collector add myCollector1 <collector-ip> 
```
