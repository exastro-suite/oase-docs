==============================
Uninstall Monitor adapters
==============================

| This section explains how to delete installed Monitor adapters.
| This section can be skipped if the target Monitor Adapter is not installed to Exastro OASE.
| Note that this manual uses the Installer version of OASE (Not the container version) as an example.

Uninstall Monitor adapters
==============================

| When uninstalling Monitor Adapters, you must specify one of the following Monitor adapter IDs as an option.

.. csv-table:: Monitor adapter ID
   :header: Monitor adapter ID,Monitor adapter,Version
   :widths: 20, 40, 30

   1, Zabbix Adapter, v1
   2, Prometheus Adapter, v1
   3, Grafana Adapter, v1
   4, Datadog Adapter, v1
   5, Mail Adapter, v1


.. code-block:: bash

   # Move to Exastro OASE main project directory
   cd ${INSTALLATION_PATH}/oase/oase-root

   # Uninstall Monitor adapter
   python3 manage.py adapter_installer -p [plugins path] -u [Monitor adapter ID]

   # E.g.) Uninstall Zabbix adapter
   python3 manage.py adapter_installer -p ${INSTALLATION_PATH}/oase/oase_install_package/OASE/oase-contents/plugins -u 1

