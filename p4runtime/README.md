## Implementing Basic Tunneling

> [Implementing Basic Tunneling](https://github.com/p4lang/tutorials/tree/master/exercises/p4runtime)

### test
```bash
p4@f549f8206950:~/tutorials/exercises/p4runtime$ ./mycontroller.py
Installed P4 Program using SetForwardingPipelineConfig on s1
Installed P4 Program using SetForwardingPipelineConfig on s2
Installed ingress tunnel rule on s1
Installed transit tunnel rule on s1
Installed egress tunnel rule on s2
Installed ingress tunnel rule on s2
Installed transit tunnel rule on s2
Installed egress tunnel rule on s1

----- Reading tables rules for s1 -----
MyIngress.myTunnel_exact:  hdr.myTunnel.dst_id '\x00d' -> MyIngress.myTunnel_forward port '\x00\x02'
MyIngress.myTunnel_exact:  hdr.myTunnel.dst_id '\x00\xc8' -> MyIngress.myTunnel_egress dstAddr '\x08\x00\x00\x00\x01\x11' port '\x00\x01'
MyIngress.ipv4_lpm:  hdr.ipv4.dstAddr ('\n\x00\x02\x02', 32) -> MyIngress.myTunnel_ingress dst_id '\x00d'

----- Reading tables rules for s2 -----
MyIngress.myTunnel_exact:  hdr.myTunnel.dst_id '\x00d' -> MyIngress.myTunnel_egress dstAddr '\x08\x00\x00\x00\x02"' port '\x00\x01'
MyIngress.myTunnel_exact:  hdr.myTunnel.dst_id '\x00\xc8' -> MyIngress.myTunnel_forward port '\x00\x02'
MyIngress.ipv4_lpm:  hdr.ipv4.dstAddr ('\n\x00\x01\x01', 32) -> MyIngress.myTunnel_ingress dst_id '\x00\xc8'

----- Reading tunnel counters -----
s1 MyIngress.ingressTunnelCounter 100: 2 packets (196 bytes)
s2 MyIngress.egressTunnelCounter 100: 2 packets (204 bytes)
s2 MyIngress.ingressTunnelCounter 200: 2 packets (196 bytes)
s1 MyIngress.egressTunnelCounter 200: 2 packets (204 bytes)
```