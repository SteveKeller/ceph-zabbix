# ceph-zabbix

A zabbix probe to get performance counters of ceph (Luminous 12.2+)


Installation
============

Install jq:
      sudo apt install jq

Copy the scripts, zabbix_agentd.conf.d into /etc/zabbix/

Check arguments: Server, Hostname, ListenIP in zabbix_agentd.conf

Check permission for read user zabbix /etc/ceph/<{$CLUSTER_NAME}>.client.admin.keyring


Sudoers
============

this allow the health check script run with root permissions,

add following line at the end of the file /etc/sudoers 

      zabbix ALL=NOPASSWD: /etc/zabbix/zabbix_agentd.scripts/ceph-data-health.sh
