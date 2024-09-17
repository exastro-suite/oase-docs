==============
Mail adapter
==============

| The Mail adapter actively acquires alert messages from the Mail server.
| It is possible to use multiple Mail servers for a single decision table.

Pre-requisites
========

* A decision table must be registered before registering a monitor adapter. For more information regarding registering Decision tables, see :doc:`../rule_definition/decision_table`.
* The Mail monitor adapter must be installed in advance. For more information, see :doc:`adapter_install`.

New registrations
========

| Go to the :menuselection:`System --> Monitor adapter` menu.
| Press the :guilabel:` Add Monitor destination`.
| Select "Mail Adapter ver1".

.. tip::
    | In order to add a monitor adapter, the user must have permission to edit the monitor adapter menu.


.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_08_v1.7.png
   :scale: 80%
   :align: center

   Selecting Monitor adapter

| Fill in the settings items for the Mail adapter.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_41.png
   :scale: 35%
   :align: left

   Mail adapter(ver. 1) settings page


.. table:: Mail adapter(ver. 1) settings items

   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | Setting item                                       | Description                                                                              |
   +============================+===================+===================================================================================+
   |  Name                                                                   | Required input field. Specify a name of the Monitor adapter.            |
   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | Protocol                                     | Select the Encryption protocol for the Mail server(SSL/TLS/None).      |
   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | IMAP server                                   | Specify the Mail server(IMAP) host name or IP address.                      |
   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | Port                                         | Specify the Mail server(IMAP)s Port number.                                      |
   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | User name                                       | Input the Mail account's user name.                                  |
   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | Password                                     | Input the password for the Mail account.                  |
   +----------------------------+-------------------+-----------------------------------------------------------------------------------+
   | Select decision table                                             | Select a Decision table from the pulldown menu.                  |
   +---------------+--------------------------------+-----------------------------------------------------------------------------------+
   | Matching information      | Condition name                         | Displays the decision table condition name.                                      |
   |               +--------------------------------+-----------------------------------------------------------------------------------+
   |               | Mail item                       | Specify the Mail header items and body. (See below for more information)            |
   +---------------+--------------------------------+-----------------------------------------------------------------------------------+

.. raw:: html

   <div style="clear:both;"></div>

.. csv-table:: Mail item
   :header: Item,Description
   :widths: 20, 60

   message_id, Evaluates the Mail Message ID.
   envelope_from, Evaluates the From Mail address' Envelope.
   envelope_to, Evaluates the To Mail address' Envelope.
   header_from, Evaluates the From mail address' Header.
   header_to, Evaluates the To mail address' Header.
   mailaddr_from, Evaluates the Sender Mail address. Both the Mail sender's Display name and :program:`header_from` are described. We recommend using :program:`mailaddr_from` for evaluating Recieving Mail addresses.
   mailaddr_to, Evaluates the Reciever Mail address.If there are multiple mail addresses, they will be evaluated divided with commas. We recommend using :program:`mailaddr_to` for evaluating Sender Mail addresses.
   date, Evaluates the date the mail was sent (Created). The date is evaluated as a string in the following format. *YYYY-MM-DD HH:mm:ss* 
   subject, Evaluates the Subject of the mail.
   body, Evaluates the Body of the mail.

.. warning:: 
   | Any Mail addresses written in the CC (Carbon Copy) are not evaluated with :program:`envelope_to`, :program:`header_to` or :program:`mailaddr_to`.


| After inputting all the required information, press the :guilabel:` Save` button.


Edit settings
========

| Open the :menuselection:`System --> Monitor adapter` menu and press the :menuselection:`Mail Adapter ver1` tab.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_42.png
   :scale: 60%
   :align: center

   Mail Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_43.png
   :scale: 60%
   :align: center

   Mail Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_49.png
   :scale: 60%
   :align: center

   Mail Adapter edit page

| After inputting all the required information, press the :guilabel:` Save` button.