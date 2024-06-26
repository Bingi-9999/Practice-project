First, get the code on your system! The simplest method is via git:
- `cd /opt`
- `git clone https://github.com/dnb-main/ltc-css-infrastructure.git`
- `cd ltc-css-infrastructure`
- `ansible-playbook cmdm_db2_playbook.yaml`
- `ansible-playbook cmdm_playbook.yaml`
- `ansible-playbook baw_playbook.yaml`



.
├── ansible.cfg
├── my_hosts
│   └── hosts
├── pmdb_db2HA.yaml
├── productmaster-ha.yaml
└── roles
    ├── db2HA
    │   ├── defaults
    │   │   └── main.yml
    │   ├── files
    │   │   ├── create_bufferpools.sql
    │   │   ├── CreateDB_PIMDB.sql
    │   │   ├── create_tablespaces.sql
    │   │   ├── grant_access_to_tablespaces.sql
    │   │   ├── PIMDB_db_backup.tar.gz
    │   │   └── update_database_configuration_parameters.sql
    │   ├── handlers
    │   │   └── main.yml
    │   ├── meta
    │   │   └── main.yml
    │   ├── README.md
    │   ├── tasks
    │   │   ├── 1-db-install.yaml
    │   │   ├── 2-db-install.yaml
    │   │   ├── 3-pmdb.yaml
    │   │   ├── 4-hadr-setup.yaml
    │   │   ├── 5-hadr-enable.yaml
    │   │   ├── db2_check.yaml
    │   │   ├── db2jcc_jar_check.yaml
    │   │   └── main.yml
    │   ├── templates
    │   │   ├── db2server.rsp
    │   │   ├── hadr_parameter_auxilary.sh
    │   │   ├── hadr_parameter_primary.sh
    │   │   └── hadr_parameter_standby.sh
    │   └── vars
    │       └── main.yml
    └── pmdmha
        ├── defaults
        │   └── main.yml
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── README.md
        ├── tasks
        │   ├── 10_product-master-fixpack-install-N1.yaml
        │   ├── 11_WAS-config-N2.yaml
        │   ├── 12_WAS_Cluster_Config.yaml
        │   ├── 13_product-master-conf.yaml
        │   ├── 14_bashrc_setup.yaml
        │   ├── 15_product-master-conf-2.yaml
        │   ├── 16_product-master-conf-3.yaml
        │   ├── 17_product-master-conf-4.yaml
        │   ├── 18_enabling-ACR.yaml
        │   ├── 1_db-client-install.yaml
        │   ├── 2_IM-install.yaml
        │   ├── 3_WAS-install.yaml
        │   ├── 4_nfs-setup.yaml
        │   ├── 5_perl-install.yaml
        │   ├── 6_WAS-config-N1.yaml
        │   ├── 7_1a-product-master-install-N1.yaml
        │   ├── 8_1b-product-master-install-N1.yaml
        │   ├── 9_1c-product-master-install-N1.yaml
        │   └── main.yml
        ├── templates
        │   ├── appsrv_expect.exp
        │   ├── company_expect.exp
        │   ├── config.sh.j2
        │   ├── db2client.rsp
        │   ├── env_settings-fixpack.j2
        │   ├── env_settings.j2
        │   ├── ibmimresponsefile.xml
        │   ├── install_pm_expect.exp
        │   ├── migrate_expect.exp
        │   ├── myconfig.j2
        │   ├── perl_expect.exp
        │   ├── schema_expect.exp
        │   ├── vhost_expect.exp
        │   ├── war_expect.exp
        │   ├── war_expect_fix.exp
        │   ├── was_cluster_creation.py
        │   ├── was_jvm.py
        │   └── was_nd.xml
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml

18 directories, 71 files


https://github.com/dnb-main/css-ltc-pmdm-infra.git



[venkatasainathb@geltcpdbxl00 pmdm-ha-feb16]$ ansible-playbook pmdb_db2HA.yaml
[DEPRECATION WARNING]: Ansible will require Python 3.8 or newer on the controller starting with Ansible 2.12. Current version: 3.6.8 (default, Jan  5 2024, 08:58:17) [GCC 8.5.0 20210514
(Red Hat 8.5.0-20)]. This feature will be removed from ansible-core in version 2.12. Deprecation warnings can be disabled by setting deprecation_warnings=False in ansible.cfg.
/home/venkatasainathb/.local/lib/python3.6/site-packages/ansible/parsing/vault/__init__.py:44: CryptographyDeprecationWarning: Python 3.6 is no longer supported by the Python core team. Therefore, support for it is deprecated in cryptography. The next release of cryptography will remove support for Python 3.6.
  from cryptography.exceptions import InvalidSignature

PLAY [db2HA] ********************************************************************************************************************************************************************************

TASK [Gathering Facts] **********************************************************************************************************************************************************************
ok: [10.119.154.12]
ok: [10.119.154.3]

TASK [db2HA : Get stats of the DB2] *********************************************************************************************************************************************************
ok: [10.119.154.12]
ok: [10.119.154.3]



[venkatasainathb@geltcpdbxl00 pmdm-ha-feb16]$ ansible-playbook productmaster-ha.yaml
[DEPRECATION WARNING]: Ansible will require Python 3.8 or newer on the controller starting with Ansible 2.12. Current version: 3.6.8 (default, Jan  5 2024, 08:58:17) [GCC 8.5.0 20210514
(Red Hat 8.5.0-20)]. This feature will be removed from ansible-core in version 2.12. Deprecation warnings can be disabled by setting deprecation_warnings=False in ansible.cfg.
/home/venkatasainathb/.local/lib/python3.6/site-packages/ansible/parsing/vault/__init__.py:44: CryptographyDeprecationWarning: Python 3.6 is no longer supported by the Python core team. Therefore, support for it is deprecated in cryptography. The next release of cryptography will remove support for Python 3.6.
  from cryptography.exceptions import InvalidSignature

PLAY [pmHA] *********************************************************************************************************************************************************************************

TASK [Gathering Facts] **********************************************************************************************************************************************************************
ok: [10.119.154.6]
ok: [10.119.154.8]

TASK [pmdmha : Update pam] ******************************************************************************************************************************************************************
ok: [10.119.154.6]

