# ip-conntrack-cacti-template

====
<br>
## Requirement<br>
OS:CentOS6<br>
Package:cacti-0.8.8b-7.el6.noarch<br>
<br>
## Install<br>
-- edit snmpd.conf<br>
$ cat snmpd.conf.add >> /etc/snmp/snmpd.conf<br>
<br>
-- check example<br>
$ cat /etc/snmp/snmpd.conf|grep ip_conntrack<br>
extend .1.3.6.1.4.1.18689.1.1 ip_conntrack /usr/local/bin/ip_conntrack<br>
<br>
-- copy ip_conntrack<br>
$ cp ip_conntrack /usr/local/bin/<br>
$ chmod 755 /usr/local/bin/ip_conntrack<br>
<br>
-- check example<br>
$ /usr/local/bin/ip_conntrack<br>
nf_conntrack_count:5623 nf_conntrack_max:360000<br>
<br>
##Note
ip conntrack/nf conntrack値を取得してみる。<br>

-- CentOS6の場合<br>
/proc/sys/net/netfilter/nf_conntrack_count<br>
/proc/sys/net/netfilter/nf_conntrack_max<br>

-- CentOS5の場合<br>
/proc/sys/net/ipv4/netfilter/ip_conntrack_count
/proc/sys/net/ipv4/netfilter/ip_conntrack_max
より取り出してみる。<br>

##参考
http://forums.cacti.net/about26714.html
