===================================
Exastro IT Automation(ITA) Driver
===================================

| The Exastro IT Automation (Hereinafter written as ITA) driver sends operation requests to Exastro IT Automation and retrieves operation results.
| It is possible to connect multiple ITA servers to a single decision table.

New registrations
========

| Go to the :menuselection:`System --> Action settings` page.
| Press the :guilabel:` Add Action target` button on top of the page.
| Select "ITA Driver ver1".

.. tip::
    | The user must have "Edit" permissions in the Action settings menu in order to add Action settings.


.. figure:: /images/ja/action/action_06.png
   :scale: 80%
   :align: center

   Select Action settings

| Fill in the ITA Driver settings items

.. figure:: /images/ja/action/action_22.png
   :scale: 35%
   :align: left

   ITA Driver(ver. 1) settings page


.. csv-table:: ITA Driver(ver. 1) setting items
   :header: Settings name, Description
   :widths: 20, 60

   Name, Specify a name for the ITA Driver.
   Version, Select the Version of target ITA.
   Protocol, Select either "http" or "https" for the target ITA's connection protocol.
   Host/IP, Input the target ITA's FQDN or IP Address.
   Port, Input the Port number used when connecting to the Target ITA.
   User name, Input the ITA User name.
   Password, Input the Password for the ITA User.

.. raw:: html

   <div style="clear:both;"></div>

| After inputting all the required information, press the :guilabel:` Save` button.

.. tip:: 
   | **Linking with ITA Ver. 1.8.1 or later:**
   | The registering user must be the user linked with oase Action role in ITA's management console - Role management.

.. warning:: 
   | **Linking with ITA Ver. 1.8.0 or earler:**
   | The following items in the ITA Management console - Role/Menu link list must be restored.
   | ・ **Menu ID:2100160002 Menu name:Menu item creation information**
   | ・ **Menu ID:2100160002 Menu name:Menu item creation information**

Edit settings
========

| Open the  :menuselection:`System --> Action settinsg` menu and press the :menuselection:`ITA Driver ver1` tab.

.. figure:: /images/ja/action/action_23.png
   :scale: 60%
   :align: center

   ITA driver list

| Press the Action driver's Detailed information button :guilabel:``.

.. figure:: /images/ja/action/action_24.png
   :scale: 60%
   :align: center

   ITA driver information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/action/action_25.png
   :scale: 60%
   :align: center

   ITA driver edit page

| After inputting all the required information, press the :guilabel:` Save` button.