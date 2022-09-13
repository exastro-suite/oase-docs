========
Login
========

| The following section explains the process of logging into Exastro OASE for the first time and changing the default password.
| The login screen provides functions required to operate OASE.

First time login
============

| When accessing OASE, the user will be asked to input the following items.

.. figure:: /images/ja/quickstart/login_form.png
   :scale: 30%
   :align: left
   :alt: "Password form"

   Password form

.. csv-table:: Initial login input contents
   :header: Item, Value, Description
   :widths: 15, 15, 30

   Login ID, :kbd:`administrator`, Input the System admin login ID.
   Password, :kbd:`oaseoaseoase`, Input the System admin login password.

.. raw:: html

   <div style="clear:both;"></div>

| Press the  :guilabel:` Login` button.


.. _change-pw:

Change the default password
==================

| Users logging in for the first time will be asked to change their password
| Input the current password and the new password.

.. figure:: /images/ja/quickstart/init_password01.png
   :scale: 30%
   :align: left
   :alt: "Password change form"

   Password update form

.. csv-table:: Password change input contents
   :header: Item, Value, Description
   :widths: 15, 15, 30

   Current password, :kbd:`oaseoaseoase`, Input the default password for the System administrator.
   New password, New password, Follow the password restrictions and input a new password.
   Re-input new password, New password, Re-input the new password.


.. note:: | The password must follow the following requirements.
          | ・Must contains 8~64 characters.
          | ・Must contain at least a capitalized letter, uncapitalized letter, number and a special symbol.

.. raw:: html

   <div style="clear:both;"></div>

| Press the :guilabel:` Change` button.

.. figure:: /images/ja/quickstart/init_password02.png
   :scale: 30%
   :align: left
   :alt: "Password change confirmation dialog"

   Password change confirmation dialog

.. raw:: html

   <div style="clear:both;"></div>

| Pressing the :guilabel:`OK` button changes the user's password and logs them out.


Loging in after changing password
============================

Use the password set in the :ref:`Change the default password <change-pw>` section to log in.

.. figure:: /images/ja/login/main02.png
   :scale: 30%
   :align: left
   :alt: "Login screen"

   Login screen

.. csv-table:: Login input contents
   :header: No., Item, Value, Description
   :widths: 2, 15, 15, 30

   ①, Login ID, administrator, Input the Login ID for the System administrator.
   ②, Password, Password set in the :ref:`Change the default password <change-pw>` section., Input the Login password for the System administrator.

.. raw:: html

   <div style="clear:both;"></div>

| Clicking the :guilabel:` Login` button will then move the user to the following dashboard.

.. figure:: /images/ja/dashboard/dashboard_no_data.png
   :width: 80%
   :align: center

   Initial login dashboard

.. raw:: html

   <div style="clear:both;"></div>
