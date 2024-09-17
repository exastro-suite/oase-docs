========
Log management
========

| This section explains Exastro OASE's log management.
| The log management provides the following functions for Exastro OASE and it's logs.

* Storage period settings

.. tip::
    | Logs for rule engines linked with Exastro OASE, relational databases and message queuing functions are not covered.
    | Exastro OASE's monitor adapter and action driver logs are not covered.


Log file
============

| Please see :doc:`../appendix/environment` for information regarding where the logs are output.

Log storage period settings
================

| The settings can be opened in the :menuselection:`System --> System settings` menu.
| Select :menuselection:`Log settings` from the menu on the left.

.. figure:: /images/ja/system_config/logs_column_edit.png
   :scale: 15%
   :align: left

   Log settings edit page.

.. csv-table:: Log setting items
   :header: Setting item, Description, Setting value, Initial value
   :widths: 25, 50, 20, 15

   Active Directory link, Active Directory log storage period., :kbd:`1 - 7` (days), :kbd:`7` (days)
   oase-agent, Agent process log storage period., :kbd:`1 - 7` (days), :kbd:`7` (days)
   oase-action, Action process log storage period., :kbd:`1 - 7` (days), :kbd:`7` (days)
   oase-apply, Apply process log storage period., :kbd:`1 - 7` (days), :kbd:`7` (days)
   oase-accept, oase-accept process log storage period, :kbd:`1 - 7` (days), :kbd:`7` (days)

.. raw:: html

   <div style="clear:both;"></div>

| After the settings are configured, click the :guilabel:` Save` button.
| Click the :guilabel:` Reset` button to revert any changes.