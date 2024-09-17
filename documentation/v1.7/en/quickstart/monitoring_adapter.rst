==================
Create Monitoring adapter
==================

| The following section explains the process of creating new monitoring adapters and implementing the ZABBIX monitor adapter.
| Monitoring adapters in Exastro OASE gathers alert information from different monitoring applications.


Add ZABBIX monitor adapter
========================

| Users can configure monitor adapters by going to the  :menuselection:`System --> Monitor adapter` menu.
| Click :guilabel:` Add new monitor destination` in order to register new monitor adapters.

| Use the :menuselection:`Add monitor adapter`menu to configure the monitor adapter.

.. figure:: /images/ja/quickstart/new_monitoring_adapter_01.png
   :width: 400px
   :align: left

   Add Monitoring destination

Select Monitoring destination
   | Select which application the monitoring adapter will function for (In this case: Zabbix).
   | In the Quickstart guide,  :guilabel:`ZABBIX Adapter ver1` will be selected.

.. raw:: html

   <div style="clear:both;"></div>

| Use the :menuselection:`ZABBIX Adapter ver1` settings form to configure the information needed in order to link the monitoring application(Zabbix) and the Decision table.

.. figure:: /images/ja/quickstart/new_monitoring_adapter_02.png
   :width: 400px
   :align: left

   ZABBIX Adapter ver1

Name
   | Input the name of the monitor adapter.
   | In the Quickstart guide, the name will be registered as :program:`New ZABBIX monitor adapter`.

Protocol
   | Select the communication protocol needed in order to connect to the Monitor application (Zabbix).
   | In the Quickstart guide, :program:`http` will be selected.

Host/IP
   | Input the Host name/IP Address used to connect to the monitor application (Zabbix).

Port
   | Input the port number used in order to connect to the monitor application (Zabbix)
   | In the Quickstart guide, the port number :program:`80` will be used.

Username
   | Input the name of the user that will used to log in to the monitor application (Zabbix).

.. tip:: The user must be able to see the monitor alerts.

Password
   | Input the password for the user that will be used to log in to the monitor application (Zabbix).

Select Decision table name
   | Select the decision table that will be linked.
   | Select the decision table created in the :doc:`decision_table` section.

Matching information
   | Select the Monitor application items that matches the decision table.
   | In the Quickstart guide, the  :program:`description` will be selected.


.. raw:: html

   <div style="clear:both;"></div>


| After inputting all the required information, press the :guilabel:` Save` button.
| The newly added monitor adapter will be displayed.

.. figure:: /images/ja/quickstart/new_monitoring_adapter_03.png
   :width: 800px
   :align: center

   Monitor adapter list

Check the Monitor application link.
============================

| Users can check the Monitor application monitor connectivity from the  :menuselection:`Rule --> Request history` menu.
| If an alert has appeard in Zabbix, it will show up in the Request history screen as shown in the figure below.

.. figure:: /images/ja/quickstart/new_monitoring_adapter_04.png
   :width: 800px
   :align: center

   Request history

| If the alert does not show up in the :menuselection:`Request history` menu, the connection to the Monitor application might have failed.
| If so, make sure to check the user permissions, setting contents and the network reachability settings.
