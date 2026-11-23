Verkonhallinta Teht01Documentation

01.1 - Topology

R1 - Client and attacker router
R2 - Main router
R3 - Branch client router
Client 1 - End client
Attacker - Security tester
Web1 - Server
Db1 - Database server
Branch-client - Non-lan connected end client
ansible - Network device management tool
Prometheus - Statistic manager
Grafana - Performance statistics manager
Zabbix - Infrastructure manager

01.2 

https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&dark=auto#R%3Cmxfile%3E%3Cdiagram%20name%3D%22Page-1%22%20id%3D%22IbD5Hi6-d80ZYtX5d62I%22%3E7VrBcpswEP0aH91BCIxzTGInzUzStHGnSU4d2ShAA8gjC2Pn6yuMZCBuUteDJOLpxcM%2BaSX8nna1CHrwPFldUjQPb4iP455t%2BaseHPVsezhw%2BG8BrEvA8ewSCGjklxCogEn0ggVoCTSLfLxodGSExCyaN8EZSVM8Yw0MUUryZrcnEjdnnaMA7wCTGYp30fvIZ6H4W65V4Z9xFIRyZmCJlgTJzgJYhMgneQ2C4x48p4Sw8ipZneO44E7yUvpdvNG6vTGKU7aPw9c7%2B%2FSLl9CL%2B5%2F3V2N7eZ3kt30XlsNgf4eGalwBLdhaslJ0nwiTUBaSgKQoHlfoGSVZ6uNiaotbVZ9rQuYcBBz8hRlbC8VRxgiHQpbEohWvIvYg3Ivrx%2BL6kyus0arWNFpLI2V0%2FSAHKIyaV2FWbhtL%2Bi0Youy0WC0cGN8lKPVvUywbLqI43rr5VTeS4u%2FkBqXrsqHWbasujwpMEszn4vxRHCMWLZs8I7E%2Bg22%2FSkJ%2BIVT8s6KXwdmP0dUzyPw8zr9Ns9Ozybgvl9teipKMzvA7g5lVfqv2Y13s95Wvif1YXwhvKF8TNCUbyXeV5BkH0QCz90g3qrhzNIpriPWWFB8YVdw9GsUbMQ4OinFLj%2BLAMyn5XttyU5Y8jBiezNFG%2FZxXZ00JSu8lijPpLSqzJaYMr2pz7P7nsFbyDMSGk1flkYTEIPBErNe1tC1VgWG3GBi22cDwPszud2I0F%2F5LBdtxye0PI%2FnQqOQaciHQlAttdbkQtBgY8H9ZuF%2BRYDIuoIa4gIriwpXnJuprhGGLcTHo0IaxZ%2FVsKDAcozvGydFo3siFXreTITSaDds8COuQ5na3NTd6FAbbrHm6lNv3fBgwpLnRqmegvupJgoT1p3NFpc%2F2EUB56TNUT9UsjvjYyp6e3CZVQBlVJ%2BqpQoyh2TOmirhyHF1cgTYravnitwtbbad3WqPFFbDeVrit%2BJhSlM7CfplRFAXJAOjKvUDDCT5KF9GUD3UIV84uV8MmV8B7xRVQxpWGE745LW42xNlCF12eMro0HPy8oOk0WmmiyoHKqHLUUxVQ9IRSpIsrdRnLVc%2BVPz2sVPw7TxA2eXLV8aThCSTHyohytBFlC6LaqRO9HYrNvZ7t9ocLZr9V8Y5I9EPO2w2J7poUXeqkMiUu6FLdmczr17SH7LLcrL7u3bTVPpGG498%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E

01.3

10.10.10.0/24 - User network - r1: 10.10.10.1, 10.10.10.254
Includes r1, client1, attacker.
r1 is connection.
Serves as simulated client and attacker network.
10.10.20.0/24 - Server network - r2: 10.10.20.1
Includes r2, web1, db1.
r2 is connection.
Serves as server network.
10.10.30.0/24 - Branch network - r3: 10.10.30.1
Includes r3, branch-client.
r3 is connection.
Serves as branch client netowowrk.
10.10.99.0/24 - Management LAN - r2: 10.10.99.1
Includes r2, ansible, Prometheus, cadvisor, Grafana, Zabbix, syslog.
r2 is connection.
Serves as management nodes.
10.255.12.0/30 - r1/r2 link - r1: 10.255.12.1, r2: 10.255.12.2
10.255.23.0/30 - r2/r3 link - r2: 10.255.23.1, r3: 10.255.23.2

01.4

Connected to all networks, except no access to management LAN.
Connection goes through at least r1 inside client and r2 outside client.
root@client1:/# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
29: eth0@if30: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default
    link/ether 02:42:ac:14:14:0c brd ff:ff:ff:ff:ff:ff link-netnsid 0
    inet 172.20.20.12/24 brd 172.20.20.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:acff:fe14:140c/64 scope link
       valid_lft forever preferred_lft forever
58: eth1@if57: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9500 qdisc noqueue state UP group default
    link/ether aa:c1:ab:fa:3d:23 brd ff:ff:ff:ff:ff:ff link-netnsid 1
    altname clab-o-05031180f95d8850
    inet 10.10.10.101/24 scope global eth1
       valid_lft forever preferred_lft forever
    inet6 fe80::a8c1:abff:fefa:3d23/64 scope link
       valid_lft forever preferred_lft forever
root@client1:/# ip route
default via 10.10.10.1 dev eth1
10.10.10.0/24 dev eth1 proto kernel scope link src 10.10.10.101
172.20.20.0/24 dev eth0 proto kernel scope link src 172.20.20.12
root@client1:/# ping -c 4 10.10.20.101
PING 10.10.20.101 (10.10.20.101) 56(84) bytes of data.
64 bytes from 10.10.20.101: icmp_seq=1 ttl=62 time=0.848 ms
64 bytes from 10.10.20.101: icmp_seq=2 ttl=62 time=0.105 ms
64 bytes from 10.10.20.101: icmp_seq=3 ttl=62 time=0.160 ms
64 bytes from 10.10.20.101: icmp_seq=4 ttl=62 time=0.140 ms

--- 10.10.20.101 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3076ms
rtt min/avg/max/mdev = 0.105/0.313/0.848/0.309 ms
root@client1:/# ping -c 4 10.10.30.101
PING 10.10.30.101 (10.10.30.101) 56(84) bytes of data.
64 bytes from 10.10.30.101: icmp_seq=1 ttl=61 time=0.376 ms
64 bytes from 10.10.30.101: icmp_seq=2 ttl=61 time=0.157 ms
64 bytes from 10.10.30.101: icmp_seq=3 ttl=61 time=0.132 ms
64 bytes from 10.10.30.101: icmp_seq=4 ttl=61 time=0.134 ms

--- 10.10.30.101 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3061ms
rtt min/avg/max/mdev = 0.132/0.199/0.376/0.102 ms
root@client1:/# traceroute 10.10.30.101
traceroute to 10.10.30.101 (10.10.30.101), 30 hops max, 60 byte packets
 1  10.10.10.1 (10.10.10.1)  1.367 ms  1.169 ms  1.140 ms
 2  10.255.12.2 (10.255.12.2)  1.120 ms  0.925 ms  0.892 ms
 3  10.255.23.2 (10.255.23.2)  0.868 ms  0.067 ms  0.058 ms
 4  10.10.30.101 (10.10.30.101)  0.040 ms  0.026 ms  0.023 ms
