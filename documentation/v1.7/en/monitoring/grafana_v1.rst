===============
Grafana adapter
===============

| The Grafana adapter automatically acquires Alert information(`Grafana HTTP API - Alerting API <https://grafana.com/docs/grafana/latest/http_api/alerting/#alerting-api>`_) sent from Grafana.
| It is possible to use multiple Grafana servers for a single decision table.

Pre-requisites
========

* A decision table must be registered before registering a monitor adapter. For more information regarding registering Decision tables, see :doc:`../rule_definition/decision_table`.
* The Grafana monitor adapter must be installed in advance. For more information, see :doc:`adapter_install`.

New registrations
========

| Go to the :menuselection:`System --> Monitor adapter` menu.
| Press the :guilabel:` Add Monitor destination`.
| Select "Grafana Adapter ver1".

.. tip::
    | In order to add a monitor adapter, the user must hage permission to edit the monitor adapter menu.


.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_08_v1.6.png
   :scale: 80%
   :align: center

   Selecting Monitor adapter

| Fill in the settings items for the Grafana adapter.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_27.png
   :scale: 35%
   :align: left

   Grafana adapter(ver. 1) settings page


.. table:: Grafana adapter(ver. 1) settings items

   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Setting item                                                               | Description                                                                                                                                                    |
   +============================+===========================================+=========================================================================================================================================================+
   | Name                                                                   | Required input field. Specify a name of the Monitor adapter.                                                                                      |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | URI                                                                    | Specify the HTTP API URI of the data you wish to retrieve from Grafana. For alerts, the API http://your-grafana-server/api/alerts is provided.|
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | User name                                                               |Specify a user that can use Grafana HTTP API.                                                                                                     |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Password                                                             | Specify the password for the user that will use the Grafana HTTP API.                                                                                   |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Select decision table                                             | Select a Decision table from the pulldown menu.                                                                                        |
   +---------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Matching information      | Monitor information - Event date                            | Specify  the date/time results will be acquired from HTTP API.                                                                                                           |
   |               +--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   |               | Monitor information - Instance information                            | Specify a label that corresponds to the `Grafana alert <https://grafana.com/docs/grafana/latest/http_api/alerting/#alerting-api>`_ instance.              |
   |               +--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   |               | Condition name                                                 | Specify the item that will be evaluated by the `Grafana alert <https://grafana.com/docs/grafana/latest/http_api/alerting/#alerting-api>`_.                          |
   +---------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

.. raw:: html

   <div style="clear:both;"></div>

| For example, if the following response is obtained, the Grafana items can be specified as following.

.. code-block:: sh

   curl http://your-grafana-server:3000/api/alerts/

.. code-block:: json

   [
     {
       "id": 1,
       "dashboardId": 1,
       "dashboardUId": "ABcdEFghij"
       "dashboardSlug": "sensors",
       "panelId": 1,
       "name": "fire place sensor",
       "state": "alerting",
       "newStateDate": "2018-05-14T05:55:20+02:00",
       "evalDate": "0001-01-01T00:00:00Z",
       "evalData": "evalMatches": [
         {
           "metric": "movement",
           "tags": {
             "name": "fireplace_chimney"
           },
           "value": 98.765
         }
       "executionError": "",
       "url": "http://grafana.com/dashboard/db/sensors"
     }
   ]


.. csv-table:: API acquired results and specified items
   :header: Key specification method,Evaluated value
   :widths: 20, 30

   [].dashboardId,1
   [].dashboardUId,ABcdEFghij
   [].dashboardSlug,sensors
   [].panelId,1
   [].name,fire place sensor
   [].state,alerting
   [].newStateDate,2018-05-14T05:55:20+02:00
   [].evalDate,0001-01-01T00:00:00Z
   [].evalData.evalMatches.metric,movement
   [].evalData.evalMatches.tags.name,fireplace_chimney
   [].evalData.evalMatches.value,98.765
   [].executionError,
   [].url,http://grafana.com/dashboard/db/sensors


| After inputting all the required information, press the :guilabel:` Save` button.


Edit settings
========

| Open the :menuselection:`System --> Monitor adapter` menu and press the :menuselection:`Grafana Adapter ver1` tab.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_28.png
   :scale: 60%
   :align: center

   Grafana Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_29.png
   :scale: 60%
   :align: center

   Grafana Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_31.png
   :scale: 60%
   :align: center

   Grafana Adapter edit page

| After inputting all the required information, press the :guilabel:` Save` button.