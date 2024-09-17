====================
Active Directory link
====================

| This section explains the Active Directory link (hereinafter written as  "AD link") function and it's required system structure and environment configuration.


Overview
====

| The AD link function provides the following functions.

.. csv-table::
   :header: Function, Application
   :widths: 15, 50
   
   User authentication, Authenticates the user using AD (LDAP) authentication from the Exastro OASE to the domain controller.
   Mirroring, Mirrors the user and group information on the domain controller to the "users" and "groups" on Exastro OASE.(One-way synchronization)


System structure
============

| The AD link function links with the domain controller which constructs the domain.

.. image:: /images/ja/active_directory/system_configuration.png
   :scale: 80%
   :align: center

| ※ userPrincipalName … Active Directory login ID.
| ※ displayName       … Display name
| ※ commonName        … Object name (In the diagram displayed above, the common name is used for the Group object.)
| ※ memberof          … Group name which the user belongs to.


Active Directory settings
=====================

.. danger:: | Using the AD link deletes all currently registered groups and users (except the system admin) and configures the group and users from the AD.
            | Lifting the AD link deletes all groups and users acquired from the AD.

| Open up the :menuselection:`System --> System settings` menu.
| Select :menuselection:`Active Directory settings` from the menu on the left.

.. figure:: /images/ja/system_config/ADLinkage_column_edit.png
   :scale: 25%
   :align: left

   Active Directory settings edit screen

.. csv-table:: Active Directory settings items
   :header: Structure components, Description
   :widths: 20, 60

   Active Directory link, Select the status of the AD Link.
   Admin user, Input the user name for the Authentication server. Can contain maximum 64 characters.
   Admin password, Input the password for the Authentication server.
   Connection destination, Configure the connecting domains in order of priority (separated by commas). Can contain maximum 512 characters.
   Link time, Input the time which the domain controller will synchronize (0~23). Divide with commas if specifying multiple hours.
   Connection time out, Specify how many seconds without operation before timeout. Specify a value between :kbd:`1-99999`.
   Load time out, Specify how many seconds before the system time outs when loading information. Specify a value between :kbd:`1-99999`.
   Authentication server search characters, Specify a identifier that can be acquired from the domain controller. Can contain maximum 256 characters.
   Add row button, Adds a row which can be used to input group list information.Max 30 group lists can be registered.
   Attribute value, Specify a group (CommonName) set to the domain controller as attribute value. Can contain maximum 40 characters.
   Attribute division name, Is used as a group name in OASE. Can contain maximum 40 characters.

| After the settings are configured, click the :guilabel:` Save` button.
| Click the :guilabel:` Reset` button to revert any changes.


Activate/deactivate Active Directory link 
=================================================

| Users can activate/deactivate the link between the Active Directory through the 3 methods shown below.

* Change the "Active Directory link" setting item in the System setting screen from :guilabel:`OFF` to :guilabel:`ON`.
* Change the "Active Directory link" setting item in the System setting screen from :guilabel:`ON` to :guilabel:`OFF`.
* Wait for the time set to the "AD Link time" in the System settings to pass.

| These system behaviour changes depending on the method.


Behaviour when changing from OFF to ON.
-----------------------------

| When changed from :guilabel:`OFF` to :guilabel:`ON`, the "Active Directory settings" input to the system screen are saved to the DB.
| The Active Directory link's crontab is then set to one of the servers.。

| When data is saved to the DB or when the crontab is configured,  OASE connects to the authentication server and acquires the user/group information.
| The acquired user and group information is saved as user and group information in Exastro OASE. 

.. figure:: /images/ja/system_config/ADLinkage_Dialog01.png
   :scale: 40%
   :align: center

   Message when Active Directory link is ON

.. warning::
   | As shown on the screen, do not close the browser or move to a different page before the process is finished.
   | If the browser is closed or the page is moved to a different page, the link might not be linked correctly.
   | If so, the user can fix it by changing the "Active Directory link" item to :guilabel:`OFF` and then :guilabel:`ON` again.
   | The came can be don if an error occurs causing the link process to fail.

Behaviour when changing from ON to OFF.
-----------------------------

| When changed from  :guilabel:`ON` to :guilabel:`OFF`, the "Active Directory link" setting items will be reset.
| The Active Directory link's crontab settings are then deleted.

| The groups and users acquired from the domain controller are deleted when the "Active Directory link" settings are reset and when the crontab settings are deleted.

.. figure:: /images/ja/system_config/ADLinkage_Dialog02.png
   :scale: 40%
   :align: center

   Message when Active Directory link is OFF.


Behaviour when the AD Link setting time passes.
---------------------------

| If the Active Directory link is set to :guilabel:`ON`, The crontab link process starts at the time set in the "AD Link time" settings.

| Meaning that updating the domain controller and group information, the changes will not immediately be displayed in Exastro OASE.
| Before passing the AD Link time, the pre-update information is active within Exastro OASE.

| When the AD Link time comes, Exastro connects to the authentication server and acquires the user/group information.
| The acquired user and group information is saved as user and group information in Exastro OASE. 

