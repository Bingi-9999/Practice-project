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


- name: Ensure virtualenv is sourced from the .bashrc
  blockinfile:
    dest: "/root/.bashrc"
    block: |
      export TOP=/opt/IBM/MDM
      . /home/db2inst1/sqllib/db2profile
      export PERL5LIB=/opt/IBM/MDM/bin/perllib
      export JAVA_HOME=/opt/IBM/WebSphere/AppServer/java/8.0/bin/java

    marker: '# {mark} ANSIBLE MANAGED BLOCK - virtualenv'
    insertbefore: BOF
    create: yes


- name: Add new host to cluster
  xml:
    path: /path/to/your/file.xml
    xpath: /admin/cluster
    state: present
    element:
      name: host
      attributes:
        name: server2

- name: Verify changes
  xml:
    path: /path/to/your/file.xml
    xpath: /admin/cluster/host[@name="server2"]
    state: present

- name: Modify <db_url> element in db_config.xml
  xml:
    path: /path/to/your/db_config.xml
    xpath: /db_config/db_url
    state: present
    value: "jdbc:db2://10.116.102.41:25010/PIMDB:clientRerouteAlternateServerName=10.116.102.33;clientRerouteAlternatePortNumber=25010;"



  fatal: [10.119.154.94]: FAILED! => {"changed": false, "msg": "Unsupported parameters for (xml) module: element. Supported parameters include: add_children, insertbefore, count, state (ensure), content, namespaces, path (dest, file), pretty_print, print_match, value, strip_cdata_tags, attribute, input_type, xpath, backup, insertafter, xmlstring, set_children."}



An exception occurred during task execution. To see the full traceback, use -vvv. The error was: ModuleNotFoundError: No module named 'lxml'
fatal: [10.119.154.94]: FAILED! => {"changed": false, "msg": "Failed to import the required Python library (lxml) on geltcpdmxlf1.dnbapp.net's Python /usr/libexec/platform-python. Please read the module 




documentation and install it in the appropriate location. If the required library is installed, but Ansible is using the wrong Python interpreter, please consult the documentation on ansible_python_interpreter"}



- name: Add new element to admin_properties.xml
  xml:
    path: /opt/IBM/MDM/etc/default/admin_properties.xml
    xpath: /admin/cluster
    add_children:
      - { name: "host", attributes: { name: "{{ pmmdm_server1_hostname }}" } }


fatal: [10.119.154.11]: FAILED! => {"changed": true, "cmd": ["/data/db2_binary/V11.5/instance/db2icrt", "-u", "db2fenc1", "db2inst1"], "delta": "0:00:02.170827", "end": "2024-04-04 08:41:09.693168", "msg": "non-zero return code", "rc": 1, "start": "2024-04-04 08:41:07.522341", "stderr": "", "stderr_lines": [], "stdout": "DB2 installation is being initialized.\n\n The host name \"geltcpdbxlb2.dnbapp.net\" is invalid. Specify a valid host name.\n\nA major error occurred during the execution that caused this program to\nterminate prematurely. If the problem persists, contact your technical service\nrepresentative.\n\nFor more information see the DB2 installation log at \"/tmp/db2icrt.log.102007\".\nDBI1446I  The db2icrt command is running.\n\n\nDBI1264E  This program failed. Errors encountered during execution were\n      written to the installation log file. Program name:\n      db2icrt. Log file name: /tmp/db2icrt.log.102007.\n\nExplanation: \n\nThis message is returned when some processes and operations have failed.\nDetailed information about the error was written to the log file.\n\nUser response: \n\nContact IBM support to get assistance in resolving this issue. Keep the\nlog file intact as this file is an important reference for IBM support.\n\n\n   Related information:\n   Contacting IBM Software Support", "stdout_lines": ["DB2 installation is being initialized.", "", " The host name \"geltcpdbxlb2.dnbapp.net\" is invalid. Specify a valid host name.", "", "A major error occurred during the execution that caused this program to", "terminate prematurely. If the problem persists, contact your technical service", "representative.", "", "For more information see the DB2 installation log at \"/tmp/db2icrt.log.102007\".", "DBI1446I  The db2icrt command is running.", "", "", "DBI1264E  This program failed. Errors encountered during execution were", "      written to the installation log file. Program name:", "      db2icrt. Log file name: /tmp/db2icrt.log.102007.", "", "Explanation: ", "", "This message is returned when some processes and operations have failed.", "Detailed information about the error was written to the log file.", "", "User response: ", "", "Contact IBM support to get assistance in resolving this issue. Keep the", "log file intact as this file is an important reference for IBM support.", "", "", "   Related information:", "   Contacting IBM Software Support"]}

  -bash: export CCD_CONFIG_DIR=/opt/IBM/MDM/cluster/geltcpdmxlf1: No such file or directory
-bash: . /opt/IBM/WebSphere/AppServer/profiles/AppSrv01Host01/bin/setupCmdLine.sh: No such file or directory



