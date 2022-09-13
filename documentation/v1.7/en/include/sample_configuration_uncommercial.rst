.. code-block:: bash
   :caption: oase_answers.txt

   # Select install mode.
   # ("Install_Online","Install_Offline","Gather_Library","Versionup_All", "Versionup_OASE", "Uninstall")
   # e.g) install_mode:Install_Online
   install_mode:Install_Online


   ##############################
   # RabbitMQ
   ##############################
   # Decide the RabbitMQ_username.
   # e.g) RabbitMQ_username:sample_rabbitmq_username
   RabbitMQ_username:admin

   # Decide the RabbitMQ_password.
   # e.g) RabbitMQ_password:sample_rabbitmq_password
   RabbitMQ_password:password


   # Decide the RabbitMQ_queuename.
   # e.g) RabbitMQ_queuename:oase
   RabbitMQ_queuename:oase

   # Enter IP address for RabbitMQ.
   # e.g) RabbitMQ_ipaddr:127.0.0.1
   RabbitMQ_ipaddr:127.0.0.1

   ##############################
   # MariaDB
   ##############################
   # Enter the MariaDB root user's password
   # e.g) db_root_password:sample_root_password
   db_root_password:password

   # Decide the database name, username, and password for OASE.
   # e.g) db_name:sample_db_name
   db_name:OASE_DB
   # e.g) db_username:sample_db_username
   db_username:OASE_USER
   # e.g) db_password:sample_db_password
   db_password:OASE_PASSWD

   # In uninstall mode,
   # Select "erase" or "leave" oase database
   # e.g) db_erase:erase
   db_erase:erase


   ##############################
   # JBoss
   ##############################
   # Enter JBoss install directory.
   # e.g) jboss_root_directory:/exastro/JBoss
   jboss_root_directory:/exastro/JBoss


   ##############################
   # Rules Engine
   ##############################
   # Rules engine to be used.("rhdm" or "drools")
   # e.g) rules_engine:drools
   rules_engine:drools

   # Decide the Administrator name, password.
   # e.g) rule_engine_adminname:admin0000
   rule_engine_adminname:admin0000
   # e.g) rule_engine_password:password@1
   rule_engine_password:password@1

   # Enter IP address & port for Rule Engine.
   # e.g) rule_engine_ipaddrport:localhost:8080
   rule_engine_ipaddrport:localhost:8080


   ##############################
   # RHDM
   ##############################
   # Full path of RHDM materials.
   # e.g) rhdm_path:/tmp/rhdm-installer-x.x.x.jar
   rhdm_path:

   # Full path of jboss-eap materials.
   # Only used for RHDM.
   # e.g) jboss_eap_path:/tmp/jboss-eap-x.x.x-installer.jar
   jboss_eap_path:


   ##############################
   # RULEFILE
   ##############################
   # Enter root path for RULEFILE.
   # e.g) rulefile_rootpath:/exastro/rule
   rulefile_rootpath:/exastro/rule


   ##############################
   # APPLY
   ##############################
   # Enter IP address & port for APPLY SERVICE.
   # e.g) apply_ipaddrport:127.0.0.1:50001
   apply_ipaddrport:127.0.0.1:50001


   ##############################
   # Maven
   ##############################
   # Enter repository path for Maven.
   # e.g) mavenrep_path:/root/.m2/repository/com/oase/
   mavenrep_path:/root/.m2/repository/com/oase/


   ##############################
   # OASE mail SMTP settings
   ##############################
   # Enter smtp settings.
   # e.g) oasemail_smtp:"{'IPADDR':'127.0.0.1','PORT':25,'AUTH':False}"
   oasemail_smtp:"{'IPADDR':'127.0.0.1','PORT':25,'AUTH':False}"


   ##############################
   # OASE install directory
   ##############################
   # Enter OASE install directory.
   # e.g) oase_directory:/exastro
   oase_directory:/exastro


   ##############################
   # settings.py
   ##############################
   # Decide the EVTIMER SERVER location
   # e.g) ev_location:127.0.0.1
   ev_location:127.0.0.1

   # Select language. ("en_US" or "ja_JP")
   # e.g) oase_language:en_US
   oase_language:ja_JP

   # Select Operation System. ("CentOS7" or "RHEL7" or "RHEL8")
   # e.g) oase_os:RHEL7
   oase_os:CentOS7

   # Enter time_zone.
   # e.g) time_zone:Asia/Tokyo
   oase_timezone:Asia/Tokyo


   ##############################
   # Installation package
   ##############################
   # Select the target you need to install.
   # yes : need
   # no  : no need
   oase_base:yes
   ita_driver:yes
   mail_driver:yes
   servicenow_driver:no
   zabbix_adapter:yes
   prometheus_adapter:no
   grafana_adapter:no


   ##############################
   # SSL server certificate
   ##############################
   # Enter the oase domain name.
   # e.g) oase_domain:exastro-oase.local
   oase_domain:exastro-oase.local

   # Enter when using user-specified certificates and private keys.
   # If no file path is entered for both "certificate_path" and "private_key_path",
   # the OASE installer creates and installs a self-certificate and private key
   # using the values entered in "oase_domain".

   # Enter the file path where the certificate to be install.
   # e.g) certificate_path:/temp/etc_pki_tls_certs/exastro-oase.crt
   certificate_path:

   # Enter the file path where the private key to be install.
   # e.g) private_key_path:/temp/etc_pki_tls_certs/exastro-oase.key
   private_key_path: