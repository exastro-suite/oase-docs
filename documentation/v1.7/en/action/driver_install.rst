==========================
Install Link Driver
==========================

| This manual explains how to add Link drivers to Exastro OASE.
| This section can be skipped if user's desired Link driver is already installed.
| Note that this manual uses the Installer version of OASE (Not the container version) as an example.

Extract Link driver files
======================

| The Link Driver resources are stored in the Exastro OASE installation path.
| The Link Driver files must be extracted before they can be installed.

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
   
   # Move to Installer directory
   cd ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents

   # Extract the Link Driver files

   tar zxf ITA_Driver.tar.gz
   tar zxf mail_Driver.tar.gz
   tar zxf ServiceNow_Driver.tar.gz

Install Link Driver
==========================

| When installing a Link Driver, you must specify one of the following Link Driver IDs as an option.

.. csv-table:: Link Driver ID
   :header: Link Driver ID, Link Driver,Version
   :widths: 20, 40, 30

   1, ITA Driver, v1
   2, Mail Driver, v1
   3, ServiceNow Driver, v1


.. code-block:: bash

   # Move to Exastro OASE main project directory
   cd ${INSTALLATION_PATH}/oase/oase-root

   # Install link driver
   python3 manage.py driver_installer -p [plugins path] -i [Link Driver ID]

   # E.g.) Install Zabbix adapter
   python3 manage.py driver_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -i 1

