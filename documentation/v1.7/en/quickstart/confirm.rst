================
Confirm Action
================

| The following section explains how to check acquired alert messages.


Procedure
============

| It is possible to manually send alert messages for cases where it might not be possible to have alert messages sent.

.. danger::
    | If Exastro OASE is linked to an automation software, a modification operation will be run to the production environment.
    | We recommend checking the decision table and action driver settings before proceeding.

.. code-block:: bash

  curl -X POST -k 'https://<ip_address_or_fqdn>/oase_web/event/event/eventsrequest' \
   -H 'accept: application/json' \
   -H 'Authorization: Bearer <access_token>' \
   -d '{"decisiontable":"New decision table","requesttype":"1","eventdatetime":"<current_datetime>","eventinfo":["This is test alert."]}'

| Modify the following parameters to fit your environment.

*ip_address_or_fqdn*
  | Input an IP address or FQDN that can connect to Exastro OASE.

*access_token*
  | Input the token paid out in the :doc:`rule` section.

*current_datetime*
  | Input the current date/time in the following format: (YYYY/MM/DD HH:mm:ss).


Request history
==============

| This section explains how to check alert messages(requests) sent from monitor applications.
| The Request history can be seen in the :menuselection:`Rule --> Request history` menu.

.. figure:: /images/ja/quickstart/request_history_01.png
   :width: 800px
   :align: center

Request history

.. note::
  | All acquired requests are displayed in this page.


Action history
==============

| The following section explains how to check that the rules written in the decision table have matched the alert messages(requests) sent from monitor applications.
| The Action history can be seen in the  :menuselection:`Rule --> Action history` menu.

.. figure:: /images/ja/quickstart/action_history_01.png
   :width: 800px
   :align: center

.. note::
  | All actions linked to matched rules are displayed in this page.