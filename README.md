# Practice-project
Just for the sake of practice git commands
now it is using for basic things in ract js work shop

set wsc = CreateObject("WScript.shell")
Do
WScript.Sleep (60*1000)
wsc.SendKeys ("{SCROLLLOCK 2}")
Loop


fatal: [10.119.154.42]: FAILED! => {"changed": true, "cmd": "/opt/IBM/WebSphere/AppServer/bin/wsadmin.sh -lang jython -username wasadmin -password wasadmin -f /opt/IBM/WebSphere/AppServer/was_cluster_creation.py", "delta": "0:00:08.599872", "end": "2024-02-29 15:31:02.651530", "msg": "non-zero return code", "rc": 105, "start": "2024-02-29 15:30:54.051658", "stderr": "", "stderr_lines": [], "stdout": "WASX7209I: Connected to process \"dmgr\" on node CellManager01Host01 using SOAP connector;  The type of process is: DeploymentManager\nWASX7017E: Exception received while running file \"/opt/IBM/WebSphere/AppServer/was_cluster_creation.py\"; exception information: com.ibm.websphere.management.exception.InvalidConfigDataTypeException: ADMG0007E: The configuration data type Node01Host01 is not valid.", "stdout_lines": ["WASX7209I: Connected to process \"dmgr\" on node CellManager01Host01 using SOAP connector;  The type of process is: DeploymentManager", "WASX7017E: Exception received while running file \"/opt/IBM/WebSphere/AppServer/was_cluster_creation.py\"; exception information: com.ibm.websphere.management.exception.InvalidConfigDataTypeException: ADMG0007E: The configuration data type Node01Host01 is not valid."]}

