Verkonhallinta week02-snmp

02.2

ojala@LAPTOP-GQU0QQCT:~/Verkonhallinta/Verkonhallinta$ docker exec -it clab-hamk-verkonhallinta-golden-web1 bash
root@web1:/# apt update
apt install snmp snmpd -y
Hit:1 http://security.ubuntu.com/ubuntu noble-security InRelease
Hit:2 http://archive.ubuntu.com/ubuntu noble InRelease
Hit:3 http://archive.ubuntu.com/ubuntu noble-updates InRelease
Hit:4 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
23 packages can be upgraded. Run 'apt list --upgradable' to see them.
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
snmp is already the newest version (5.9.4+dfsg-1.1ubuntu3.3).
snmpd is already the newest version (5.9.4+dfsg-1.1ubuntu3.3).
0 upgraded, 0 newly installed, 0 to remove and 23 not upgraded.
root@web1:/# service snmpd status
 * snmpd is running
root@web1:/# nano /etc/snmp/snmpd.conf
bash: nano: command not found
root@web1:/# rocommunity public
bash: rocommunity: command not found
root@web1:/# service snmpd restart
 * Restarting SNMP Services snmpd                                                                                   [ OK ]
root@web1:/# ps aux | grep snmpd
Debian-+    4383  0.0  0.0  20108  7752 ?        S    10:03   0:00 /usr/sbin/snmpd -LSwd -Lf /dev/null -u Debian-snmp -g Debian-snmp -I -smux mteTrigger mteTriggerConf -p /run/snmpd.pid
root        4385  0.0  0.0   3536  1852 pts/1    S+   10:03   0:00 grep --color=auto snmpd
root@web1:/#

02.3

root@ansible:/# snmpwalk -v2c -c public web1 .1.3.6.1.2.1.1.5.0
Timeout: No Response from web1
root@ansible:/# snmpwalk -v2c -c public web1 .1.3.6.1.2.1.1
Timeout: No Response from web1
root@ansible:/# snmpwalk -v2c -c public web1 system
Timeout: No Response from web1
root@ansible:/# snmpwalk -v2c -c public web1 system
Timeout: No Response from web1
root@ansible:/#

Kokeilin useaan kertaan käyttää kaiken läpi Raulin kanssa, samoilla komennoilla mitä hän käytti, mutta tulos on sama ja komennot eivät toimi.

Tein loppuun paritehtävänä Raulin kanssa.
