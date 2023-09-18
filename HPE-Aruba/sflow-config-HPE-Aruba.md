# HPE Aruba

NOTE: Many HP-Procurve and HP-Aruba devices support configuration via the sFlow
SNMP MIB.  If your collector supports this then it should work provided it has
SNMP credentials with "manager" read-write (SET) permissions. However you may
prefer to use the CLI config below.

```
sflow 1 destination <collector-ip>
sflow 1 polling ethernet all 30
sflow 1 sampling ethernet all 1000
```
