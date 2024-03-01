# Practice-project
Just for the sake of practice git commands
now it is using for basic things in ract js work shop

set wsc = CreateObject("WScript.shell")
Do
WScript.Sleep (60*1000)
wsc.SendKeys ("{SCROLLLOCK 2}")
Loop


db2 connect to {{ item.name }}
db2 update db cfg for {{ item.name }} using HADR_LOCAL_HOST {{ db_server1_hostname }}
db2 update db cfg for {{ item.name }} using HADR_LOCAL_SVC  {{ item.primary }}
db2 update db cfg for {{ item.name }} using HADR_REMOTE_HOST {{ db_server2_hostname }}
db2 update db cfg for {{ item.name }} using HADR_REMOTE_SVC {{ item.standby }}
db2 update db cfg for {{ item.name }} using HADR_REMOTE_INST db2inst1
db2 update db cfg for {{ item.name }} using HADR_TARGET_LIST '{{ db_server2_hostname }}:{{ item.standby }}'
db2 update db cfg for {{ item.name }} using HADR_TIMEOUT 120
db2 update db cfg for {{ item.name }} using HADR_SYNCMODE NEARSYNC
db2 update db cfg for {{ item.name }} using HADR_SPOOL_LIMIT 100000
db2 update db cfg for {{ item.name }} using HADR_PEER_WINDOW 300
db2 update db cfg for {{ item.name }} using LOGINDEXBUILD ON
db2 update db cfg for {{ item.name }} using INDEXREC RESTART
db2 update db cfg for {{ item.name }} using LOGARCHMETH1 'DISK:/data/db2_archivelogs/{{ item.name }}'
db2 terminate
db2stop
db2start
db2 connect to {{ item.name }}
db2 get db cfg for {{ item.name }} show detail|grep -i HADR
db2 terminate

db2 restore database {{ item.name }} from /data/db2_backup without prompting
db2 update db cfg for {{ item.name }} using HADR_LOCAL_HOST {{ db_server2_hostname }}
db2 update db cfg for {{ item.name }} using HADR_LOCAL_SVC {{ item.standby }}
db2 update db cfg for {{ item.name }} using HADR_REMOTE_HOST {{ db_server1_hostname }}
db2 update db cfg for {{ item.name }} using HADR_REMOTE_SVC {{ item.primary }}
db2 update db cfg for {{ item.name }} using HADR_REMOTE_INST db2inst1
db2 update db cfg for {{ item.name }} using HADR_TARGET_LIST '{{ db_server1_hostname }}:{{ item.primary }}'
db2 update db cfg for {{ item.name }} using HADR_TIMEOUT 120
db2 update db cfg for {{ item.name }} using HADR_SYNCMODE NEARSYNC
db2 update db cfg for {{ item.name }} using HADR_SPOOL_LIMIT 100000
db2 update db cfg for {{ item.name }} using HADR_PEER_WINDOW 300
db2 update db cfg for {{ item.name }} using LOGINDEXBUILD ON
db2 update db cfg for {{ item.name }} using INDEXREC RESTART
db2 terminate


