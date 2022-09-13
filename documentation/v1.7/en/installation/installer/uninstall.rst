=========================
Uninstall ※Manual incomplete
=========================

| The following manual explains how to uninstall Exastro OASE.
| This manual will use well-known usecases to show how to uninstall Exastro OASE with 4 different methods.


Prerequisites
========

 Uninstalling Exastro OASE uses the setting values used when installing OASE, meaning that the user will need to have the Installation configuration files on hand.


Method 1: For leaving data
============================

install_mode
  | **Uninstall** : Specify the Uninstall mode.

db_root_password
  | Specify MariaDB root password.

db_erase
  | **leave** : Data will not be deleted from MariaDB when uninstalled.

oase_directory
  | Specify **<Exastro OASE installation directory>/OASE**. 


Method 2: For deleting all data
============================

 install_mode
  | **Uninstall** : Specify the Uninstall mode.

 db_root_password
  | Specify MariaDB root password.

 db_erase
  | **erase** : Deletes all data from MariaDB when uninstalled.

 oase_directory
  | Specify **<Exastro OASE installation directory>**. 


Run installer
================

.. tip::
   | The installation directories for the various processes are as following.
   | Exastro OASE: **/exastro**
   | JBoss (WildFly): **/exastro/JBoss**

| Run environment construction tool.

.. code-block:: bash
   
   # Switch to root
   sudo su -
   
   # Move to installion directory
   cd ${EXTRACT_PATH}/oase/oase_install_package/install_scripts

   # Run installer
   sh oase_installer.sh

.. tip::
   | The install log is created in the following path.
   | **<extract_path>/oase/oase_install_package/install_scripts/logs**
   | In this manual, the path will be as following.
   | **/tmp/oase/oase_install_package/install_scripts/logs**


| Check the installer execution results.
| If the following is output or displayed in the install log, the installation has ended successfully.

.. code-block:: text

   [2020-11-12 08:59:43] INFO : Finished to install
   [2020-11-12 08:59:43] #####################################
   [2020-11-12 08:59:43] INFO : Install Finished
   [2020-11-12 08:59:43] #####################################
