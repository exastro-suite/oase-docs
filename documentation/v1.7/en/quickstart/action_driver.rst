========================
Creating Action drivers
========================

| This section explains how to add a new ITA(Exastro IT Automation) Action driver.
| Action drivers in Exastro OASE are functions that links automation software.

.. note::
   | **Exastro IT Automation** might be shortened to **ITA**.

Adding ITA(Exastro IT Automation) action driver
==================================================

| The Action Driver settings can be configured by going to the :menuselection:`System --> Action settings` menu.
| In order to register a new Action driver, press the :guilabel:` Add Action destination` button.

|  Configure from the :menuselection:`Add Action destination` settings form.

.. figure:: /images/ja/quickstart/new_action_driver_01.png
   :width: 400px
   :align: left

   Add Action destination

Select Action destination
   | Select the Link software(ITA) action driver.
   |  Select :program:`ITA Driver ver1`.

.. raw:: html

   <div style="clear:both;"></div>

|  Input the information necessary to link with the software(ITA) and the Decision table in the :menuselection:`ITA Driver ver1`  settings form.

.. figure:: /images/ja/quickstart/new_action_driver_02.png
   :width: 400px
   :align: left

   ITA Driver ver1

Name
   | Input a name for the action driver.
   | In the Quickstart guide, the name :program:`New ITA action driver` will be used.

Version
   | Select the version of the link software(ITA).

Protocol
   | Select the connection protocol for connecting to the link software(ITA).
   | In the Quickstart guide, :program:`http` will be selected.

Host/IP
   | Input a Host name or IP Address for connecting to the link software(ITA).

Port
   | Specify a port number used for connecting to the link software(ITA).
   | In the Quickstart guide, the port number :program:`80`.

User name
   | Input the user name for the link software(ITA).

   .. warning::
      | The ITA user must be linked to the Exastro OASE role.

Password
   | Input the password for the link software(ITA) user.

Access permissions
   | Define permissions for the different groups.
   | Here all items will be editable.

.. raw:: html

   <div style="clear:both;"></div>


| After inputting all the items, press the :guilabel:` Save` button.
| The added action driver will be displayed.

.. figure:: /images/ja/quickstart/new_action_driver_03.png
   :width: 800px
   :align: center

   Action driver list
