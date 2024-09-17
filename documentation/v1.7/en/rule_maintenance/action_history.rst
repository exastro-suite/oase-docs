==============
Action history
==============

| The Action history page allows the user not only check action statuses and results, but also to approve and/or reject any actions that are waiting for approval.

| The following section explains the Action history page structure and components.


Check Action history
==================

| If an event matches with a rule, an action will be executed.
| In order to check the executed action, go to the :menuselection:`Rule --> Action history` menu and open the :menuselection:`Action history page`.

.. figure:: /images/ja/action_history/action_history_01.png
   :scale: 80%
   :align: center

   Action history page

.. warning:: 
   | The user must have permission to view the decision table in order for it to be displayed in the Action history page.

| The Action's status icons and their meaning are as following.

.. list-table:: Status icon
    :widths: 20, 60
    :header-rows: 1

    * - Icon
      - Description
    * - .. figure:: /images/ja/action_history/check.png
           :scale: 20%
      - The action has been executed successfully.
    * - .. figure:: /images/ja/action_history/gear.png
           :scale: 20%
      - The action is currently beign executed.
    * - .. figure:: /images/ja/action_history/cross.png
           :scale: 20%
      - The Action was force canceled
    * - .. figure:: /images/ja/action_history/stop.png
           :scale: 20%
      - The action is waiting for approval.
    * - .. figure:: /images/ja/action_history/square.png
           :scale: 20%
      - The action approval was canceled.
    * - .. figure:: /images/ja/action_history/attention.png
           :scale: 20%
      - An error occured while running Exastro.
    * - .. figure:: /images/ja/action_history/prevent.png
           :scale: 39%
      - The action was stopped.


Check Action execution status
========================

| The action's execution status can be seen by pressing the "More information" button :guilabel:``. Here users can see the Execution status and Execution log.
| The More information page is divided into 3 parts. "Request information", "Action information" and "Log".
| The information displayed in the "Action information" section differs depends on the Action type.

.. figure:: /images/ja/action_history/action_history_04.png
   :scale: 60%
   :align: center

   Action history more information page

.. csv-table:: Action history detailed information description
   :header: Item, Description
   :widths: 20, 60

   Event start date/time, Displays the date of the event/ the cause of the action.
   Event serial No., Request information identifier.
   Event information, Displays requested event information.
   Action date/time, Displays the date/time of the Action
   Event No., Request information identifier. Contains the same value as "Event serial No.".
   Decision table name, Displays the name of the executed decision table.
   Rule name, Displays the name of the rule that executed the action.
   Event, Displays the event that executed the action.
   Method overview, Displays an overview of the method that was executed by the action.
   Action parameter information, Displays the parameter information of the action.
   Log information, Displays an Action execution log. A Message ID will be set to the ouput log.


Exastro IT Automation execution results
------------------------------

| The Exastro IT Automation native execution result items displayed in the More details page are as following.

* When executing Symphony

.. figure:: /images/ja/action_history/action_history_12.png
   :scale: 30%
   :align: left

   Symphony execution results

.. csv-table:: Native items(When executing ITA Symphony) description
   :header: Structure components, Description
   :widths: 20, 60

   ITA display name, Displays the ITA_NAME written in the Decision table file.
   Symphony instance number, Displays the Symphony list ID that was executed in ITA.
   Symphony class ID, Displays the Symphony class list ID that was executed in ITA.
   Operation ID, Displays the Input operation list ID that was executed in ITA.
   Symphony operation URL, Displays an URL that allows users to check the Symphony. Sends the user to the ITA Symphony confirm page.
   RESTAPI error detailed information, Displays error contents if an error occured in the REST results between OASE and ITA.
   Link item, Displays the value link in ITA when executing an ITA action with Menu ID Specification.

.. raw:: html

   <div style="clear:both;"></div>

* When executing Conductor

.. figure:: /images/ja/action_history/action_history_14.png
   :scale: 30%
   :align: left

   Conductorexecution results
   

.. csv-table:: Native items(When executing ITA Conductor) description
   :header: Structure components, Description
   :widths: 20, 60

   ITA display name, Displays the ITA_NAME written in the Decision table file.
   Conductor instance number, Displays the Conductor list ID that was executed in ITA.
   Conductor class ID, Displays the Conductor class list ID that was executed in ITA.
   Operation ID, Displays the Input operation list ID that was executed in ITA.
   Conductor operation URL, Displays an URL that allows users to check the Conductor. Sends the user to the ITA Conductor confirm page.
   RESTAPI error detailed information, Displays error contents if an error occured in the REST results between OASE and ITA.
   Link item, Displays the value link in ITA when executing an ITA action with Menu ID Specification.

.. raw:: html

   <div style="clear:both;"></div>

Mail results
--------------

.. figure:: /images/ja/action_history/action_history_13.png
   :scale: 30%
   :align: left

   Mail native items

.. csv-table:: Native items(Mail) description
   :header: Structure components, Description
   :widths: 20, 60

   Mail template name, Displays the name of the template that was used when the action was executed.
   Receiving mail address, Displays the Mail address the mail was sent to when the action was executed.

.. raw:: html

   <div style="clear:both;"></div>

.. note::
    The "Receiving mail address" is written in a way the user can tell whether the mail address written in the Decision table file
    or the mail address written in the Mail template was used.


ServiceNow link results
-------------------

.. figure:: /images/ja/action_history/action_history_15.png
   :scale: 30%
   :align: left

   ServiceNow link native items

.. csv-table:: Native items(ServiceNow link) description
   :header: Structure components, Description
   :widths: 20, 60

   ServiceNow display name, Displays the SERVICENOW_NAME written in the Decision table file.
   sys_id, Display the Incident and Workflow ID set in ServiceNow.
   Short Description, Displays the Short Description linked with ServiceNow.


.. raw:: html

   <div style="clear:both;"></div>


Acquiring Action history detailed information.
========================

| The detailed information can be downloaded as a text file by pressing the Download Detailed information button :guilabel:``.

.. figure:: /images/ja/action_history/action_history_05.png
   :scale: 60%
   :align: center

   Acquiring Action hsitory detailed information.


Re-running actions
================
| If an action failed due to an error and allows for re-runs, the user can press the Re-run button :guilabel:`` to re-execute the action.

.. figure:: /images/ja/action_history/action_history_07.png
   :scale: 60%
   :align: center

   Re-run action

.. note::
   | The user must have "Can edit" permissions for the corresponding decision table in order to re-run actions.


Approving actions
========

* If a rule written in the  Decision table's Pre-execution Action parameter information is run before the action is executed, the action can be paused.
* In the Action history page, users can press either the Approve or Reject button to choose what to do with the Action.

.. include:: ../include/approval_dialog.rst


