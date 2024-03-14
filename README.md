# Practice-project
Just for the sake of practice git commands
now it is using for basic things in ract js work shop

set wsc = CreateObject("WScript.shell")
Do
WScript.Sleep (60*1000)
wsc.SendKeys ("{SCROLLLOCK 2}")
Loop

node = node2
server = server2
host = host2
hostname = host.upper()

print("[-nodeName {} -serverName {} -genericJvmArguments "-Dsvc_name=appsvr_{} -DTOP=/opt/IBM/MDM -DCCD_ETC_DIR=/opt/IBM/MDM/etc -Dsvc_etc_dir=/opt/IBM/MDM/etc/default -Dtrigo.memflags=-Xmx2048m_-Xms256m -Djava.security.policy=/opt/IBM/MDM/etc/default/java.policy -Dexit_if_config_file_not_found=false -DenableJava2Security=true -Dsysout.dir=/opt/IBM/MDM/logs/appsvr_{} -Dlog4j2.disable.jmx=true -Dclient.encoding.override=UTF-8".format(hostname, hostname)]".format(node, server))


node = node2
server = server2
host = host2
hostname = host.upper()

# Define the generic JVM arguments string
jvm_arguments = "-Dsvc_name=appsvr_{} -DTOP=/opt/IBM/MDM -DCCD_ETC_DIR=/opt/IBM/MDM/etc -Dsvc_etc_dir=/opt/IBM/MDM/etc/default -Dtrigo.memflags=-Xmx2048m_-Xms256m -Djava.security.policy=/opt/IBM/MDM/etc/default/java.policy -Dexit_if_config_file_not_found=false -DenableJava2Security=true -Dsysout.dir=/opt/IBM/MDM/logs/appsvr_{} -Dlog4j2.disable.jmx=true -Dclient.encoding.override=UTF-8".format(hostname, hostname)

# Print the formatted output with node and server names
print("[-nodeName {} -serverName {} -genericJvmArguments {}]".format(node, server, jvm_arguments))

