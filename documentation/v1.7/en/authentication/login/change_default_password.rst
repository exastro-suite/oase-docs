====================
Change default password
====================

| This section explains how to change the default password after the initial login to Exastro OASE.
| The login screen contains the following functions.

Initial login
============

| After accessing the Exastro OASE Screen, fill in the following items.

.. figure:: /images/ja/quickstart/login_form.png
   :scale: 30%
   :align: left
   :alt: "Password input form"

   Password input form

.. csv-table:: Initial login input contents
   :header: Item, Input value, Description
   :widths: 15, 15, 30

   Login ID, :kbd:`administrator`, Input the Login ID for the system administrator.
   Password, :kbd:`oaseoaseoase`, Input the Login password for the system administrator.

.. raw:: html

   <div style="clear:both;"></div>

| Click the  :guilabel:` Login` button.


.. _change-pw:

Change initial password.
==================

| After loging in to Exastro OASE for the first time, the user will be asked to change the password.
| Input both the current password and the new password.

.. figure:: /images/ja/quickstart/init_password01.png
   :scale: 30%
   :align: left
   :alt: "Change password form"

   Change password form

.. csv-table:: Change password input contents
   :header: Item, Input value, Description
   :widths: 15, 15, 30

   Current password, :kbd:`oaseoaseoase`, Input the initial password for the System administrator.
   Current password, New password, Input a new password that follows the password constraints.
   Re-input new password, New password, Re-input the new password.


.. note:: | All passwords must follow the following constraints.
          | ・Between 8 and 64 characters.
          | ・Must contain a capitalized letter, uncapitalized letter, a number and a special symbol.

.. raw:: html

   <div style="clear:both;"></div>

|  Press the :guilabel:` Change` button.

.. figure:: /images/ja/quickstart/init_password02.png
   :scale: 30%
   :align: left
   :alt: "Change password confirmation dialog box"

   Change password confirmation dialog box

.. raw:: html

   <div style="clear:both;"></div>

| Press the :guilabel:`OK` in order to change the password. The user will then be logged out.


Loging in after changing the initial password
============================

Use the new password set in the :ref:`Change initial password <change-pw>` section and log in to Exastro OASE.

.. figure:: /images/ja/login/main02.png
   :scale: 30%
   :align: left
   :alt: "Login page"

   Login page

.. csv-table:: Login input contents
   :header: Item, Input value, Description
   :widths: 2, 15, 15, 30

   ①, Login ID, administrator, Input the Login ID for the System administrator.
   ②, Password, Input the new password set in the :ref:`Change initial password <change-pw>` section.

.. raw:: html

   <div style="clear:both;"></div>

| Click the :guilabel:` Login` button. If logged in successfuly, the page displayed in the picture below should be displayed.

.. figure:: /images/ja/dashboard/dashboard_no_data.png
   :width: 80%
   :align: center

   First-time login Dashboard.
.. raw:: html

   <div style="clear:both;"></div>
