
==============
Action definition
==============

| The user must input appropriate parameters in the Decision table's :menuselection:`Action parameter information` in order for Exastro OASE to link with Exastro IT Automation and Mail server.
| This section explains how to write said parameter information.


Exastro IT Automation link
==========================

| This section explains the action parameters used when linking with Exastro IT Automation (ITA).
| The Action parameter changes depending on which system the Taret Host and Input parameters are managed in(ITA and OASE).

ITA Action parameters
-----------------------

+----------------+-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
| Parameter class | Parameter variables          | Parameter value                                                                                  | Input example                                |
+================+=========================+===============================================================================================+=======================================+
| Driver name     | ITA_NAME                | ITA driver name.                                                                               | ITA_NAME=exastro-ita01                |
+                +                         +                                                                                               +                                       +
|                |                         | Required input field.                                                                                |                                       |
+----------------+-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
| Job flow   | CONDUCTOR_CLASS_ID      | Conductor class ID.                                                                   | CONDUCTOR_CLASS_ID=2                  |
+                +                         +                                                                                               +                                       +
|                |                         | The Conductor Class ID can be seen in the Conductor class list.                                        |                                       |
+                +                         +                                                                                               +                                       +
|                |                         | Either SYMPHONY_CLASS_ID or CONDUCTOR_CLASS_ID must be selected.                                 |                                       |
+                +-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
|                | SYMPHONY_CLASS_ID       | Symphony class ID.                                                                    | SYMPHONY_CLASS_ID=3                   |
+                +                         +                                                                                               +                                       +
|                |                         | The Symphony Class ID can be seen in the Symphony class list.                                          |                                       |
+                +                         +                                                                                               +                                       +
|                |                         | Either SYMPHONY_CLASS_ID or CONDUCTOR_CLASS_ID must be selected.                                     |                                       |
+----------------+-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
| Operation | OPERATION_ID            | Operation ID used when executin operations                                                  | OPERATION_ID=4                        |
+                +                         +                                                                                               +                                       +
|                |                         | Cannot link with Operation targets or menus when using OPERATION_ID.                             |                                       |
+----------------+-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
| Input parameter | MENU_ID                 | ITA Menu ID.                                                                      | MENU_ID=1                             |
+                +                         +                                                                                               +                                       +
|                |                         | Only menus that can be used by the Host group can be linked.                | MENU_ID=1:2                           |
+                +                         +                                                                                               +                                       +
|                |                         | <Menu ID>:<Menu ID>:...                                                                 |                                       |
+                +                         +                                                                                               +                                       +
|                |                         | CONVERT_FLG must be specified                                                                 |                                       |
+                +-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
|                | CONVERT_FLG             | Flag for using Target hosts through messages.                                    | CONVERT_FLG=TRUE                      |
+                +                         +                                                                                               +                                       +
|                |                         | Must be specified when MEMU_ID is used.                                                             | CONVERT_FLG=FALSE                     |
+                +                         +                                                                                               +                                       +
|                |                         | :kbd:`TRUE` : Uses acquired messages as Taret host name.                          |                                       |
+                +                         +                                                                                               +                                       +
|                |                         | :kbd:`FALSE` : Extracts character string of acquired messages and uses it and uses it as Target host name   |                                       |
+----------------+-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
| Target Operation       | SERVER_LIST             | Target host registered in ITA's Device list                                                | SERVER_LIST=www01                     |
+                +                         +                                                                                               +                                       +
|                |                         | OPERATION_IDs are automatically paid out.                                                         | SERVER_LIST=www01:www02               |
+                +                         +                                                                                               +                                       +
|                |                         | OPERATION_ID and MENU_ID cannot be used together                                               |                                       |
+                +-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
|                | HOST_NAME               | Host name linked in ITA's host group list.                          | HOST_NAME=1:db01                      |
+                +                         +                                                                                               +                                       +
|                |                         | <Menu ID>:<Host name>&<Host name>&...|<Menu ID:<Host name>...                             | HOST_NAME=1:db01&db02|2:www01         |
+                +                         +                                                                                               +                                       +
|                |                         | Can only be specified when MENU_ID is being used.                                                             |                                       |
+                +-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+
|                | HOSTGROUP_NAME          | Host group name as seen in ITA's Host group list.                | HOSTGROUP_NAME=1:db-group|2:web-group |
+                +                         +                                                                                               +                                       +
|                |                         | Can only be specified when MENU_ID is being used.                                                             |                                       |
+----------------+-------------------------+-----------------------------------------------------------------------------------------------+---------------------------------------+



.. note::
   | **CONVERT_FLG is TRUE**
   | Can be used if the Rules written in the Condition part follows the restrictions below.
   | ・The first condition must be able to match with the target host name.
   | ・The other conditions must ble able to match with the values linked to the parameter sheet.
   | The value matched to the rule will be registered to the Parameter sheet.
   | The order in which the values are registered to the parameter sheet is the same order of the event information.
   |
   | **CONVERT_FLG is FALSE**
   | Can be used without any rule restrictions.
   | The Values linked to ITA's parameter sheets are exctracted from the matched character string by a specified extraction condition.
   | The values extracted must have a target host.
   | The order in which the values are registered to the parameter sheet can be specified per Menu ID.


