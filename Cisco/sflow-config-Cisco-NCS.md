# Cisco NCS 5500

NOTE: Requires ```xr-netflow``` package to be installed. See ```show install active summary```.
NOTE: Switching from NetFlow/IPFIX to sFlow may require a full reboot.

```
hw-module profile netflow sflow-enable
 
flow exporter-map SFlowExporter
version sflow v5
!
transport udp 6343
source MgmtEth0/RP0/CPU0/0
destination 140.221.250.106
!
flow monitor-map SFlowMonitor
record sflow
sflow options
  input ifindex physical
  output ifindex physical
  sample-header size 128
  if-counters polling-interval 30
  extended-router
  extended-gateway
!
exporter SFlowExporter
!
sampler-map SFlowSampler
random 1 out-of 5000
 
interface HundredGigE0/0/0/29.555
flow datalinkframesection monitor SFlowMonitor sampler SFlowSampler ingress
# repeat for all physical interfaces (wildcard?)
```
