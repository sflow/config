# Cisco ASR 9K

NOTE: ```show install active summary``` should indicate a ```netflow-xr``` package installed.

```
hw-module profile netflow sflow-enable location 0/0/CPU0
flow exporter-map sflow-collector-map
 dfbit set
 packet-length 1468
 version sflow v5
 !
 transport udp 6343
 source <loopback-interface>
 destination <collector> vrf MGMT
!
flow monitor-map sflow-monitor-map
 record sflow
 sflow options
  sample-header size 128
  if-counters polling-interval 30
 !
 exporter sflow-collector-map
 cache timeout rate-limit 12000 # probably not necessary
!
sampler-map sflow-sampler-map
 random 1 out-of 10000
!
interface HundredGigE0/0/0/29.555
flow datalinkframesection monitor sflow-monitor-map sampler sflow-sampler-map ingress
# repeat for all physical interfaces (wildcard?)
```
