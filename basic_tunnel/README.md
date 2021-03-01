## Implementing Basic Forwarding

> [Implementing Basic Tunneling](https://github.com/p4lang/tutorials/tree/master/exercises/basic_tunnel)

### mininet
```bash
mininet> pingall
*** Ping: testing ping reachability
h1 -> h2 h3
h2 -> h1 h3
h3 -> h1 h2
*** Results: 0% dropped (6/6 received)
mininet> nodes
available nodes are:
h1 h2 h3 s1 s2 s3
mininet> dump
<P4Host h1: eth0:10.0.1.1 pid=7855>
<P4Host h2: eth0:10.0.2.2 pid=7857>
<P4Host h3: eth0:10.0.3.3 pid=7859>
<ConfiguredP4RuntimeSwitch s1: lo:127.0.0.1,s1-eth1:None,s1-eth2:None,s1-eth3:None pid=7861>
<ConfiguredP4RuntimeSwitch s2: lo:127.0.0.1,s2-eth1:None,s2-eth2:None,s2-eth3:None pid=7865>
<ConfiguredP4RuntimeSwitch s3: lo:127.0.0.1,s3-eth1:None,s3-eth2:None,s3-eth3:None pid=7869>
mininet>
```