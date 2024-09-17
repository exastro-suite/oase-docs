==========
Apply rules
==========

| This section explains the functions found in the OASE Rule page.
| Rules are applied to decision tables in the following stages.

* Applying rules to Staging environment
* Validating rules
* Applying rules to Production environment
* Rule failback

Staging and Production environment
====================================

| Exastro OASE comes with a staging and production environment for each decision table.
| See below for more information regarding the different environments.

Staging environment
   | The Staging environment is used to validate the rules written in the created in the decision tables.
   | The validation done in this environment will not have any effect on the production environment or other external systems.

Production environment
   | The Production environment uses rules validated in the Staging environment to automize monitoring.

.. figure:: /images/ja/rule/staging_confirmation.png
   :scale: 45%
   :align: left
   
   Applying rules

.. figure:: /images/ja/rule/rule_00_01.png
   :scale: 40%
   :align: right

   Staging and Production environment page structure

.. raw:: html

   <div style="clear:both;"></div>


Applying rules to Staging environment
====================================

| In order to apply rules in Exastro OASE, the rules must first be validated in the Staging environment before being able to be applied to the Production environment. This ensures that the rules only carries out actions intended by the users and that they can be safely applied to the Production environment.

Uploading Decision table file
------------------------------------------

| To upload a Decision table to the Staging environment, go to the  :menuselection:`Rule --> Rule` menu and press the :guilabel:` Select file` button inside the :menuselection:`Apply rules to Staging environment` frame. Select your desired Decision table file and upload it.

.. note::
   | For information regarding creating decision tables and acquiring decision table files, see :doc:`rule_format`.
   | The user must have "Can edit" permission for the target Decision table in order to apply it to the Staging environment.

.. figure:: /images/ja/rule/rule_03_02.png
   :width: 75%
   :align: center

   Selecting Decision table file

| After selecting the Decision table file, press the :guilabel:` Upload` button in order to apply the decision table file to the staging environment.

.. note::
   | The Upload button is only visible to users that have "Can edit" permission for the Staging environment.

.. figure:: /images/ja/rule/rule_03_03.png
   :width: 75%
   :align: center

   Uploading Decision table file

Checking Rule application status
--------------------

| Uploading the Decision table file will automatically start the Rule application process.
| When uploaded, the decision table's Application status can be seen in the status field. If the Operation status says "Not validated", the rule has successfully been applied to the Staging environment.

.. tip:: 
   | If the file was not successfully uploaded, chances are that the Decision table was not written correctly.
   | If so, Press the :guilabel:`` button for the rules corresponding to the  :menuselection:`Applying rules to Staging environement` to acquire the rule's log file. Use this log file to find the source of the error. 

| The following table contains information regarding the different Operational statuses that can be displayed when applying rules to the Staging environment.

.. csv-table:: Operational status (Rules applying to Staging environment)
   :header: Status name, Description
   :widths: 20, 60

   Not applied, State of the rules right after the decision table file has been uploaded. The status will change to "Not verified" after the file has been successfully uploaded and applied to the Staging environment. If something wrong happens while uploading the file, the status will stay "Not Applied".
   Not verified, State of the rules where they have been applied to the staging environment, but not been verified. The status will change to "Verifying" "Verification NG" or "Verficiation completed" depending of the outcome of the test request. The user can also change the status to one of the aformentioned statuses on their own.
   Verifying, State of the rules where they are currently being verified by a Test request. The status will change to "Verification NG" or "Verficiation completed" depending of the outcome of the test request. The user can also change the status to one of the aformentioned statuses on their own.
   Verification NG, State of the rules where something wrong happened while verificating the rules.The status will change to "Not verified" "Verification NG" or "Verficiation completed" depending of the outcome of the test request. The user can also change the status to one of the aformentioned statuses on their own.
   Verification completed, State of the rules where they have beem successfully verified. Once the rules have reached this state, they can be applied to the Production environment by pressing the "Apply" button.The user can also change the status to "Not verified" "Verifying" or "Veryfication NG" on their own as long as the rules are not applied to the Production environment.
   Verifying completed(Applied to Production environment), State of the rules where they have been successfully been verified and applied to the Production environment. The user cannot freely change the status when this state is reached.
   Applied, State of the rules when previously applied to Staging environment but have since been updated and are not in use. Decision tables with this status will only be displayed if the :guilabel:` Include previous decision tables` button says "ON".

| The following table contains information regarding the different Working statuses that can be displayed when applying rules to the Staging environment.

