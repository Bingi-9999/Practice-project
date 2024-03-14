# Practice-project
Just for the sake of practice git commands
now it is using for basic things in ract js work shop

set wsc = CreateObject("WScript.shell")
Do
WScript.Sleep (60*1000)
wsc.SendKeys ("{SCROLLLOCK 2}")
Loop

    - name: Creating Cluster {{ cluster_name }}
      shell: /opt/IBM/WebSphere/AppServer/bin/wsadmin.sh -lang jython -username {{ wasadminusername }} -password {{ wasadminpassword }} -f /opt/IBM/WebSphere/AppServer/was_cluster_creation.py
      ignore_errors: yes
      register: cluster_output

    - debug:
        var: cluster_output.stdout_lines
