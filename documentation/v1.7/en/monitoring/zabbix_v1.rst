==============
Zabbix adapter
==============

| The Zabbix adapter automatically acquires (`Trigger information <https://www.zabbix.com/documentation/current/en/manual/api/reference/trigger/object>`_) sent from Zabbix servers.
| It is possible to use multiple Zabbix servers for a single decision table.

Pre-requisites
========

* A decision table must be registered before registering a monitor adapter. For more information regarding registering Decision tables, see :doc:`../rule_definition/decision_table`.
* In order to link with Zabbix, the Zabbix server's URL must contain http[s]://zabbix.server.fqdn/**zabbix**, and the Service must be public in the */zabbix* directory.
* The Zabbix monitor adapter must be installed in advance. For more information, see :doc:`adapter_install`.

New registrations
========

| Go to the :menuselection:`System --> Monitor adapter` menu.
| Press the :guilabel:` Add Monitor destination`.
| Select "ZABBIX Adapter ver1".

.. tip::
    | In order to add a monitor adapter, the user must hage permission to edit the monitor adapter menu.


.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_08_v1.6.png
   :scale: 80%
   :align: center

   Selecting Monitor adapter

| Fill in the settings items for the Zabbix adapter.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_09.png
   :scale: 35%
   :align: left

   Zabbix adapter(ver. 1) settings page


.. table:: Zabbix adapter(ver. 1) settings items

+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Setting item                                | Description                                                                                                                                                                           |
+============================+============+================================================================================================================================================================================+
| Name                                    | Required input field. Specify a name of the Monitor adapter.                                                                                                         |
+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Protocol                              | Select either HTTP or HTTPS from the pulldown menu.                                                                                              |
+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Host/IP                               | Required input field. Input either FQDN or an IP Address. Can contain maximum 128 characters.                                                                                        |
+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Port                                  | Specify a Port number that can connect to the Zabbix server.                                                                                                                               |
+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| User name                                | Specify the Zabbix user                                                                                                                                                    |
+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Password                              | Input the Zabbix user password.                                                                                                                                          |
+----------------------------+------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Select Decision table              | Select a Decision table from the pulldown menu.                                                                                                               |
+---------------+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Matching information      | Condition name                  | The Condition from the selected decision table is displayed.                                                                                                                             |
|               +-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|               | Zabbix item              | Select a Zabbix trigger item that will be evaluated by the Decision table <https://www.zabbix.com/documentation/current/en/manual/api/reference/trigger/object>`. |
+---------------+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. raw:: html

   <div style="clear:both;"></div>

| After inputting all the required information, press the :guilabel:` Save` button.


Edit settings
========

| Open the :menuselection:`System --> Monitor adapter` menu and press the :menuselection:`ZABBIX Adapter ver1` tab.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_10.png
   :scale: 60%
   :align: center

   Zabbix adapter list

| Click the More information button :guilabel:`` for the Monitor adapter you want to edit.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_11.png
   :scale: 60%
   :align: center

   Zabbix Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_13.png
   :scale: 60%
   :align: center

   Zabbix Adapter edit page

| After inputting all the required information, press the :guilabel:` Save` button.