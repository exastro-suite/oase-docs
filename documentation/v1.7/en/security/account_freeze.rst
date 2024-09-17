==============
Freezed accounts
==============

| The Account freezing function restricts users from unlocking the accounts themselves/
| Users who had their accounts freezed can have them unfrozen by the System administrator or the :program:`Mail notification destination login ID` user


Account freeze settings
====================

| For settings regarding locking accounts, see the following items in :doc:`../system/password`.
Incorrect password threshold
| Locks any users who input incorrect passwords more times than the set threshold.
  
Account lock period
| How long before the account lock is released.

Account lock limit
| Freezes any accounts who are locked more times than the set limit. The user is then registered to the Account lock user list.

| E.g. If the Incorrect password threshold is set to 5 and the Account lock limit is set to 3, the account will be freezed if the user inputs an incorrect password 15 times in a row.



Un-freezing accounts
================================

| Users with freezed accounts cannot un-freeze them by themselves.
| Accounts and only be un-freezed by users who has permission to edit the Account lock user page.

.. tip::
   | The Menu button in the Menu bar that moves users to to the Account lock user is not displayed when connected to AD.

Pre-requisites
--------

| The following requirements must be met in order to release a locked account.

* The user must be either System administrator or the Mail notification destination login ID user

.. tip::
   | For information regarding the Mail notification destination login ID, see the :program:`Mail notification destination login ID`  section in the :doc:`../system/password` document.

Procedure
--------

| Go to the :menuselection:`System --> Account lock user` menu.
| All locked accounts are displayed in this page.

.. figure:: /images/ja/locked_user/locked_user_02.png
   :scale: 60%
   :align: center
   
   Account lock user page
   
| Press the "Release button" :guilabel:`` to release the account.
