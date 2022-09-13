==========================
Install Monitor adapters
==========================

| This section explains how to add monitor adapters for Exastro OASE environments.
| This section can be skipped if the user's desired monitor adapter is already installed.
| Note that this manual uses the Installer version of OASE (Not the container version) as an example.

Extract Monitor adapter files
======================

| The Monitor adapter resources are stored in the Exastro OASE installation path.
| The Monitor adapter files must be extracted before they can be installed.

.. tip::
   | The installation directory is as follows.
   | Exastro OASE: **/exastro**
   | JBoss (WildFly): **/exastro/JBoss**

.. code-block:: bash

   # Switch to root
   sudo su -
   
   # Save the Exastro OASE isntallation directory in variables
   # E.g.) If installed to /exastro
   INSTALLATION_PATH=/exastro
   
   # Move to the directory with the Installer
   cd ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents

   # Extract the Monitor adapter files
   tar zxf ZABBIX_Adapter.tar.gz
   tar zxf Prometheus_Adapter.tar.gz
   tar zxf Grafana_Adapter.tar.gz
   tar zxf Datadog_Adapter.tar.gz
   tar zxf Mail_Adapter.tar.gz

Install monitor adapters
==========================

| When installing a monitor adapter, you must specify one of the following Monitor adapter IDs as an option.

.. csv-table:: Monitor adapter ID
   :header: Monitor adapter ID,Monitor adapter,Version
   :widths: 20, 40, 30

   1, Zabbix Adapter, v1
   2, Prometheus Adapter, v1
   3, Grafana Adapter, v1
   4, Datadog Adapter, v1
   5, Mail adapter, v1


.. code-block:: bash

   # Move to Exastro OASE main project directory
   cd ${INSTALLATION_PATH}/oase/oase-root

   # Install Monitor adapter
   python3 manage.py adapter_installer -p [plugins path] -i [Monitor adapter ID]

   # E.g.) Install Zabbix adapter
   python3 manage.py adapter_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -i 1

