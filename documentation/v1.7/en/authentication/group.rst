========
Group
========

| This section explains the Group management function.
| The Group management function provides the following functions.

* Registration, deletion and updating group information.
* Editing of permissions (No permission/Can see/Can edit)

Default groups
============

| Both the groups **System administrator** and **SSO default group** are registered as default groups from installation.
| These groups have different permissions than other groups and users.

System administrator
  | Useres with this role have access to everything in Exastro OASE.
  | The **System administrator**  group cannot be deleted or have their  **Group name** changed.
  | The **Access permission**  and  **Overview** can be edited.

SSO Default group
  | This groups does not have any control permission in Exastro OASE by default. Permissions can be added later if required.
  | The **System administrator**  group cannot be deleted or have their  **Group name** changed.
  | The **Access permission**  and  **Overview** can be edited.


Group management
==============

| Group management(Adding new, editing, or deletion of groups) can be done from the  :menuselection:`System --> Group` menu.
| Clicking the :guilabel:` Edit` button in the :menuselection:`Group` page allows users to enter Edit mode.
| If you want to add a new group,press the :guilabel:` Add new` button. If you want to delete or update an existing group, press the :menuselection:`Update` button and then either :program:`Update` or :program:`Delete` button.


.. tip:: 
   | The logged in user must have "Edit" permission for the groups they want to edit.
   | In the default state, only the System admin can use this function.

.. figure:: /images/ja/group/group_17.png
   :width: 900px
   :align: center

   Group edit page

.. csv-table:: Group edit function description
   :header: Item, Description
   :widths: 20, 60

   Update, Press either the :program:`Update` or :program:`Delete` button for the desired group.
   Group name, Enter a name for the group.
   Description, Text box where users can use freely to write descriptions.
   Last updated by, Displays the last user who pressed the :guilabel:` Save` button in the Group screen.
   Last updated, Displays the last time the :guilabel:` Save` button was pressed.
   ,Delete button, Pressing the :guilabel:`` button deletes the newly added row. The delete button :guilabel:`` is only displayed after "Add new" button is pressed.


.. danger::
   | If a user is only registered to one group and said group is deleted, the user will be deleted together with the group.
   | This will not happen if the user belongs to multiple groups.

| Confirm the contents and press the :guilabel:` Save` button in order to save the settings.


Access permission confirmation
================

| All the groups registered to OASE as well as their access permissions are displayed.

.. figure:: /images/ja/group/group_20.png
   :scale: 40%
   :align: center

   Access permission page

.. note::
   | The Cancel and Edit button are only displayed if the user has "Can edit" permissions for the Group page, regardless of the AD(Active Directory) link settings. 


Edit Access permission
================

| Users can add and edit group permissions for the different pages.
| This page is only displayed if the group has "Can edit" permissions.

.. figure:: /images/ja/group/group_22.png
   :scale: 40%
   :align: left

   Access permission edit page

.. csv-table:: Access permission edit function description
   :header: Permission, Description
   :widths: 20, 60

   No permission, The group is not be able to view the page.
   Can see, The group is able to view the contents of the page and can edit parts of the contents.
   Can edit, The group is able to edit contents within Exastro OASE and perform actions such as "Add new", "Update", and "Delete".

.. raw:: html

   <div style="clear:both;"></div>