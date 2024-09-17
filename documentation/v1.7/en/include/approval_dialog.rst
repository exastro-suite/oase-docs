| Users can use the Approve/Reject button :guilabel:`` in order to approve(execute action) or reject(stop action) actions waiting for approval.

.. note::
   | The user must have "Can edit" permissions for the Decision table page in order to approve or reject actions.

.. figure:: /images/ja/action_history/action_history_06.png
   :scale: 60%
   :align: center

   Approval dialog

.. csv-table:: Approve/Reject button description
   :header: 
   Button, Description
   :widths: 20, 60

   Approve/Reject, Allows users to approve or reject actions put on hold.
   Put on hold button, Returns the user to the Action history page.
   Approve button, Approves the action and executes it.
   Reject button, Rejects the action and stops it.

.. warning::
   | Rejected actions cannot be executed again.
   | If the same event information hits multiple rules, causing multiple actions to be executed, rejecting the action will also stop all later actions.
