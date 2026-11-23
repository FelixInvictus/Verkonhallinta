Verkonhallinta week04

04.1

Routers, client workstations, servers, monitoring infrastructure. management tools, network segments, infrastructure groups, node exporter targets, all nodes.
Ryhmät on muodostettu vastaamaan käyttötarkoitusta ja laitetyyppiä.
Ryhmien avulla löytää tiedot helpommin.

04.2

Pingaa saatavilla olevia palvelimia.
Playbook ei saa yhteyttä moneen palvelimeen.

04.3

apt, copy, service, shell, register, debug, notify, changed_when, file, get_url, unarchive, args, url
vars muuttujat määrittelevät käytössä olevan node_exporter version ja snmp_community tilan.
Handlers takaa löytyy snmpd restart service.

04.4

root@ansible:/ansible/playbooks# ansible-playbook -i ../inventory.ini install-webserver.yml

PLAY [Install and config Nginx server] *******************************************************************************

TASK [Update apt package cache] **************************************************************************************
ok: [web1]

TASK [Install Nginx web server] **************************************************************************************
ok: [web1]

TASK [Ensure web root directory exists] ******************************************************************************
ok: [web1]

TASK [Create index.html displaying the server hostname] **************************************************************
ok: [web1]

TASK [Ensure Nginx service is started and enabled at boot] ***********************************************************
ok: [web1]

TASK [Verify web server responds with HTTP 200 and expected hostname] ************************************************
ok: [web1]

PLAY RECAP ***********************************************************************************************************
web1                       : ok=6    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

root@ansible:/ansible/playbooks#

04.5

Ubuntu Debian
ansible_all_ipv4_addresses: 172.20.20.3 , 10.10.20.101
16 prosessoria
16 ram
