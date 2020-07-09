#/bin/bash
#install zabbix-agent
#version:v1.0.0


IP_ADDR=`ip addr|grep eth0 |grep inet|awk '{print $2}'|awk -F'/' '{ print $1}'`

HOSTNAME=`cat /etc/hostname`

ZABBIX_AGENT=/opt/zabbix-agent

CONF=${ZABBIX_AGENT}/conf/zabbix_agentd.conf

sed -i "s/SourceIP=192.168.0.103/SourceIP=${IP_ADDR}/g" $CONF

sed -i "s/Hostname=yinshipin/Hostname=${HOSTNAME}/g" $CONF

${ZABBIX_AGENT}/sbin/zabbix_agentd -c ${CONF}