.. csv-table:: Working status(Rules applying to Staging environment)
   :header: Status name, Description
   :widths: 20, 60

   Uploading, State right after the decision table has been uploaded.
   Failed to Upload, State of decision table where something wrong happened while uploading it.
   Successfully uploaded, State where the Upload process successfully ended. The Build process will automatically start and the status will change to "Building".
   Building, State where the system uses the uploaded decision table to build a project for the Decision table.
   Failed to build, State where something wrong happened during the build process.
   Build complete, State where the build process ended successfully. If the Applying to Staging environment process automatically starts, the status will change to "Applying to Staging environment".
   Applying to Staging environment, State when the project is being deployed.
   Failed to apply to Staging environment, State when somethign wrong happened when deploying.
   Applied to Staging environment, State when the deploy process ended successfully.

.. note::
   | If the "Automatic screen update" button is set to "ON" and the status says either "Uploading", "Buildling," or "Applying to Staging environment, the list will be uploaded with 5 seconds intervals.

Verifying rules
============

| Exastro OASE comes with a Test request function that allows users to verify the Uploaded rules.
| This purpose of this function is to verify that the rules works as intended by the users.
| We recommend that all rules are verified through the Test request function, but if the user does not wish to verify the rules, the users can :ref:`change_operatioin_status` to skip the verification process.

| The functions allows 2 different methods of verifying rules.Sending single requests and sending multiple requests at the same time.

.. note::
   | The user need "Can edit" or "Can view" permission for the Decision table's staging environment in order to verify the rules.
   
Start Test(Single test)
----------------------

| Single tests can be completed through the browser.

| Press the :guilabel:` Test request` button in order to open the Test request window.
| Select the desired decision table from the pulldown menu.

.. figure:: /images/ja/rule/rule_03_04.png
   :scale: 30%
   :align: left

   Test request

.. figure:: /images/ja/rule/rule_03_13_02.png
   :scale: 45%
   :align: right

   Select Decision table

.. raw:: html

   <div style="clear:both;"></div>

| Select the desired Decision table and press the :guilabel:` Test request` button.
| Press the :menuselection:`Single test` button and input the contents of the test request.

.. figure:: /images/ja/rule/rule_03_18.png
   :scale: 45%
   :align: left

   Test request settings

.. csv-table:: Test request setting items
   :header: Item name, Description
   :widths: 30, 100

   Event start date, The current date/time is automatically input.
   Request item, Set the value that will be sent through the test request to match with the Condition defined in the Decision table file. Input an expected value based on the requests submitted by the Web API and event information obtained from the Monitoring adapter.

.. raw:: html

   <div style="clear:both;"></div>

| After Inputing the value for the Test request items, press the :guilabel:` Execute` button to start the test.

Start Test(Bulk test)
----------------------

| Bulk test uses pre-prepared spreadsheet files to verify multiple rules/scenarios.

| Press the :guilabel:` Test request` button in order to open the Test request window.
| Select the desired decision table from the pulldown menu.

.. figure:: /images/ja/rule/rule_03_04.png
   :scale: 30%
   :align: left

   Single test request

.. figure:: /images/ja/rule/rule_03_13_02.png
   :scale: 45%
   :align: right

   Select Decision table

.. raw:: html

   <div style="clear:both;"></div>

| Select the desired Decision table and press the :guilabel:` Test request` button.
| Press the :menuselection:`Bulk test` button and download the excel file from by pressing the :guilabel:` Download Excel file for bulk test` button.
| Open the Excel file and Set values that will be sent through the test request to match with the Condition defined in the Decision table file. Input expected values based on the requests submitted by the Web API and event information obtained from the Monitoring adapter.

.. figure:: /images/ja/rule/rule_03_19.png
   :scale: 40%
   :align: left

   Bulk test request settings

.. figure:: /images/ja/rule/rule_04_01.png
   :scale: 25%
   :align: right

   Excel file for Bulk testing

.. raw:: html

   <div style="clear:both;"></div>

| After inputing all the test request values, save the file and press the :guilabel:` Select file`. Select the desired Excel file and press the :guilabel:` Execute` button to start the test.

Check Test results
--------------------

| When the test starts, the :menuselection:`Execution log` page will open. Here users can see the status of the test.
| The Execution status is acquired on a regular basis and the log output is output as needed.
| The Execution status is acquired as long as the Test is not finished or the Test request window is open.

.. figure:: /images/ja/rule/rule_03_25_01.png
   :scale: 40%
   :align: left

   Exection log(Single test)

.. csv-table:: Log output contents(Single test)
   :header: No., Ouput item, Description
   :widths: 5, 25, 60

   1, Staging execution start, Displays the time/date of when the Test request was executed.
   2, Request information, Displays the information input for the different Request items in the Settings tab.
   3, Execution status, Displays the Test's execution status.
   4, Match results, displays the match results of the rules when tested. Nothing will be displayed if the test is not completed or if the rule did not match.

