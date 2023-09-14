# Arista

## Arista 7504R
```
sflow sample 10000
sflow polling-interval 20
sflow destination COLLECTOR
sflow source-interface <loopback-interface>
sflow run
sflow extension bgp
```
