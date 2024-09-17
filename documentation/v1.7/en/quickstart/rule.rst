======================
Creating and applying rules
======================

| Rules defines what actions will be executed when specific alerts are recieved from the Monitor applications.
| This section explains how to create and apply said rules.


.. _new_rule:

Create rule
==========

| The user will need a decision table when creating rules.
| Download decision table files from the :menuselection:`Rule --> Decision table` menu.
| Go to the Decision table menu and press the Download button next to the decision table we created earlier in the XX section:doc:`decision_table` で作成した :program:`新規ディシジョンテーブル` のダウンロードボタン :guilabel:`` 、ディシジョンテーブルファイルをダウンロードします。


.. figure:: /images/ja/quickstart/new_rule_01.png
   :width: 400px
   :align: center

   Download Decision table

| Open the Decision table file and add the rules.
| The contents of the rules we will add have been shortened. For more information, please see :doc:`../rule_definition/action`.

| The most important items are as following.

Alert message(Regulard expression match)
  | Defines the maching conditions for the alert messages acquired from the Monitor applications. In this quickstart guide, all alerts will be matched to run ITA.

Action parameter information(Required)
  | Specifies the Automation software action drivers and parameters.

  | :program:`ITA_NAME`
  |   Specify the name of the action driver created in the :doc:`action_driver` section.
  | :program:`CONDUCTOR_CLASS_ID`
  |   Specify the ITA Conductor class ID that will be executed from Exastro OASE.
  | :program:`OPERATION_ID`
  |   Specify the Operation ID linked to the ITA Conductor that will be executed from Exastro OASE.



| For more information regarding all the different items used in this guide, please see the table below.

+-------------------------------------+---------------------------------------------------------------------------+
| Rule description                         | Quickstart                                                          |
+-------------------------------------+---------------------------------------------------------------------------+
| Alert message (Match regular expression) | .*                                                                        |
+-------------------------------------+---------------------------------------------------------------------------+
| Rule name (Required)                   | New rule                                                              |
+-------------------------------------+---------------------------------------------------------------------------+
| Event (Required)                    | Alert detected                                                            |
+-------------------------------------+---------------------------------------------------------------------------+
| Action (Required)                    | Run ITA                                                                 |
+-------------------------------------+---------------------------------------------------------------------------+
| Action type                      | ITA(ver1)                                                                 |
+-------------------------------------+---------------------------------------------------------------------------+
| Action parameter information (Required)    | ITA_NAME=NewZABBIXActionDriver,CONDUCTOR_CLASS_ID=1,OPERATION_ID=1 |
+-------------------------------------+---------------------------------------------------------------------------+
| Confirmation mail parameter information (Required)    | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Retry interval (Required)                | 1                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Retry number (Required)                | 1                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Deterrence time (Required)                    | 0                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Condition number (Required)                    | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Condition time(seconds) (Required)                | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Big group (Required)                  | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Priority (Required)                    | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Small group (Required)                  | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Priority (Required)                    | X                                                                         |
+-------------------------------------+---------------------------------------------------------------------------+
| Activate date                              |                                                                           |
+-------------------------------------+---------------------------------------------------------------------------+
| Deactivate date                              |                                                                           |
+-------------------------------------+---------------------------------------------------------------------------+

.. figure:: /images/ja/quickstart/new_rule_02.png
   :width: 800px
   :align: center

   Decision table file

| Save the file after inputing the rule(s).

Pay out new Token
======================

| In the quickstart guide, we will insert the alert information using Exastro OASE's Web API. In this section, we will pay out the token needed in order to use the Web API.
| Tokens can be paid out from the :menuselection:`Rule --> Pay out Token` menu.
| For more information regarding Tokens, please see :doc:`../api/token`.

| Press the :guilabel:` Pay out new token` button at the top of the screen.

.. figure:: /images/ja/quickstart/new_token_01.png
   :scale: 30%
   :align: left

   Token Pay out

Token name
   | Input the name of the Token.
   | In the Quickstart guide, the name :program:`New token` will be used.

Expiration date
   | Specify the expiration date for the Token
   | In the Quickstart guide, no exppiration date will be set(blank).

Permission settings
   | Define permissions for the user groups.
   | In the Quickstart guide, all user groups will have :program:`With permission`.

.. raw:: html

   <div style="clear:both;"></div>

| After inputting the required information, press :guilabel:` Pay out token`.
| The token will be displayed on the screen. Users can check the token later in the Token menu.


Test rules
============

| Rules can be configured from the :menuselection:`Rule --> Rule` menu.
| Click the :guilabel:` Select file` button and select the Decision table file created in the :ref:`new_rule` section.
| Check that you have selected the correct file and press the :guilabel:` Upload` button.

.. figure:: /images/ja/quickstart/rule_apply_01.png
   :width: 800px
   :align: center

| Check that the :menuselection:`Operation status` displays :program:`Applied to Staging` and click the :guilabel:` Test request` button to test the rule(s).

.. tip:: 
   | If an error occurs when uploading the file, press the Download button :guilabel:`` and check the log file in the downloaded zip file


.. figure:: /images/ja/quickstart/test_request_01.png
   :scale: 30%
   :align: left

   Test request (Select Decision table)

Select Decision table name
   | Select the Decision table you want to test.
   | In this guide, we will select :program:`New decision table`.

.. raw:: html

   <div style="clear:both;"></div>

| Click :guilabel:` Test request settings`.

.. figure:: /images/ja/quickstart/test_request_02.png
   :scale: 30%
   :align: left

   Test request(Configure Test request)

Alert message
   | Set the message that will be sent through the Test request.
   |  Select :menuselection:`Single test` and write :kbd:`This is a test alert.`.

.. raw:: html

   <div style="clear:both;"></div>

| Click :guilabel:` Execute`.

.. figure:: /images/ja/quickstart/test_request_03.png
   :scale: 30%
   :align: left

   Test request(Configure Test request)

| Check that the message sent through the test request matches with the rule defined in the decision table.

.. raw:: html

   <div style="clear:both;"></div>

| Click the :guilabel:` Close` button.
| We will need to check that the operation status says :program:`Test completed`,so click :guilabel:`OK`.


Applying rules to production environment.
================

| Rules can be applied to the production environment in the :menuselection:`Rule --> Rule` menu.
| Click the :guilabel:`` button on the top of the :menuselection:`Staging applied rules` screen.

| The :menuselection:`Operation status` should change to :program:`Succesfully applied to Production`.

.. figure:: /images/ja/quickstart/rule_apply_02.png
   :width: 800px
   :align: center

| ITA's Conductor will be executed when Exastro OASE recieves alert messages from the Monitor application.