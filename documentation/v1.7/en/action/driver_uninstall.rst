==============================
Uninstall Link Driver
==============================

| This manual explains how to remove installed Link drivers.
| This section can be skipped if the desired Link driver has already been uninstalled.
| Note that this manual uses the Installer version of OASE (Not the container version) as an example.

Uninstall Link Driver
==============================

| When uninstalling a Link Driver, you must specify one of the following Link driver IDs as an option.

.. csv-table:: Link Driver ID
   :header: Link Driver ID, Link Driver,Version
   :widths: 20, 40, 30

   1, ITA Driver, v1
   2, Mail Driver, v1
   3, ServiceNow Driver, v1


.. code-block:: bash

   # Move to Exastro OASE main project directory
   cd ${INSTALLATION_PATH}/oase/oase-root

   # Uninstall link driver
   python3 manage.py driver_installer -p [plugins path] -u [Link Driver ID]

   # E.g.) Uninstall Zabbix adapter
   python3 manage.py driver_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -u 1