.. raw:: html

   <div style="clear:both;"></div>

.. figure:: /images/ja/rule/rule_03_25_02.png
   :scale: 40%
   :align: left

   Execution log(Bulk test)

.. csv-table:: Log output contents(Bulk test)
   :header: No., Ouput item, Description
   :widths: 5, 25, 60

   1, Staging execution start, Displays the time/date of when the Test request was executed.
   2, File name, Displays the file name of the bulk request file.
   3, Process number, Displays the number of requests sent and numbers of requests completed.
   4, Execution status, Displays the file contents and test status for each request. If a Match result is acquired from the Decision table 、the number of the of matches and the action parameters will be displayed.

.. raw:: html

   <div style="clear:both;"></div>

| The Execution log can be downloaded as a text file.

.. figure:: /images/ja/rule/rule_03_27.png
   :scale: 40%
   :align: center

   Download Log

| After the test has completed, press the  :guilabel:` Close` button to return to the Rule page.
| Doing so will cause the system to display a message saying "Do you want to change the Operational status to "Verification completed?".
| Press the :guilabel:`OK` button to change the Operational status to "Verification completed". Pressing "Cancel" will change the status to "Verifying".

.. figure:: /images/ja/rule/rule_03_31.png
   :scale: 40%
   :align: center

   Verification completed

.. _change_operatioin_status:

Manually changing the Ooperational status
------------------------------

| If the Rule file's operational status says "Not verified", "Verifying", "Verification NG" or "Verification completed" and it has not been applied to the Production environment, the user can change the status manually.
| The status can only be changed manually by users who have "Can edit" permissions for the Staging envrionment.

.. figure:: /images/ja/rule/rule_03_06.png
   :scale: 80%
   :align: center

   Changing Operation status

Applying rules to Production environment
======================================

| Rules that have been applied to the Staging environment and their operational status says "Verification completed" can be applied to the Production environments.
| Press the :guilabel:`` button for the desired rule in the :menuselection:`Rules applying to Staging environment` in order to apply it to the Production environment.

.. warning:: 
   | Pressing the :guilabel:`` button causes the rules to process in the Production environment.

.. note::
   | The user need "Can Edit" permissions for the production decision table's production environment in order to apply the rules to the Production environment.

.. figure:: /images/ja/rule/rule_03_08.png
   :scale: 80%
   :align: center

   Applying rules to Production environment

| Applying the rules to the Production environment causes the Operational status and the Working status to update.
| If the "Rules applying to Production envrionment" rule's operational status says "Applied to Production environment", the rule has been successfully applied.

.. figure:: /images/ja/rule/rule_03_09.png
   :scale: 80%
   :align: center

   Rules applying to Production environment

| The Operational statuses in the "Rules applying to Production envrionment" field are as following.

.. csv-table:: Operational status(Rules applying to Production environment)
   :header: Status name, Description
   :widths: 20, 60

   Not applied to Production, State of Rules that are being applied from Staging environment to Production environment. If the application process fails, the status will stay the same.
   Applied to Production, State of currently rules applied to the Production environment.
   Production application finished, State of the rules when previously applied to the Production environment but have since been updated and are not in use. Decision tables with this status will only be displayed if the :guilabel:` Include previous decision tables` button says "ON".

| The Working statuses in the "Rules applying to Production envrionment" field are as following.

.. csv-table:: Working status (Rules applying to Production environment)
   :header: Status name, Description
   :widths: 20, 60

   Applying to Production, State of Rules that are being applied from Staging environment to Production environment or are being re-applied by failback.
   Failed to apply to Production, State where something went wrong during the Production application process.
   Application to Production completed, State where the rules have successfully been applied to the Production environment

Rule failback
================

| The Rule failback allows users to revert rules to previous versions in cases where there is something wrong with the Rule Description.

| Press the :guilabel:` Include previous rules` button on the top of the  :menuselection:`Rules applying to Production environment` panel and have the system display previous applied rules.
| The :guilabel:` Include previous rules` button displays "OFF" by default. Pressing it switches the state of the function between ON and OFF.

| In order to check rules previously applied to the Production environment, press the download button :guilabel:`` and open the downloaded Decision table file.
| If there are no problems with the contents of the Decision table file, press the failback button :guilabel:`` in order to start the Production environment application(Failback) process.

.. note::
   | The user need "Can Edit" permissions for the production decision table's production environment in order to apply the rules to the Production environment.

.. figure:: /images/ja/rule/rule_03_12.png
   :scale: 80%
   :align: center

   Re-applying rules from the Production applied rule history

Rule evaluation results
================

| For more information regarding the Rule's evaluation results, see :doc:`../rule_maintenance/action_history`.