Usecases
------------

| **Case 1**
| Using devices and parameters configured in ITA

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,OPERATION_ID=1

::

 ITA_NAME=exastro-ita01,SYMPHONY_CLASS_ID=2,OPERATION_ID=2

| **Case 2**
| Using devices and parameters configured in ITA to specify host in OASE.

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,SERVER_LIST=www01

::

 ITA_NAME=exastro-ita01,SYMPHONY_CLASS_ID=2,SERVER_LIST=db01:db02

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,SERVER_LIST={{ VAR_<Condition name> }}

| **Case 3**
| Using target hosts/ host groups and parameter sheets configured in ITA to specify Host or Host group in OASE.

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,MENU_ID=1,HOST_NAME=1:www01,CONVERT_FLG=FALSE

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,MENU_ID=1,HOSTGROUP_NAME=1:web-group,CONVERT_FLG=FALSE

::

 ITA_NAME=exastro-ita01,SYMPHONY_CLASS_ID=2,MENU_ID=2:3:4,HOST_NAME=2:www01,HOSTGROUP_NAME=3:db-group|4:app1-group&app2-group,CONVERT_FLG=FALSE
 
| **Case 4**
| Using the value matched with Condition 1 as host name and specifying values matched with later conditions as values linked to parameter sheets.

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,CONVERT_FLG=TRUE

::

 ITA_NAME=exastro-ita01,SYMPHONY_CLASS_ID=2,CONVERT_FLG=TRUE

| **Case 5**
| Using the value matched with Condition 1 as host name and specifying extracted values extracted from later conditions as values linked to parameter sheets.

::

 ITA_NAME=exastro-ita01,CONDUCTOR_CLASS_ID=1,CONVERT_FLG=FALSE

::

 ITA_NAME=exastro-ita01,SYMPHONY_CLASS_ID=2,CONVERT_FLG=FALSE



Mail link
=========

| The following section describes action parameters used when using mail notifications.

.. include:: ../include/mail_action.rst

Usecases
------------

| **Case 1**
| Notify specified users through mail.

::

 MAIL_NAME=management-mail,MAIL_TO=maintener@example.com,MAIL_CC=dev-team@example.com,MAIL_BCC=

| **Case 2**
| Using a mail template to notify specified users through mail.

::

 MAIL_NAME=management-mail,MAIL_TO=,MAIL_CC=dev-team@example.com,MAIL_BCC=,MAIL_TEMPLATE=service-down


ServiceNow link
===============

| The following section explains the action parameters used when linked to ServiceNow.

ServiceNow Action parameters
------------------------------

+----------------+-------------------------+-------------------------------------------------------------------------------------------------------------+---------------------------------------+
| Parameter class | Parameter variable          | Parameter value                                                                                                | Input example                                |
+================+=========================+=============================================================================================================+=======================================+
| Driver name     | SERVICENOW_NAME         | ServiceNow driver name.                                                                                      | SERVICENOW_NAME=department01          |
+                +                         +                                                                                                             +                                       +
|                |                         | Required input field.                                                                                              |                                       |
+----------------+-------------------------+-------------------------------------------------------------------------------------------------------------+---------------------------------------+
| Workflow   | WORKFLOW_ID             | Specifies the **work schedule's sys_id** linking to the executing workflow.                         | WORLFLOW_ID=abcdef1234567890          |
+                +                         +                                                                                                             +                                       +
|                |                         | Input only when linked to Workflow.                                                                          |                                       |
+                +                         +                                                                                                             +                                       +
|                |                         | .. warning:: Make sure that it is not the workflow's sys_id.                                             |                                       |
+----------------+-------------------------+-------------------------------------------------------------------------------------------------------------+---------------------------------------+
| Incident   | INCIDENT_STATUS         | Specifies whether to issue incident or update status.                                              | INCIDENT_STATUS=NEW                   |
|                |                         | Input only when using Incident management.                                                                          |                                       |
+                +                         +                                                                                                             +                                       +
|                |                         | :kbd:`NEW`: Specify when new issuing new incident.                                                            | INCIDENT_STATUS=IN_PROGRESS           |
|                |                         | If Managing incidents, make sure that the it matches with something first.                                          |                                       |
+                +                         +                                                                                                             +                                       +
|                |                         | :kbd:`IN_PROGRESS`: Specify when status is "In progress".                                              | INCIDENT_STATUS=RESOLVED              |
|                |                         | Normally specifies a rule before running an action.                                          |                                       |
+                +                         +                                                                                                             +                                       +
|                |                         | :kbd:`RESOLVED`: Specify when status is "Resolved".                                               | INCIDENT_STATUS=CLOSED                |
|                |                         | Normally specifies a rule after running an action.                                          |                                       |
+                +                         +                                                                                                             +                                       +
|                |                         | :kbd:`CLOSED`: Specify when closing status.                                                 |                                       |
|                |                         | Normally specifies a rule after recieving an approval for closing an incident.                                              |                                       |
+                +-------------------------+-------------------------------------------------------------------------------------------------------------+---------------------------------------+
|                | WORK_NOTES_APPROVAL     | Specifies an approval text for running actions.                                                                    | WORK_NOTES_APPROVAL=APPROVED_ACTION   |
+                +                         +                                                                                                             +                                       +
|                |                         | The process will only continue if the Incident's operation memo contains an approval text.               | WORK_NOTES_APPROVAL=APPROVED_CLOSE    |
|                |                         | If not, the action will pause.                                    |                                       |
+                +-------------------------+-------------------------------------------------------------------------------------------------------------+---------------------------------------+
|                | WORK_NOTES_REJECTED     | Specifies a rejection text for running actions.                                                                    | WORK_NOTES_REJECTED=REJECTED_ACTION   |
+                +                         +                                                                                                             +                                       +
|                |                         | The process will stop if the Incident's operation memo contains a rejection text.          | WORK_NOTES_REJECTED=REJECTED_CLOSE    |
|                |                         | If the memo does not contain a rejection text, nothing will hapen.                                    |                                       |
+----------------+-------------------------+-------------------------------------------------------------------------------------------------------------+---------------------------------------+


