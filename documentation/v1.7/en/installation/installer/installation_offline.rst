======================
Offline installation
======================

| The following section explains the process of installing Exastro OASE on an offline environment.
| Make sure to see the  :doc:`../requirements` before installing Exastro OASE.

Prerequisites
========

* While this manual allows the user to install Exastro OASE on an offline environment, the user will need an internet connection in order to download the required installation files.
* The OS used to collect the installation files must match the OS where Exastro OASE will be installed to.

| For information regarding installing Exastro OASE on an online environment, please see :doc:`installation_online`.


Acquire installation ilfes
====================



Preparation
========

| Installation environment

.. code-block:: bash

    # For Exastro OASE v1.5.0
    OASE_VER="1.5.0"

    # File extract directory
    EXTRACT_PATH=/tmp

    # Exastro OASE installation directory
    INSTALLATION_PATH=/exastro

| Time zone settings

.. code-block:: bash

   # Check current time zone
   timedatectl status
   Time zone: <any_time_zone>

   # Change time zone
   sudo timedatectl set-timezone <your_time_zone>

   # For Japan time
   sudo timedatectl set-timezone Asia/Tokyo

   # Check current time zone
   timedatectl status
   Time zone: Asia/Tokyo (JST, +0900)

Install required packages
==========================

| Install required packages

.. code-block:: bash

   sudo yum install -y gcc wget

Acquire newest release files
======================

| In order to acquire the release files, the user will need to move to the directory where the code is arranged.

.. tip:: | The operation directory will be used later in this manual.。
         | In this manual, the file extraction path (EXTRACT_PATH) is set to **/tmp** . 

| Download release files

.. code-block:: bash

    # For Exastro OASE v1.5.0
    OASE_VER=1.5.0
    wget -P ${EXTRACT_PATH} https://github.com/exastro-suite/oase/releases/download/v${OASE_VER}/exastro-oase-${OASE_VER}.tar.gz
    
| Extract files

.. code-block:: bash

    tar zxvf ${EXTRACT_PATH}/exastro-oase-${OASE_VER}.tar.gz -C ${EXTRACT_PATH}

| (Option) Check extract path
| ※Directory structure post extraction

.. code-block:: bash

    # Acquire tree command
    sudo yum -y install tree

    # Check Extract path
    tree --charset=C ${EXTRACT_PATH}/oase/

    # Output results
    /tmp/oase/
    |-- CHANGELOG.md
    |-- LICENSE
    |-- NOTICE
    |-- README_ja.md
    |-- licenses
    |   |-- Django.txt
    |   |-- configparser.txt
    |   |-- djangorestframework.txt
    |   |-- fasteners.txt
    |   |-- jQuery.txt
    |   |-- ldap3.txt
    |   |-- openpyxl.txt
    |   |-- pycrypto.txt
    |   |-- pytz.txt
    |   |-- ress.txt
    |   |-- retry.txt
    |   `-- xlrd.txt
    |-- oase-root
    |   |-- backyards
    |   |   |-- accept_driver
    |   |   |   |-- oase-accept.service
    |   |   |   `-- oase_accept.py
    |   |   |-- action_driver
    |   |   |   |-- oase-action.service
    |   |   |   |-- oase_action.py
    |   |   |   `-- oase_action_sub.py

    ～(Abbr)～

    `-- tool
        |-- conf
        |   |-- Grafana.conf
        |   |-- ITA.conf
        |   |-- Prometheus.conf
        |   |-- ServiceNow.conf
        |   |-- ZABBIX.conf
        |   `-- mail.conf
        |-- encrypter.py
        `-- service
            |-- nginx.service
            `-- uwsgi.service

Create installation configuration files
==============================


.. tip:: | In this manual, the extract path(EXTRACT_PATH) is set to **/tmp**. 
         | If the extract path used is different, make sure to change it accordingly.

| Move to a directory where the environment construction shell is stored.

.. code-block:: bash
   
   cd ${EXTRACT_PATH}/oase/oase_install_package/install_scripts


| Create installation configuration file(oase_answers.txt).
| The already existing installation configuration file (oase_answers.txt) serves as a sample. Make sure to change the variables to fit the user's environment.


Installation configuration items
------------------------------

| See the page below for more information regarding the setting items for the installation setting files.

.. include:: ../../include/installation_configuration_online.rst


Installation setting file sample (For commercial purposes)
---------------------------------------------

| The following installation configuration file(oase_answers.txt) is a sample that can be used for constructing an Exastro OASE environment for commercial use.
| The installation requirements are written below.

Install format
  | Online install

Decision logic
  | Red Hat Decision Manager

Install OS
  | Red Hat Enterprise Linux 7

.. include:: ../../include/sample_configuration_commercial.rst

Installation setting file sample (For non-commercial purposes)
-----------------------------------------------

| The following installation configuration file(oase_answers.txt) is a sample that can be used for constructing an Exastro OASE environment for non-commercial use.
| The installation requirements are written below.

Install format
  | Online install

Decision logic
  | Drools

Install OS
  | CentOS 7

.. include:: ../../include/sample_configuration_uncommercial.rst


Run installer
================

.. tip::
   | The installation directories for the various processes are as following.
   | Exastro OASE: :file:`/exastro``
   | JBoss (WildFly): :file:`/exastro/JBoss`

| Run the environment construction tool.

.. code-block:: bash
   
   # Switch to root
   sudo su -
   
   # Move to installion directory
   cd ${EXTRACT_PATH}/oase/oase_install_package/install_scripts

   # Run installer
   sh oase_installer.sh

.. tip::
   | The install log is created in the following path.
   | :file:`<extract_path>/oase/oase_install_package/install_scripts/logs`
   | In this manual, the path will be as following.
   | :file:`/tmp/oase/oase_install_package/install_scripts/logs`


| Check the installer execution results.
| If the following is output or displayed in the install log, the installation has ended successfully.

.. code-block:: text

   [2020-11-12 08:59:43] INFO : Finished to install
   [2020-11-12 08:59:43] #####################################
   [2020-11-12 08:59:43] INFO : Install Finished
   [2020-11-12 08:59:43] #####################################

Django settings
===========

| Configure Django's :program:`HOST_NAME`.
| :program:`HOST_NAME` specifies the URL used to access the Exastro OASE server.

.. code-block:: bash

   # Example used in this manual
   vi ${INSTALLATION_PATH}/OASE/oase-root/confs/frameworkconfs/settings.py

.. code-block:: python
   
   # For all-in-one structure(if all processes are running on the same server)
   HOST_NAME = 'https://127.0.0.1'

   # E.g.) Specifying with Domain name
   HOST_NAME = 'https://oase.example.com:8080'

| For other setting values, change them to fit the project's environment.
| Restart the Web service in order to display the settings.

.. code-block:: bash

   systemctl restart httpd

Check connectivity
========

.. include:: ../../include/confirm_login.rst
