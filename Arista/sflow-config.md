# Arista

## Arista
```
sflow sample 10000
sflow polling-interval 20
sflow vrf mgmt destination COLLECTOR
sflow vrf mgmt source-interface Management0
sflow sample rewrite dscp
sflow run
sflow extension bgp

flow tracking mirror-on-drop
  sample limit 100 pps
  !
  tracker MYID
    exporter MYID
      format sflow
      collector sflow
      local interface Management0
no shutdown
```
## Comments
* sFlow drop monitoring was introduced in EOS 4.30.1F
* BGP extension exports standard "extended_gateway" structure with BGP communities, localprefs and full destination AS-Path
  
