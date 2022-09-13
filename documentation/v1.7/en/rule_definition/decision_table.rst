==========================
Decision table management
==========================

| Decisio ntables analyzes alert messages acquired from monitor applications and decides what actions to run using the table's rules.

| This section explains the functions found in the Decision table page and how to use them.
| The Decision table page contains the following functions.

* Adding, Editing, Cloning and Deleting Decision tables.
* Configuring permissions for Decision tables


Add new/Edit Decision tables
====================================

| The Decision table settings can be configured from the :menuselection:`Rule --> Decision table` menu.
| Click the :guilabel:`Add new` button to create a new Decision table
| Click the "More information button" :guilabel:`` on a Decision table in order to edit it.


Basic information・Permission settings
------------------

| The Basic information and Permission settings can be configured in the :menuselection:`Basic information・Permission` settings form.

.. figure:: /images/ja/quickstart/new_decision_table_01.png
   :width: 400px
   :align: left

   Basic information・Permission settings

Decision table name
   | Input a name for the Decision table. The name can contain multibyte character strings.
   |  Register as :program:`New Decision table`.

Permission settings
   | Define access permission for the different groups.
   | For more information, see :numref:`decision_table_authentication`.
  
.. raw:: html

   <div style="clear:both;"></div>


.. table:: Permission settings
   :name: decision_table_authentication

   +----------+----------------------+--------------------+----------------------------------------------------------------------------------------+
   | Category | Page                 | Function               | Description                                                                                   |
   +==========+======================+====================+========================================================================================+
   | Rule  | Decision table | Edit・Delete         | Allows users to edit or delete the target Decision table.                         |
   +          +----------------------+--------------------+----------------------------------------------------------------------------------------+
   |          | Rule               | Staging environment   | Set permissions for the Staging environment linked to the Decision table  .                 |
   +          +                      +--------------------+----------------------------------------------------------------------------------------+
   |          |                      | Production environment | Set permissions for the Production environment linked to the Decision table.                 |
   +          +----------------------+--------------------+----------------------------------------------------------------------------------------+
   |          | Request history                            | Set permissions for the Request history acquired from the Adapter linked to the Decision table. |
   +          +----------------------+--------------------+----------------------------------------------------------------------------------------+
   |          | Action history                            | Set permissions for the Action history acquired from the Adapter linked to the Decision table.                   |
   +----------+----------------------+--------------------+----------------------------------------------------------------------------------------+
   | System | Monitor adapter                              | Set permissions for the Decision table in the Monitor adapter settings.                 |
   +----------+----------------------+--------------------+----------------------------------------------------------------------------------------+

| After inputting all the required information, press the :guilabel:`Condition settings` button.


Condition settings
----------

| In the :menuselection:`Conditional expression` settings form, users can configure Conditional expressions for different alert messages.

.. warning::
   | It is not possible to add, delete or edit a Condiional expressions that has arleady been set.
   | If needed, follow the steps below in order to move the Conditional expression.

.. figure:: /images/ja/quickstart/new_decision_table_02.png
   :width: 400px
   :align: left

   Conditional expression

Condition name
   | Input a name for the Condition.

Conditional expression
   | Conditional expressions evaluates events(Messages) acquired from the Monitor applications.
   | The Decision table contains the values and their relationships.
   | If an alert message matches with a Conditional expression, Exastro OASE will run the specified action.
   | For more information regarding the Condiional expressions, see :numref:`decision_table_conditions`.

.. raw:: html

   <div style="clear:both;"></div>

.. include:: ../include/decision_table_conditions.rst

| After inputting all the required information, press the :guilabel:`Unknown event notification settings` button.


Unknown event notification settings
----------------

| Notifications for when Unknown events are detected can be configured from the :menuselection:`Unknown event notification` settings form.

.. figure:: /images/ja/quickstart/new_decision_table_03.png
   :width: 400px
   :align: left

   Unknown event notification

Unknown event notification
   | Lets users configure notifications for when Unknown events (Events not defined) are detected.
   |  For more information regarding Unknown event notifications, see :numref:`unknown_event_notification`.


.. raw:: html

   <div style="clear:both;"></div>

.. csv-table:: Unknown event notification
   :name: unknown_event_notification
   :header: Item, Description
   :widths: 30, 70

   Do not notify me, Will not notify the user if an unknown event is detected.
   Notify by mail, Sends a mail to the specified mail address if an unknown event is detected.
   Link to ServiceNow, Issues a new Incident to the Account linked with the set ServiceNow driver.
   Notify by mail ＆ link with ServiceNow, Notifies the user through mail and issues a new incident to ServiceNow if an unknown event is detected.

| After inputting all the required information, press the :guilabel:` Save` button.

| The newdly created Decision table is displayed in the Decision table page.

.. figure:: /images/ja/quickstart/new_decision_table_04.png
   :width: 800px
   :align: center

   Decision table list


.. _copy_decision_table:

Copy/Edit Decision table
================================

| Users can clone existing Decision tables and use them as a base to create new Decision tables.
| A Decision table cloning page containing the permissions, conditional expressions and the unknown event notification settings from the original decision table is displayed.

| Press the "More information" button :guilabel:`` for the target Decision table in order to clone it.
| Press the Duplicate button:guilabel:`` at the bottom of the page.
| Input a name for the new Decision table and press the :guilabel:` Save` button in order to register it.

.. note::
   | The new Decision table cannot have the same name as an existing Decision table.


.. _delete_decision_table:

Delete Decision tables
==========================

| The user's group must have "Edit" permissions in order to delete decision tables.

| In order to delete a Decision table, press the target Decision table's "More information" button :guilabel:``.
| Press the "Delete button":guilabel:`` at the bottom of the screen.

.. danger::
   |  If a Decision table has been deleted, the Decision table file will also be deleted, and it cannot be restored.
   | The Request history and Action history will not be deleted.


Transfer Decision table
==========================

| It is not possible to edit a Decision table's conditional expression once the Decision table has been created.
| For cases like these, the decision table will need to be transfered.
| Follow the steps below in order to transfer the Decision table safely.

1. :ref:`copy_decision_table`
2. Transfer Rules
3. Change Monitor adapter
4. :ref:`delete_decision_table`

.. figure:: /images/ja/decision_table/migrate_decision_table.svg
   :width: 800px
   :align: center

   Transfering Decision table

Copy/Edit existing Decision tables
------------------------------------

#. Follow the steps in the :ref:`copy_decision_table` section and create a clone of the Decision table.
#. Input a name for the Decision table and edit the desired Conditional expression.

Transfer Rules
----------------

#. Add new rules or Edit the existing rules in the new Decision table file.
#. Apply the new Decision table file to the Staging environment and test the rules.
#. Once the rule has passed the test, apply them to the Production environment.

Change Monitor adapter
--------------------------------------------------

#. Open the Monitor adapter settings form and change the Monitor adapter.

Delete old Decision tables
----------------------------

#. Once completed, follow the steps in the :ref:`delete_decision_table` section and delete the old Decision table.
