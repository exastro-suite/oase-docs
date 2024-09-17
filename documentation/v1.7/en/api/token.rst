========
Token
========

| This section explains Tokens used in Exastro OASE and how to pay them out.
| The Pay out Token page contains the following functions.
| The Token page can be accessed by going to the :menuselection:`Rule --> Pay out Token`.


Using Tokens
==============

| Tokens have the following applications.

* External API call authentication
* Sending Test requests.


Paying out new tokens
======================

| Press the :guilabel:` Pay out new token` button on top of the page.

.. figure:: /images/ja/token/token_10.png
   :scale: 30%
   :align: center

   New token payout page


| Input information into the required item fields in the settings form.

.. figure:: /images/ja/token/token_11.png
   :scale: 20%
   :align: left

   New token payout page(Input)

Token name
   | Input a name for the token.
   | The Token name can contain maximum 64 characters.

Expiration date
   | Input a expiration date for the token.
   | If nothing is input, the token will be registered with  :program:`No expiration date`.

Permission settings
   | Define permissions for the different groups.

.. warning:: If all groups have "No permission", no user will be able to use the token.

.. raw:: html

   <div style="clear:both;"></div>

| After inputting all the necessary information, press the :guilabel:` Pay out Token` button.
| The Token will be displayed on top of the page. Users can see the tokens later, so there is no need to write it down.

.. figure:: /images/ja/token/token_12.png
   :scale: 35%
   :align: center

   Token display page


Checking paid out tokens
======================

| Users can check paid out tokens from the  :menuselection:`Pay out Token` page

.. figure:: /images/ja/token/token_07.png
   :scale: 60%
   :align: center

   Token information page

| Press the :guilabel:` Display Token` button.
| Input the password of the currently logged in user.

.. figure:: /images/ja/token/token_08.png
   :scale: 30%
   :align: center

   Password input page

| Press the :guilabel:` Display Token` button, and the Token will be displayed.
| The Token re-display page structure and components are as following.

.. figure:: /images/ja/token/token_09.png
   :scale: 30%
   :align: left

   Token re-display page

.. csv-table:: Token re-display page
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   ①, Page name, Name of the currently displayed page.
   ②, Token, Value of the currently paid out token.
   ③, Copy, Saves the Token value to the user's clip board.
   ④, Close, Closes the window.


.. raw:: html

   <div style="clear:both;"></div>

Edit Token
==============

| While the token itself cannot be edited, users can edit which groups have what permissions for the Token.
| Open the :menuselection:`Token details` page and press the :guilabel:` Edit.`

.. figure:: /images/ja/token/token_13.png
   :scale: 30%
   :align: left

   Token edit page

.. csv-table:: Token edit page description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   ①, No permission, Any groups with this radio button active will not have permission to edit or display the target token.
      ②, Has permission, Any groups with this radio button active will have permission to edit and display the target token.
   ③, Save button, Saves any changes in the Token information page and closes the window.

