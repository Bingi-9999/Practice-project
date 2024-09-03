ERROR! couldn't resolve module/action 'xml'. This often indicates a misspelling, missing collection, or incorrect module path.

The error appears to be in '/home/venkatasainathb/pmdm-latest/roles/productmaster/tasks/9-enabling-ACR.yaml': line 3, column 3, but may
be elsewhere in the file depending on the exact syntax problem.

The offending line appears to be:


- name: Modify db_url element in db.xml
  
  - name: Modify db_url element in db.xml
  xml:
    path: /opt/IBM/MDM/etc/default/db.xml
    xpath: /db_config/db_url
    state: present
    value: "jdbc:db2://{{ db_server1_ip }}:{{ db_server1_port }}/PIMDB:clientRerouteAlternateServerName={{ db_server2_ip }};clientRerouteAlternatePortNumber={{ db_server2_port }};"
  when: inventory_hostname == "{{ pmmdm_server1_ip }}"
