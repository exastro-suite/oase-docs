==========
Create Rules
==========

| The link between messages acquired from Monitor adapters/Web API and the measures/actions are managed as Rules.
| Decision table files are spreadsheet files where rules are defined.


Acquire Decision table file
==================================

| In order to acquire a Decision table file from a newly added Decision table, open the :menuselection:`Rule --> Decision table` menu and press the target Decision table's :guilabel:`` button.

.. figure:: /images/ja/decision_table/decision_table_04.png
   :scale: 50%
   :align: center

   Downloading new Decision table files
 
| In order to acquire a Decision table from an already registered Decision table, open the :menuselection:`Rule --> Rule` page and press the target Decision table's :guilabel:`` button.

.. figure:: /images/ja/rule/rule_03_07.png
   :scale: 50%
   :align: center

   Downloading registered Decision table files


Writing rules and running actions
==============================

| If a message matches with a rule, the method(s) specified in the Decision table file's Action part will be executed.
| If a message matches with multiple ruless, the actions will normally be executed starting from the rule highest in the Decision table.

Rule
   | Defines the conditions that a message received/retrieved by Exastro OASE must meet for the Actions to be executed.
   | In Exastro OASE, Rules are managent within the Decision table files.

Match
   | A condition in which a message received/retrieved by Exastro OASE satisfies the rule-defined conditions.
      

| This section explains what happens when the rules in :numref:`rule_and_action` are written in a Decision table.

| **Pattern 1** : If an alert with the name "mysql is down" is received, a mail containing DB Failure information will be sent, as only it only matches with Rule 2.
| **Pattern 2** : If an alert with the name "httpd is down" is received, a mail containing Web Failure information will be sent and Apache will be started, as it matches with both Rule 1 and Rule 3.

.. csv-table:: Pseudo rules
   :name: rule_and_action
   :escape: \
   :header: Condition, Condition, Method
   :widths: 30, 60, 50

   Rule 1, Alert name is "httpd is down", Sends a mail containing Web failure information.
   Rule 2, Alert name is "mysql is down", Sends a mail containing DB failure information.
   Rule 3, Alert name is "httpd is down", Starts Apache.

.. note::
   | The system will behave differently if :doc:`correlation` is used.

Decision table Structure
==================================

| Decision table files are constructed by 2 sheets. See below for more information.

Tables sheet
   | Defines rules.

example sheet
   | Contains examples and instructions on how to write rules.

Writing rules
================

Since actions are executed based on the Test request/Rule match results, the Tables sheet in the Decision table must contain conditions which will be used as criteria.

.. figure:: /images/ja/decision_table/decision_table_20.png
   :scale: 100%
   :align: center

   Decision table file(Tables sheet)


.. csv-table:: Tables sheet(Rule management sheet)
   :header: Structure component, Description
   :widths: 20, 60

   Comment part, Colored green and can be used freely to input whatever character strings the user desires.
   Condition part(Conditional expression),Colored light blue and is used to define conditions used to evaluate alert messages.
   Action part, Colored yellow and is used to define the method contents.
   Action condition part, Colored red and is used to define the rule application conditions.

| The following section explains the different items.


Comment part
----------

| The green parts in the :menuselection:`Tables sheet`. Can be used freely to input whatever character strings the user desires.
| The contents written in these cells will not have any effect on the system.

.. figure:: /images/ja/decision_table/decision_table_30.png
   :scale: 75%
   :align: center

   Comment part

.. csv-table:: Comment part structure
   :header: Item, Description, Input example
   :widths: 20, 100, 20

   Rule description, Cells that users can use freely to input whatever character strings they want. Does not have any effect on the system. Can be used to contain comments regarding the rules., Acquires log


Condition part
------

| The light blue parts in the :menuselection:`Tables sheet`. Defines conditions used to evaluate alert messages.
| Items for the Conditional expressions written when the Decision table was created are displayed.

.. include:: ../include/decision_table_conditions.rst

.. figure:: /images/ja/decision_table/decision_table_31.png
   :scale: 75%
   :align: center

   Condition part

.. note::
   | The "Time[HH:mm](From-to)" input when the Decision table was created/cloned is divided in two rows in the Excel file,"[HH:mm](from)" and "[HH:mm](to)". Input data for both Start date and End date.

.. note::
   | If the Condition part is blank, the condition will match with any value. Note that it is not possible for a single rule to have all it's condition parts be blank.


