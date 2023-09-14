'''Arista 7504R'''
{{{
sflow sample 10000
sflow polling-interval 20
sflow destination 140.221.250.106
sflow source-interface Loopback0
sflow run
sflow extension bgp
}}}
