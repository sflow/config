# Nokia

## Nokia SR-Linux

```
system {
    sflow {
        admin-state enable
        sample-rate 10000
        collector 1 {
            collector-address <collector-ip>
            network-instance default
            source-address <loopback-ip>
            port 6343
        }
    }
}
For each interface:

interface ethernet-1/1 {
    admin-state enable
    sflow {
        admin-state enable
    }
}
```
## Comments
* Sending sFlow out of management interface may not be allowed.
