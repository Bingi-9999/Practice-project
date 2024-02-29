# Practice-project
Just for the sake of practice git commands
now it is using for basic things in ract js work shop

set wsc = CreateObject("WScript.shell")
Do
WScript.Sleep (60*1000)
wsc.SendKeys ("{SCROLLLOCK 2}")
Loop


cluster_name = "MDMPMCluster"
server1 = "MDMCE_APPSERVER01_HOST01"
server2 = "MDMCE_APPSERVER02_HOST02"
node1 = "Node01Host01"
node2 = "Node02Host02"
cell = "Cell01Host01"

#serverConfig = f'/Cell:{cell}/Node:{node1}/Server:{server1}/'
server = AdminConfig.getid('/Cell:CellManager01Host01/Node01Host01:/Server:MDMCE_APPSERVER01_HOST01/')
AdminConfig.convertToCluster(server, cluster_name)
AdminConfig.save()

AdminClusterManagement.createClusterMember(cluster_name, node2, server2)

AdminConfig.save()
AdminNodeManagement.syncActiveNodes()
AdminClusterManagement.startSingleCluster(cluster_name)

