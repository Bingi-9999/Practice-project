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
