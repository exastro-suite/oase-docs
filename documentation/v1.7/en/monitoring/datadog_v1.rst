===============
Datadog adapter
===============

| The Datadog adapter automatically acquires (`Event information <https://docs.datadoghq.com/ja/api/latest/events/>`_)sent from Datadog.
| It is possible to use multiple Datadog endpoints for a single decision table.

Pre-requisites
========

* A decision table must be registered before registering a monitor adapter. For more information regarding registering Decision tables, see :doc:`../rule_definition/decision_table`.
* The Datadog monitor adapter must be installed in advance. For more information, see :doc:`adapter_install`.

New registrations
========

| Go to the :menuselection:`System --> Monitor adapter` menu.
| Press the :guilabel:` Add Monitor destination`.
| Select "Datadog Adapter ver1".

.. tip::
    | In order to add a monitor adapter, the user must hage permission to edit the monitor adapter menu.


.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_08_v1.6.png
   :scale: 80%
   :align: center

   Selecting Monitor adapter

| Fill in the settings items for the Datadog adapter.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_36.png
   :scale: 35%
   :align: left

   Datadog adapter(ver. 1) settings page


.. table:: Datadog adapter(ver. 1) settings items

   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Setting item                                                               | Description                                                                                                                                                    |
   +============================+===========================================+=========================================================================================================================================================+
   | Name                                                                   | Required input field. Specify a name of the Monitor adapter.                                                                                  |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | URI                                                                    | Specify the HTTP API URI of the data you wish to retrieve from Datadog. For alerts, the API https://api.datadoghq.com/api/v1/events is provided.|
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | API KEY                                                                | Specify an API Key that can be used for the Datadog HTTP API                                                                                                    |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | APPLICATION KEY                                                        | Specify an Application key that can be used for the Datadog HTTP API.                                                                                         |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Proxy                                                               | Specify a Proxy server that can connect to Datadog.(Optional)                                                                                        |
   +----------------------------+-------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Select decision table                                             | Select a Decision table from the pulldown menu.                                                                                        |
   +---------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Matching information      | Condition name                                                 |Specify the item that will be evaluated by the `Datadog alert <https://docs.datadoghq.com/ja/api/latest/events/>`_.                                                  |
   +---------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

.. raw:: html

   <div style="clear:both;"></div>

| For example, if the following response is obtained, the Datadog items can be specified as following.


.. code-block:: sh

   curl https://api.datadoghq.com/api/v1/events

.. code-block:: json

   {
      "events": [
         {
            "alert_type": "info",
            "date_happened": 46337152,
            "device_name": "cillum",
            "host": "ut pariatur reprehenderit culpa",
            "id": 97756271,
            "id_str": "do cupidatat qui Duis",
            "payload": "{}",
            "priority": "normal",
            "source_type_name": "ex cillum ut",
            "tags": [
            "environment:test"
            ],
            "text": "Oh boy!",
            "title": "Did you hear the news today?",
            "url": "Duis sit"
         }
      ],
      "status": "ullamco aliquip velit pariatur"
   }

.. csv-table:: API acquired results and specified items
   :header: Key specification method,Evaluated value
   :widths: 20, 30

   evnets.[].alert_type,info
   evnets.[].date_happened,46337152
   evnets.[].device_name,cillum
   evnets.[].host,"ut pariatur reprehenderit culpa"
   evnets.[].id,97756271
   evnets.[].id_str,"do cupidatat qui Duis"
   evnets.[].payload,"{}"
   evnets.[].priority,normal
   evnets.[].source_type_name,"ex cillum ut"
   evnets.[].tags.[],"environment:test"
   evnets.[].text,Oh boy!
   evnets.[].title,Did you hear the news today?
   evnets.[].url,Duis sit"
   status,"ullamco aliquip velit pariatur"

| After inputting all the required information, press the :guilabel:` Save` button.


Edit settings
========

| Open the :menuselection:`System --> Monitor adapter` menu and press the :menuselection:`Datadog Adapter ver1` tab.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_37.png
   :scale: 60%
   :align: center

   Datadog adapter list

| Click the More information button :guilabel:`` for the Monitor adapter you want to edit.

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_38.png
   :scale: 60%
   :align: center

   Datadog Adapter information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/monitoring_adapter/monitoring_adapter_40.png
   :scale: 60%
   :align: center

   Datadog Adapter edit page

| After inputting all the required information, press the :guilabel:` Save` button.