Usecases
------------

| **Case 1**
| Execute workflow using the Workflow schedule.

::

 SERVICENOW_NAME=department01,WORKFLOW_ID=abcdef1234567890


| **Case 2**
| Issue incident and update status.

::

 SERVICENOW_NAME=department01,INCIDENT_STATUS=NEW

::

 SERVICENOW_NAME=department01,INCIDENT_STATUS=CLOSED

| **Case 3**
| Use incident and wait for approval.

::

 SERVICENOW_NAME=department01,INCIDENT_STATUS=IN_PROGRESS,WORK_NOTES_APPROVAL=APPROVED_ACTION,WORK_NOTES_REJECTED=REJECTED_ACTION


Best utilizing Incident management
------------------------------------

| If the user is using Exastro OASE and is linked with ServiceNow incidents, a decision table file like the one below can be used.

.. csv-table:: Pseudo rules for managing and processing incidents
   :name: rule_and_action
   :escape: \
   :header: Rule name, Condition, Event, Action, Action parameter※ Without Driver name
   :widths: 20, 35, 30, 40, 40

   Issue incident, If Alert name contains ".* is down", Service failed, Issuing incident.[APPROVAL_REQUEST], INCIDENT_STATUS=NEW
   Processing, If Alert name contains "httpd is down", Apache service failed, Starting Service restart process., INCIDENT_STATUS=IN_PROGRESS
   Run ITA, If Alert name contains "httpd is down", Apache service failed, Starting Service restart process,CONDUCTOR_CLASS_ID=3\,OPERATION_ID=4
   Process complete, If Alert name contains "httpd is down", Apache service failed, Service restart process completed,INCIDENT_STATUS=RESOLVED
   Close Incident(With approval), If Alert name contains "httpd is down", Apache service failed, Closing Incident. If there are no problems with the processing contents, approve close request.,INCIDENT_STATUS=CLOSED\,WORK_NOTES_APPROVAL=APPROVED_CLOSE\,WORK_NOTES_REJECTED=REJECTED_CLOSE

| The :program:`Rule name`, :program:`Event` and :program:`Action` written in the Decision table file will be added to the ServiceNow's Incident description field.

.. code-block:: text

    2022-01-11 10:45:35
    Rule name : Close Incident(With approval)
    Event : Apache service failed
    Action : Closing Incident. If there are no problems with the processing contents, approve request.
    ==================================================
    2022-01-11 10:45:32
    Rule name : Process complete
    Event : Apacke service failed
    Action : Service restart process completed
    ==================================================
    2022-01-11 10:43:34
    Rule name : Processing(With approval)
    Event : Starting Service restart process.
    Action : Changing to the standard OASE page. If there are no problems with the processing contents, approve request.
    ==================================================
    2022-01-11 10:43:32
    Rule name : Issue incident
    Event : Service failed
    Action : Issue incident.[APPROVAL_REQUEST]

| For linking with request approvals system, the `Flow Designer <https://www.servicenow.co.jp/products/platform-flow-designer.html>`_ must be configured from the ServiceNow side.
| More specifically, similar to :numref:`approval_sequence`, the trigger character string(APPROVAL_REQUEST) written in the Incident table update and Incident contents' description fields are used Flow start triggers.
| The system requests an approval from the user. If approved, a character string serving as an approval message will be written in the the operation's memo field. If not, a character string serving as a disapproval message will be written.
| OASE reads the contents of the operation memo and decides what to do next.

.. figure:: /images/ja/decision_table/approval_sequence.svg
   :name: approval_sequence
   :scale: 100%
   :align: center

   Acquiring messages that matches :numref:`rule_and_action`