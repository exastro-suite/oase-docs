===========
Blocked IPs
===========

| The IP Block function blocks the IP of users who has failed to log in to many times.
| Blocked IPs can not be unblocked from the same IP. The System admin or the Mail notification destination login ID user must log in from a non-blocked IP.

.. tip:: We recommend registering safe IP addresses to the White list.


IP block settings
====================

| For information regarding configuring IP blocks, see the following items in the System settings'  :doc:`../system/password` section.

Consecutive logins from same IP limit 
  | If multiple failed login attempts (exceeding the set attempt limit) are detected from the same IP address , the IP address will be added to the black list.

| E.g. If the "Consecutive logins from same IP limit" is set to 5, the user's IP address will be added to the black list after the 5th attempt.


White list
==============

| White listed IP Addresses will not be added to the black list can access Exastro OASE regardless of Consecutive failed login attempts.

| The White list page contains the following functions

* Registration, editing and deletion of white lists


Prerequisites
--------

| The following requirements must be met in order to use the White list.

* The user be either the System admin or must have a "Mail notification destination" login ID in order to use the White list.

.. tip::
   | For information regarding the Mail notification destination Login ID, see the :menuselection:`Mail notification destination Login ID` section in the "":doc:`../system/password` manual.

.. _whitelist_manual:

Procedure
--------

| Go to the :menuselection:`Management --> White list` menu.

.. figure:: /images/ja/whitelist/disp_index.png
   :scale: 60%
   :align: center

   White list page

| Click the :guilabel:` Edit` button in order to add, delete or edit an existing white list.

.. figure:: /images/ja/whitelist/edit_index.png
   :scale: 60%
   :align: center

   Edit White list page

.. table:: Edit White list function

   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Component         | Description                                                                                                                          |
   +==================+===============================================================================================================================+
   | Cancel       | Closes the White list edit page without saving the contents and returns the user to the White list page.                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Reset         | Reverts any edits.                                                                            |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Add             | Adds a row.                                                                                                     |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Save             | Saves the edited contents and returns the user to the White list page.                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Edit             | :kbd:`Edit` - Select when editing existing contents.                                                                            |
   +                  +                                                                                                                               +
   |                  | :kbd:`Deactivate` - Select when deactivating existing contents.                                                                          |
   +                  +                                                                                                                               +
   |                  | Press the :guilabel:` Save` button in order to save. ※Newly added rows will not be displayed in the pulldown menu.   |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | IP Address       | Required input field. Can use wild cards.                                                                              |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Last updated by      | Displays the name of the user who last updated the White list.                                                                    |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Register date         | Displays the registration date of the White list.                                                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Delete added rows button | The :guilabel:`` button appears when the :guilabel:`Add button` is pressed.               |
   +                  +                                                                                                                               +
   |                  | Press the :guilabel:`` button in order to delete the added row.                                                                            |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+

| Press the :guilabel:` Save` button to save the settings.

Black list
==============

| If the amount of failed login attempts comming from the same IP Address exceeds the set **Consecutive logins from same IP limit **, the IP Address will be added to the Black list and will be blocked from accessing Exastro OASE.

| The Black list page contains the following functions.

* Registration, editing and deactivation of black lists
* Black list auto-registration


Prerequisites
--------

| The following requirements must be met in order to use the Black list.

* The user be either the System admin or must have a "Mail notification destination" login ID in order to use the Black list.

.. tip::
   | For information regarding the Mail notification destination Login ID, see the :menuselection:`Mail notification destination Login ID` section in the "":doc:`../system/password` manual.

Procedure
--------

| Go to the :menuselection:`Management --> Black list` menu.

.. figure:: /images/ja/blacklist/disp_index.png
   :scale: 60%
   :align: center

   Black list

| Click the :guilabel:` Edit` button in order to add, delete or edit an existing Black list.

.. figure:: /images/ja/blacklist/edit_index.png
   :scale: 60%
   :align: center

   Edit Black list page

.. table:: Edit Black list function

   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Component         | Description                                                                                                                          |
   +==================+===============================================================================================================================+
   | Cancel       | Closes the Black list edit page without saving the contents and returns the user to the Black list page.                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Reset         | Reverts any edits.                                                                            |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Add             | Adds a row.                                                                                                     |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Save             | Saves the edited contents and returns the user to the Black list page.                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Edit             | :kbd:`Edit` - Select when editing existing contents.                                                                            |
   +                  +                                                                                                                               +
   |                  | :kbd:`Deactivate` - Select when deactivating existing contents.                                                                          |
   +                  +                                                                                                                               +
   |                  | Press the :guilabel:` Save` button in order to save. ※Newly added rows will not be displayed in the pulldown menu.   |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | IP Address       | Required input field. Can use wild cards.                                                                              |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Last updated by      | Displays the name of the user who last updated the Black list.                                                                    |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Register date         | Displays the registration date of the Black list.                                                                                |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Delete row button | The :guilabel:`` button appears when the :guilabel:`Add button` is pressed.               |
   +                  +                                                                                                                               +
   |                  | Press the :guilabel:`` button in order to delete the added row.                                                                            |
   +------------------+-------------------------------------------------------------------------------------------------------------------------------+

| Press the :guilabel:` Save` button to save the settings.


Black list and White list relationship
====================================

| If an IP Address is registered to both the Exastro OASE Black list and White list, the White list will be prioritized **White list will be prioritized**.


If the user is blocked and cannot login
===================================================

.. include:: ../include/unblock_method.rst