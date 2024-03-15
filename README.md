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
fatal: [10.119.154.94]: FAILED! => {"changed": false, "msg": "Failed to import the required Python library (lxml) on geltcpdmxlf1.dnbapp.net's Python /usr/libexec/platform-python. Please read the module documentation and install it in the appropriate location. If the required library is installed, but Ansible is using the wrong Python interpreter, please consult the documentation on ansible_python_interpreter"}

