======
Users
======

| This section explains the User management function and how to use it.


User list
================

| All registered users can be seen by going to the :menuselection:`System --> User` menu and then the :menuselection:`User` page.

.. figure:: /images/ja/user/disp_index.png
   :scale: 60%
   :align: center

   User list


.. csv-table:: User list item list
   :header: Item, Description
   :widths: 20, 60

   User name, Displays the User's User name.
   Login ID, Displays the User's Login ID.
   Mail address, Displays the User's mail address.
   Group, Displays the Group(s) the user belongs to. If the user belongs to more than 6 groups, the rest of the groups will be shortened.
   Last updated by, Displays the last user who pressed the :guilabel:` Save` button in the Group screen.
   Last updated, Displays the last time the :guilabel:` Save` button was pressed.

.. note::
   | The Edit button will not be displayed when linked to AD. It is also not displayed if the user does not have "Can edit" permissions for the User page.


User management
============

| This section explains the process of adding new users and editing/deleting already registered users.
| Press the :guilabel:` edit` button on the upper left corner in the :menuselection:`user` page.

.. tip:: 
   | In order to use the User management function, the operating user must have "Can edit" permission for the User page.

.. figure:: /images/ja/user/disp_editbutton.png
   :scale: 60%
   :align: center

   User list page

| To add new users, press the :guilabel:` add` button and fill in the required input fields.
| To edit existing users, press the :menuselection:`Edit` item and select :program:`Edit` from the pulldown selection.
| To delete existing users, press the :menuselection:`Edit` item and select :program:`Delete` from the pulldown selection.

.. figure:: /images/ja/user/edit_index.png
   :scale: 60%
   :align: center

   Edit User page

.. csv-table:: Edit user items
   :header: Item, Description
   :widths: 18, 60

   Edit, Allows users to edit and delete existing users. Select either "Edit" or "Delete" from the pulldown selection.
   User name, Input a user name.
   Login ID, Input a login ID. The login ID can contain all alphabetic characters as well as some special characters(.@_-).
   Mail address, input a mail address. Can contain maximum 256 characters.
   Group, Select which group(s) the user will belong to. If more than 6 groups are added, the groups will be shortened and a "Group" button will appear.
   Last updated by, Displays the last user who pressed the :guilabel:` Save` button in the Group screen.
   Last updated, Displays the last time the :guilabel:` Save` button was pressed.
   Delete button, Pressing the :guilabel:`` button deletes the newly added row. The delete button :guilabel:`` is only displayed after "Add new" button is pressed.

| If the user wants to edit the relationship between the groups and the users, Press the :guilabel:`` button in the :menuselection:`Group` item.
| The user can then select which groups they want to link with from the :menuselection:`Select group` page. Press the :guilabel:` Save` button to save any changes.

.. figure:: /images/ja/user/edit_group.png
   :scale: 100%
   :align: center

   Select Group page

.. note::
   | If a user belongs to multiple groups, The strongest permissions will be displayed.

| After inputting all the required information, press the :guilabel:` Save` button.