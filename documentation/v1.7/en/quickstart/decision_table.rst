========================
Creating Decision tables
========================

| The following section explains how to configure new Decision tables.
| Decision tables for Exastro OASE decides what decisions are handled out for different messages.


Add Decision table
========================

| In order to configure decision tables, Press :menuselection:`Rule --> Decision table`.
| Press the :guilabel:` Add new` button in order to create a new decision table.
| Use the :menuselection:`Basic info / Permission` tab to configure permission and basic information.

.. figure:: /images/ja/quickstart/new_decision_table_01.png
   :width: 400px
   :align: left

   Basic info / Permission settings

Decision table name
   | Input the name of the Decision table.The name can contain multibyte strings.
   | In the quickstart guide, the name of the decision table will be :program:`New decision table`. 

Permission settings
   | Configure permissions for the different user groups.
   | In the quickstart guide, all groups will have all permissions.

   .. warning::
      | The permissions configured in this guide are set to all groups for simplicity.
      | Make sure to be careful with giving out permissions for any decision tables that are not for demonstration purposes.

.. raw:: html

   <div style="clear:both;"></div>

| After inputting the required information, press the :guilabel:` Conditional expression settings` button.
| Use the :menuselection:`Conditional expression` to configure the conditions for the alert messages.

.. figure:: /images/ja/quickstart/new_decision_table_02.png
   :width: 400px
   :align: left

   Conditional expression

Condition name
   | Input the name of the Condition.
   | In the quickstart guide, the name of the condition will be  :program:`Alert message`.

Conditional expression
   | Conditional expressions evaluates events (Messages) gathered from the Monitor application.
   | Lists the relationship with the values written in the Decision table.
   | Exastro OASe will execute an action when an alert message fitting the conditional expression is recieved.
   | In the Quickstart guide, we will select :program:`Matches regular expression` .


.. raw:: html

   <div style="clear:both;"></div>

| After inputting the required information, press the :guilabel:` Unknown event notification settings` button.
| Use the :menuselection:`Unknown event notification`  tab to configure notification destination settings.

.. figure:: /images/ja/quickstart/new_decision_table_03.png
   :width: 400px
   :align: left

   Unknown event notification

Unknown event notification
   | Lets the user configure notifications sent when an unknown event (Non-defined events) occurs.
   | In the Quickstart guide,  :program:`Don't notify` will be set.

.. raw:: html

   <div style="clear:both;"></div>

| After inputting all the items press the 、:guilabel:` Save` button.
| The newly added decision table will then be displayed.

.. figure:: /images/ja/quickstart/new_decision_table_04.png
   :width: 800px
   :align: center

   Decision table list
