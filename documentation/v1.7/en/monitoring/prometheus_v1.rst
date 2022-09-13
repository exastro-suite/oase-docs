==================
Prometheus adapter
==================

| The Prometheus adapter automatically acquires Alert information(`Prometheus HTTP API - Alerts <https://prometheus.io/docs/prometheus/latest/querying/api/#alerts>`_) sent from Prometheus.
| It is possible to use multiple Prometheus servers for a single decision table.

Pre-requisites
========

* A decision table must be registered before registering a monitor adapter. For more information regarding registering Decision tables, see :doc:`../rule_definition/decision_table`.
* The Prometheus monitor adapter must be installed in advance. For more information, see :doc:`adapter_install`.

New registrations
========

| Go to the :menuselection:`System --> Monitor adapter` menu.
| Press the :guilabel:` Add Monitor destination`.
| Select "Prometheus Adapter ver1".

.. tip::
    | In order to add a monitor adapter, the user must hage permission to edit the monitor adapter menu.


.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_08_v1.6.png
   :scale: 80%
   :align: center

   Selecting Monitor adapter

| Fill in the settings items for the Prometheus adapter.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_22.png
   :scale: 35%
   :align: left

   Prometheus adapter(ver. 1) settings page


.. table:: Prometheus adapter(ver. 1) settings items

   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Setting item                                                               | Description                                                                                                                                                   |
   +============================+===========================================+=========================================================================================================================================================+
   | Name                                                                   | Required input field. Specify a name of the Monitor adapter.                                                                               |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | URI                                                                    | Specify the HTTP API URI of the data you wish to retrieve from Prometheus. For alerts, the API http://your-prom-server/api/v1/alerts is provided. |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Select decision table                                             | Select a Decision table from the pulldown menu.                                                                                        |
   +---------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Matching information      | Monitor information - Event date                            | Specify  the date/time results will be acquired from HTTP API.                                                                                                           |
   |               +--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   |               | Monitor information - Instance information                            | Specify a label that corresponds to the `Prometheus alert <https://prometheus.io/docs/prometheus/latest/querying/api/#alerts>` instance.              |
   |               +--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   |               | Condition name                                                 | Specify the item that will be evaluated by the `Prometheus alert <https://prometheus.io/docs/prometheus/latest/querying/api/#alerts>`_ .                             |
   +---------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

.. raw:: html

   <div style="clear:both;"></div>

| For example, if the following response is obtained, the Prometheus items can be specified as following.


.. code-block:: sh
   
   curl http://your-prom-server:9090/api/v1/alerts
   

.. code-block:: json

   {
       "data": {
           "alerts": [
               {
                   "activeAt": "2018-07-04T20:27:12.60602144+02:00",
                   "annotations": {},
                   "labels": {
                       "alertname": "my-alert",
                       "instance": "my-instance"
                   },
                   "state": "firing",
                   "value": "1e+00"
               }
           ]
       },
       "status": "success"
   }


.. csv-table:: API acquired results and specified items
   :header: Key specification method,Evaluated value,Description
   :widths: 20, 30, 20

   data.alerts.[].activeAt,2018-07-04T20:27:12.60602144+02:00, Update date
   data.alerts.[].annotations,(No value), Annotation
   data.alerts.[].labels.alertname,my-alert, Alert name
   data.alerts.[].labels.instance,my-instance,Instance name
   data.alerts.[].state,firing, Status
   data.alerts.[].value,1e+00, Acquired value
   status,success,API Acquired results



| After inputting all the required information, press the :guilabel:` Save` button.


Edit settings
========

| Open the :menuselection:`System --> Monitor adapter` menu and press the :menuselection:`Prometheus Adapter ver1` tab.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_20.png
   :scale: 60%
   :align: center

   Prometheus adapter list

| Click the More information button :guilabel:`` for the Monitor adapter you want to edit.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_21.png
   :scale: 60%
   :align: center

   Prometheus Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_22.png
   :scale: 60%
   :align: center

   Prometheus Adapter edit page

| After inputting all the required information, press the :guilabel:` Save` button.