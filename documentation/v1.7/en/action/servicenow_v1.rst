===================
ServiceNow Driver
===================

| The ServiceNow driver runs workflows, manages incidents and implements approval flows.
| It is possible to connect multiple ServiceNow accounts to a single decision table.

New registrations
========

| Go to the :menuselection:`System --> Action settings` page.
| Press the :guilabel:` Add Action target` button on top of the page.
| Select "ServiceNow Driver ver1".

.. tip::
    | The user must have "Edit" permissions in the Action settings menu in order to add Action settings.


.. figure:: /images/ja/action/action_06.png
   :scale: 80%
   :align: center

   Select Action settings

| Fill in the ServiceNow Driver setting items

.. figure:: /images/ja/action/action_52.png
   :scale: 35%
   :align: left

   ServiceNow Driver(ver. 1) settings page


.. csv-table:: ServiceNow Driver(ver. 1) setting items
   :header: Settings name, Description
   :widths: 20, 60

   Name, Specify a name for the ServiceNow driver.
   Protocol, Select either "http" or "https" for the target ServiceNow instance connection protocol.
   Host/IP, Input the target ServiceNow instance's FQDN or IP Address.
   Port, Input the Port number used when connecting to the target ServiceNow instance.
   User name, Input the ServiceNow User name.
   Password, Input the Password for the ServiceNow account.
   Proxy, Input the proxy server connection point used for internet access.(Optional)

.. raw:: html

   <div style="clear:both;"></div>

| After inputting all the required information, press the :guilabel:` Save` button.

Edit settings
========

| Open the  :menuselection:`System --> Action settinsg` menu and press the :menuselection:`ServiceNow Driver ver1` tab.

.. figure:: /images/ja/action/action_53.png
   :scale: 60%
   :align: center

   ServiceNow driver list

| Press the Action driver's Detailed information button :guilabel:``.

.. figure:: /images/ja/action/action_54.png
   :scale: 60%
   :align: center

   ServiceNow driver information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/action/action_55.png
   :scale: 60%
   :align: center

   ServiceNow driver edit page

| After inputting all the required information, press the :guilabel:` Save` button.