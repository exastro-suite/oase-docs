==================
Event requests
==================

| This section explains the information needed in order to request events(Send event message) to decision tables.


Property
==========

| The property specified when API requesting are as following

.. table:: Event request property

   +---------------+----------+----------------------------+------------------------------------------------+
   | Property    | Data type | Description/Setting value                |  Setting value description                                    |
   +===============+==========+============================+================================================+
   | decisiontable | Caracter string   | Decision table name                                                     |
   +---------------+----------+---------------+-------------------------------------------------------------+
   | requesttype   | Caracter string   | Request type                                                              |
   +               +          +----------------------------+------------------------------------------------+
   |               |          | * 1                        | Selects Production as the request destination.   |
   +               +          +----------------------------+------------------------------------------------+
   |               |          | * 2                        | Selects Staging as the request destination.      |
   +---------------+----------+----------------------------+------------------------------------------------+
   | eventdatetime | Caracter string   | Event start date/time                                                            |
   +               +          +----------------------------+------------------------------------------------+
   |               |          | + \- (Hyphen)            | Does not specify any time.                           |
   +               +          +----------------------------+------------------------------------------------+
   |               |          | + YYYY/MM/DD HH:mm:ss      | Sets the Event start time/date.                 |
   +---------------+----------+----------------------------+------------------------------------------------+
   | eventinfo     | Array     | Event information                                                                |
   +               +          +                                                                             +
   |               |          | The number of events and condition expressions defined in the Decision table must be the same.      |
   +---------------+----------+-----------------------------------------------------------------------------+


Request header
================

| The Header information needed for API requesting are as following.

.. table:: Request header

   +---------------+--------------------------------------+--------------------------------------+
   | Header      |Description/Setting value                           | Setting value description                             |
   +===============+======================================+======================================+
   | Content-Type  | Contents format                                                              |
   +               +--------------------------------------+--------------------------------------+
   |               | * application/json                   | Supports JSON format only.    |
   +---------------+--------------------------------------+--------------------------------------+
   | Authorization | Authentication information                                                                    |
   +               +--------------------------------------+--------------------------------------+
   |               | * Bearer: <token>                    | Specifies paid out token. |
   +---------------+--------------------------------------+--------------------------------------+

Response
==========

| The API Request responses are as following.

+------------+--------------------------------------------------+-------------------------------------------------------------------+
| Property | Description/Return value                                      | Return value description                                                       |
+============+==================================================+===================================================================+
| result     | API execution results                                                                                                 |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * true                                           | Is output when the API Execution succeeds.                          |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * false                                          | Is output when the API Execution fails.                          |
+------------+--------------------------------------------------+-------------------------------------------------------------------+
| msg        | Messages for the API Execution results.                                                                               |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Accept request.                                | Request is accepted.                                |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Unmatch, Number of event information elements. | Number of Event information components does not match.                              |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Invalid request. Must be POST. Not GET.        | Request is invalid. The request must be POST and cannot be GET. |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Invalid request format. Must be JSON.          | Request format is invalid. The format must be JSON.             |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Invalid request type.                          | Request type is invalid.                                      |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Invalid request.                               | Request is invalid.                                            |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * Unexpected error.                              | An unexpected error occurred.                                              |
+            +--------------------------------------------------+-------------------------------------------------------------------+
|            | * other error.                                   | Other error occurred.                                                |
+------------+--------------------------------------------------+-------------------------------------------------------------------+
| trace_id   | Event serial number. Used for tracking acquired event messages.                                             |
+------------+--------------------------------------------------+-------------------------------------------------------------------+

Example
=======

| The request below is sent to the decision table, *decisiontable001*, as an example. The response can be seen at the bottom.

Request
----------

.. code-block:: bash

   curl -X POST -k 'https://<fqdn_or_ip_address>/oase_web/event/event/eventsrequest' \
        -H 'accept: application/json' \
        -H 'Authorization: Bearer <access_token>' \
        -d '{
             "decisiontable": "decisiontable001",
             "requesttype":   "1",
             "eventdatetime": "2018/12/13 15:16:29",
             "eventinfo":     ["This is alert message.","hostname"]
            }'

Response
----------

.. code-block:: json

   {"result": true, "msg": "Accept request.", "trace_id": "TOS_20210412053112220048_0000000010"} 

