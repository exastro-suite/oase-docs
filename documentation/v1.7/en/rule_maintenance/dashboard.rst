==============
Dashboard
==============

| This section explains the Dashboard function in Exastro OASE.
| The Dashboard function uses Exastro OASE's acquired event information and visualizes how much it matches the rules.
| By defining rules for the non-matched events allows users to get closer to 100% coverage, enhancing the system automation.


Page structure
========

| The Dashboard page structure are as following.

.. figure:: /images/ja/dashboard/dashboard_01.png
   :scale: 40%
   :align: center

   Page structure


| The different panels in the Dashboard page are as following.

.. csv-table:: Dashboard page panels
   :header: Panel, Description
   :widths: 20, 60

   Coverage(24h), Displays the rate of matched and non-matched rules in the last 24 hours in a pie graph.
   Match ranking(24h), Displays a ranking of the most matched rules in the last 24 hours in a pie graph.
   Non-match ranking(24h), Displays a ranking of the most non-matched rules in the last 24 hours in a pie graph.
   Request number(Hourly), Displays a bar graph of the number of matched and unmatched requests in the time period of the last 30 days until 24:00 of the previous day.
   Request number(Monthly), Displays a bar graph of the number of matched and unmatched requests from the last 12 months.


Panel structure
==========

Coverage(24h)
---------------

| The Coverage graph uses the events acquired by Exastro OASE and displays the rate of events matched with a rule and events that did not match.
| The Coverage(24h) displays the rate of the events from the last 24 hours.

.. figure:: /images/ja/dashboard/dashboard_02.png
   :scale: 80%
   :align: left

   Coverage(24h) page structure

.. csv-table:: Coverage(24h) items
   :header: Item, Description
   :widths: 20, 60

   Item name, Name of the graph.
   Pie graph, Pie graph displaying events that matched with rules and events that did not match with any rules in the last 24 hours.
   Match, Number of events that matched with rules from decision tables in the last 24 hours.
   Unmatch, Number of events that did not match with rules from decision tables in the last 24 hours.

.. raw:: html

   <div style="clear:both;"></div>

Match ranking(24h)
----------------------

| The Match ranking(24h) displays a ranking of the most matched rules in the last 24 hours.

.. figure:: /images/ja/dashboard/dashboard_03.png
   :scale: 80%
   :align: left

   Match ranking(24h) page structure

.. csv-table:: Match ranking(24h) items
   :header: Item, Description
   :widths: 20, 60

   Item name, Name of the graph.
   Pie graph, A pie graph displaying the most matched rules in the last 24 hours.
   Ranking item, Items displaying the Decision table name, event information and number of events. Ranked from 1st to 5th.
   Detailed information, Pressing this button moves the user to the Request history where the target event information is filtered.
   Other, The "Other" item contains all items ranked 6 and below.

.. raw:: html

   <div style="clear:both;"></div>

Non-match ranking(24h)
--------------------------

| The Non-match ranking(24h) displays a ranking of events that did not match with any rules.

.. figure:: /images/ja/dashboard/dashboard_04.png
   :scale: 80%
   :align: left

   Non-match(24h) page structure

.. csv-table:: Non-match(24h) itemms
   :header: Item, Description
   :widths: 20, 60

   Item name, Name of the graph.
   Pie graph, A pie graph displaying all events that did not match with any rules in the last 24 hours.
   Ranking item, Items displaying the Decision table name, event information and number of events. Ranked from 1st to 5th.
   Detailed information, Pressing this button moves the user to the Request history where the target event information is filtered.
   Other, The "Other" item contains all items ranked 6 and below.

.. raw:: html

   <div style="clear:both;"></div>

Request number(Hourly)
------------------------

| The Request number(Hourly) item displays events that did or did not match with a rule on an hourly basis.

.. figure:: /images/ja/dashboard/dashboard_05.png
   :scale: 50%
   :align: left

   Request number(Hourly) page structure

.. csv-table:: Request number(Hourly) items
   :header: Item, Description
   :widths: 20, 60

   Item name, Name of the graph.
   Bar graph, A bar graph displaying the number of requests that matched/did not match with rules in the last 30 days. Divided on an hourly basis. The X axis displays number of events. The Y axis displays hours.

.. raw:: html

   <div style="clear:both;"></div>

Request number(Monthly)
--------------------

| The Request number(Monthly) item displays events that did or did not match with a rule on a monthly basis.

.. figure:: /images/ja/dashboard/dashboard_06.png
   :scale: 50%
   :align: left

   Request number(Monthly) page structure

.. csv-table:: Request number(Monthly) items
   :header: Item, Description
   :widths: 20, 60

   Item name, Name of the graph.
   Bar graph, A bar graph displaying the number of requests that matched/did not match with rules in the last 12 months days. Divided on aa monthlybasis. The X axis displays number of events. The Y axis displays hours.

.. raw:: html

   <div style="clear:both;"></div>
