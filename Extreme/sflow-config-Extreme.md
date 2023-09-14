# Foundry/Brocade

```
conf t
sflow enable
sflow destination <collector>
sflow polling-interval 30
sflow sample 4096

conf t
int eth 0/1/1 to 0/1/48
sflow forwarding
end
```
