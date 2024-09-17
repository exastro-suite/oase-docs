===========================
Exastro OASE system structure
===========================

| Exastro OASE system structure can be selected to fit the user's requirements.
| The following describes the mail structures.

All-in one structure
==================

| The most simple structure where All of Exastro OASE's components are on the same system.
| While it is simple to cosntruct, it might be subject to SPoF(Single point of Failure), meaning that if something happens to the system, Exastro OASE might not work properly.


.. figure:: /images/ja/introduction/deploy_all_in_one.png
   :scale: 80%
   :align: center

   All-in one structure

High availability structure
========================

| A more advanced structure that allows for higher expandability and availability. The Exastro OASE components are deployed on multiple systems.
| Compared to the All-in one structure, it is more complex to construct, but it is not subject to SPoF.

.. figure:: /images/ja/introduction/deploy_high_availability.png
   :scale: 80%
   :align: center

   High availability structure