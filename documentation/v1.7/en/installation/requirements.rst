============
System requirements
============

| This section explains the system requirements for using and constructing Exastro OASE.

Hardware requirements(Reference values)
========================

| The following are the recommended server specs for constructing Exastro OASE.

.. csv-table::
   :widths: 10, 50

   OS,     Linux Centos7
   CPU,  Quad core
   Memory, 8GB
   HDD,    100GB


.. note:: These values might differ depending on the linking monitoring application, number of rules, alerts and drivers.


System structure pattern
====================

| Web contents, BackYard contents and Databases can be used in the following server structures.

.. csv-table::
   :header: Structure, Description, Features
   :widths: 16, 20, 15

   The All-in-one structure is the most simple and cheapest structure OASE can be built on.
   The High availability structure is capable of higher availability and expansions. It is not subject to SPoF (Single Point of Failure), meaning that the service can keep running even if something happens to the main structure.

The following diagrams illustrates said structures.

.. figure:: /images/ja/introduction/deploy_all_in_one.png
   :scale: 33%
   :align: left

   All in one structure diagram

.. figure:: /images/ja/introduction/deploy_high_availability.png
   :scale: 33%
   :align: right

   High availability structure diagram

.. raw:: html

   <div style="clear:both;"></div>

Communication requirements
========

| The communication requirements for the different services are as following.

.. csv-table:: Communication requirements list
   :header: FROM, TO, Protocol, Main application
   :widths: 20, 20, 30, 50

   Device, Exastro OASE, "http(s) [80,443/tcp]", Accessing the Exastro OASE Web console
   Exastro OASE, RDB(MariaDB), "3306/tcp", DB communication
   Exastro OASE, RabbitMQ, "5672/tcp", Sending and recieving event messages
   Exastro OASE, RHDM or Drools, "http [8080/tcp]", Managing the Decision table container 
 
.. note:: Input all required items. The values are based on OASE's external services, so make sure to change the values to fit the environment.

Software requirements
================

| The Exastro OASE system is running on a Linux server and can be accessed from Client PCs through a web browser.
| The following are the software requirements for the Server.

+------------------+------------------+-----------+
| OS               | CentOS           | 7.5.1804  |
+                  +------------------+-----------+
|                  | RHEL             | 7.8 , 8.3 |
+------------------+------------------+-----------+
| web server       | Apache           | 2.4.6-97  |
+------------------+------------------+-----------+
| Framework        | Django           | 2.1.3     |
+------------------+------------------+-----------+
| Database         | MariaDB          | 10.5.8-1  |
+------------------+------------------+-----------+
| 言語             | python           | 3.6.5     |
+                  +------------------+-----------+
|                  | OpenJDK          | 1.8.0_212 |
+------------------+------------------+-----------+
| python Library   | openpyxl         | 2.5.14    |
+------------------+------------------+-----------+
| Red Hat          | Decision Manager | 7.3.1     |
+                  +------------------+-----------+
|                  | JBoss EAP        | 7.2.0     |
+------------------+------------------+-----------+
| Drools           | Business Central | 7.22.0    |
+                  +------------------+-----------+
|                  | WildFly          | 14.0.1    |
+------------------+------------------+-----------+

.. note::
    Other OS have not been tested.
    The user will have to use either Red Hat Decision Manager or Drools.
    The user can choose which one when installing Exastro OASE.


System requirements for the Client
================================

| The following are the system requirements for the client side PC.

+---------------+------------------+--------------------+
| OS            | windows          | Windows7 or later  |
+---------------+------------------+--------------------+
| Software      | Excel            | MS Office 2016  or later|
+---------------+------------------+--------------------+
| Browser       | Edge             | 20 or later         |
+               +------------------+--------------------+
|               | FireFox          | 64.0 or later      |
+               +------------------+--------------------+
|               | Chrome           | 72.x or later      |
+---------------+------------------+--------------------+

