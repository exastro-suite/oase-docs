==============
Approving Actions
==============

| Exastro OASE comes with a function that asks the user for approval before automatically running any actions.
| This section will explain how to use said functiosn and how to write :menuselection:`Apprival mail parameters`.

Send Approval requests.
==================

| This section explains the approval mail parameters used when sending approval mails.
| The parameters are more or less the same as the action parameters for the Mail link.

.. note::
   | The user will need to input the approval parameter information in the same row as the action they want to apply the approval request to.

.. include:: ../include/mail_action.rst



Usecases
------------

| **Case 1**
| Sends a mail to specified users asking for approval.

::

 MAIL_NAME=management-mail,MAIL_TO=maintener@example.com,MAIL_CC=dev-team@example.com,MAIL_BCC=

| **Case 2**
| Uses a mail template to send a mail to specified users asking for approval.

::

 MAIL_NAME=management-mail,MAIL_TO=,MAIL_CC=dev-team@example.com,MAIL_BCC=,MAIL_TEMPLATE=request_approval


Approving operations
========

| Operations can be approved by going to the :menuselection:`Rule --> Action history` menu and opening the :menuselection:`Action history` page.

.. include:: ../include/approval_dialog.rst