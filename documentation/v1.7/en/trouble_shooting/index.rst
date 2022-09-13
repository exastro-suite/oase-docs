============================
Trouble shooting guide.
============================

| This section serves as a trouble guide for problems the user might meet whiel using Exastro OASE.


The message "403 Fordidden" is displayed and the contents is not displayed.
=======================================================

Situation
----

| When opening a page/menu within Exastro OASE, the message "You dont have permission to view this page" is displayed.

.. figure:: /images/ja/common/common_02.png
   :scale: 60%
   :align: center
   
   "403 Fordidden" page

Cause and solution
--------------

| The most probable reason for this problem is that the permission the set to the group the user belongs to is "No permission".
| Changing the access permission the group has the corresponding page to either "Can view" or "Can edit" fixes this problem.


The message "404 Fordidden" is displayed and the contents is not displayed.
=======================================================

Situation
----

| When opening a page/menu within Exastro OASE, the message "Could not find the requested URL on this server".

.. figure:: /images/ja/common/common_16.png
   :scale: 60%
   :align: center
   
   "404 Not Found" page


Cause and solution
--------------

| Check that the the URL is correct or that the page has not been moved or deleted. This message is only displayed when the URL is invalid.


I cant access the OASE Login page anymore.
============================================

.. include:: ../include/unblock_method.rst