Action Part
------------

| The yellow parts in the :menuselection:`Tables sheet`. Defines the contents of the Actions/Methods.
| It is possible to add the following settings for the actions in the Action part.

* Set an approval mail before running the action.
* Set number of retries and retry interval time if the action fails to run.
* Set amount of alert messages and interval time between they arrive to not execute the specified action. Used to prevent actions being executed when large quantities of the same alert are received.

.. figure:: /images/ja/decision_table/decision_table_32.png
   :scale: 100%
   :align: center

   Action Part

| The following table :numref:`action_part` explains the different items in the Action part.
|  See the next sections for more information regarding :doc:`action`, :doc:`suppression` and :doc:`correlation`

.. csv-table:: Action part structure
   :name: action_part
   :escape: \
   :header: Item, Description, Input example
   :widths: 30, 60, 50

   Rule name (Required), Specifies the Name of the rule.,Restart process.
   Event,Used to describe expected events. Is written in the Action history's and ServiceNow's incident management's Description field., Detected no response from the process.
   Method overvew,Used to describe the contents of the method/action. Is written in the Action history's and ServiceNow's incident management's Description field., Will Restart the process.
   Action type,Select the driver which will run the method/action. See :doc:`action` for more information., ITA(ver1)
   Action parameter information,Describes the parameter information sent to the Drivers. See :doc:`action` for more information,CONDUCTOR_CLASS_ID=1\,OPERATION_ID=1
   Approval mail parameter information,Describes parameter information for the Apprival mail.See :doc:`approval` for more information,MAIL_NAME=oasetest\,MAIL_TO=aaa@aaa.com;bbb@bbb.com\,MAIL_CC=ccc@ccc.com\,MAIL_BCC=ddd@ddd.com\,MAIL_TEMPLATE=test_template
   Retry interval, Describes the time (seconds) before retrying process when failed.,5
   Retry times,Describes the amount of process will be executed, with additional amounts being executed if the process fails. E.g. Input 2 for 1 retry.,1
   Deterrent interval, Is used by the :doc:`suppression`. The :doc:`suppression` is used to prevent the same action being executed multiple times when recieving large amounts of the same alert at the same time. Describes the time (seconds) between incoming alerts before the action will be blocked.,120
   Deterrent number, Is used by the :doc:`suppression`. Describes how many alerts the system will ignore. If the number of incoming alerts exceeds the set deterrent number, all actions are executed until the next deterrent interval starts.,100
   Condition number, Is used by the :doc:`correlation`.The rule is true only true if the amount of messages matches the set Condition number.,2
   Condition period(seconds), Is used by the :doc:`correlation`. Describes the period in which the Condition number is active.,600
   Big group, Is used by the :doc:`correlation`.Groups small correlation groups.,Group1
   Priority, Is used by the :doc:`correlation`. Describes the priority of the small groups. If multiple small groups are true, the group with the highest priority will be used. The smaller the number, the higher the priority.,1
   Small group, Is used by the :doc:`correlation`. Groups rules for correlation analysis,Group1-2
   Priority, Is used by the :doc:`correlation`. Describes the priority of the rules within the small groups. 
  The rule with the highest priority triggers the start of the collation analysis, and the action of the lowest rule is executed. The lower the number, the higher the priority.,2



Action Condition Part
----------------

| The red parts in the :menuselection:`Tables sheet`. Defines when the rules are activated and deactivated.

.. figure:: /images/ja/decision_table/decision_table_33.png
   :scale: 75%
   :align: center

   Action Condition Part

| See the next section for more information regarding the :numref:`action_condition` part.

.. csv-table:: Action Condition part structure
   :name: action_condition
   :escape: \
   :header: Item, Description, Input example
   :widths: 30, 60, 50

   Date Effective, Allows users to set the date in which the rule is effective. Set in the following format: :program:`yyyy-mm-dd HH:mm`. Leave the field blank to not set an effective date. If set to 2020-01-01 01:00, all events after 2020-01-01 01:00:01 will be matched.,2020-01-01 01:00
   Expiration Date, Allows users to set the date the rule is deactivated. Set in the following format: :program:`yyyy-mm-dd HH:mm`. Leave the field blank to not set an expiration date. If set to 2020-01-01 01:00, all events after 2020-01-01 01:00:00 will not be matched,2020-01-01 01:00
