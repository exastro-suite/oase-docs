=======================
Single Sign On(SSO)
=======================

| This section explains the :term:`Single Sign On` (Hereinafter written as "SSO") function, how to configure it and how it is used to log in to Exastro OASE.
| The SSO Settings screen contains the following functions.

* Register, edit and delete SSO Settings information


SSO settings Screen configuration
============

The SSO settings screen configuration is as following.

.. figure:: /images/ja/sso_info/sso_info_01.png
   :scale: 60%
   :align: center

   Figure 2.1-1 Screen configuration


The SSO Setting screen structure components and their functions are as following.

.. csv-table:: Table 2.1-1 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Add new button, Opens up a page where users can register new SSO information.
   3, List, Displays the currently registered SSO settings information.


The following screen will be displayed if there are no SSO settings information registered.

.. figure:: /images/ja/sso_info/sso_info_02.png
   :scale: 60%
   :align: center

   Figure 2.1-2 Page structure


The "Add new (SSO basic information)" page structure are as following.

.. figure:: /images/ja/sso_info/sso_info_03.png
   :scale: 40%
   :align: left

   Figure 2.1-3 Page structure


The "Add new (SSO basic information)" tab's structure components and their functions are as following.

.. csv-table:: Table 2.1-3 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Close button, closes the window and returns the user to the SSO settings page.
   3, Operation tab name, Name of the current tab.
   4, Provider name, Input a Provider name
   5, Authentication method, Select an Authentication method (Pulldown).
   6, Logo, Press "Select file" and select the image file for the Logo.
   7, Display flag, Select Display flag (Pulldown).
   8, SSO attribute information settings button, Moves the user to the SSO attribute information settings tab (Any input information is saved).

.. raw:: html

   <div style="clear:both;"></div>



The "Add new(SSO Attribute tab)" page structure as as following.

.. figure:: /images/ja/sso_info/sso_info_04.png
   :scale: 40%
   :align: left

   Figure 2.1-4 Page structure


The "Add new (SSO attribute information)" tab's structure components and their functions are as following.

.. csv-table:: Table 2.1-4 Function Description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Close button, closes the window and returns the user to the SSO settings page.
   3, Operation tab name, Name of the current tab.
   4, clientId, Allows users to input an Authentication client identifier.
   5, clientSecret, Allows users to input an Authentication client secret.
   6, authorizationUri, Allows users to input an User authentication end point.
   7, accessTokenUri, Allows users to input an endpoint for acquiring accessTokens.
   8, resourceOwnerUri, Allows users to input an endpoint for acquiring user information.
   9, scope, Allows users to input the scope of user information displayed.
   10, id, Allows users to input the User ID key name.
   11, name, Allows user to input the User name key name.
   12, email, Allows the user to input an User mail address key name.
   13, imageUrl, Allows users to input an user picture URL key name.
   14, proxy, Allows users to input a Proxy.
   15, Cancel button,Closes the window and returns the user to the SSO settings page.
   16, Save button, Saves the input information and returns the user to the SSO settings page.

.. raw:: html

   <div style="clear:both;"></div>


The Provider information(SSO basic information) page structure is as following.

.. figure:: /images/ja/sso_info/sso_info_05.png
   :scale: 40%
   :align: left

   Figure 2.1-5 Page structure


The Provider information(SSO basic information) tab's structure components and their functions are as following.

.. csv-table:: Table 2.1-5  Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Close button, closes the window and returns the user to the SSO settings page.
   3, Operation tab name, Name of the current tab.
   4, Provider name, Displays the Provider name selected in the SSO settings page.
   5, Authentication method, Displays the SSO information's authentication method selected in the SSO settings page.
   6, Logo, Displays the SSO information's logo file name selected in the SSO settings page.
   7, Display flag, Displays the SSO information's display flag selected in the SSO settings page.
   8, Delete button, Deletes the selected SSO information and closes the Provider information window.
   9, Edit button, Allows the user to edit the selected SSO information.

.. raw:: html

   <div style="clear:both;"></div>

The Provider information(SSO attribute information) page structure is as following.

.. figure:: /images/ja/sso_info/sso_info_06.png
   :scale: 40%
   :align: left

   Figure 2.1-6 Page structure


The Provider information (SSO attribute information) tab's structure components and their functions are as following

.. csv-table:: Table 2.1-6 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Close button, closes the window and returns the user to the SSO settings page.
   3, Operation tab name, Name of the current tab.
   4, clientId, Displays the SSO information's authentication client identifier selected in the SSO settings page.
   5, clientSecret, Displays the Authentication client secret selected in the SSO settings page.
   6, authorizationUri, Displays the SSO information's end point for user authentication selected in the SSO settings page.
   7, accessTokenUri, Displays the SSO information's endpoint for acquiring accessTokens selected in the SSO settings page.
   8, resourceOwnerUri, Displays the SSO information's endpoint for acquiring User information selected in the SSO settings page.
   9, scope, Displays the SSO information's user information display scope selected in the SSO settings page.
   10, id, Displays the SSO information's user ID key name selected in the SSO settings page.
   11, name, Displays the SSO information's user name key name selected in the SSO settings page.
   12, email, Displays the SSO information's user mail address key name selected in the SSO settings page.
   13, imageUrl,  Displays the SSO information's User picture URL key name selected in the SSO settings page.
   14, proxy, Displays the SSO information's proxy selected in the SSO settings page.
   8, Delete button, Deletes the selected SSO information and closes the Provider information window.
   9, Edit button, Allows the user to edit the selected SSO information.

.. raw:: html

   <div style="clear:both;"></div>



The Edit Provider(SSO Basic information) tab constructure is as following.

.. figure:: /images/ja/sso_info/sso_info_07.png
   :scale: 40%
   :align: left

   Figure 2.1-7 Tab structure


Edit provider(SSO Basic information) tab structure components and their functions are as following.

.. csv-table:: Table 2.1-7 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Close button, closes the window and returns the user to the SSO settings page.
   3, Operation tab name, Name of the current tab.
   4, Provider name, displays the SSO Information's Provider name selected in the SSO Settings page. Can be edited.
   5, Authentication method, Displays the SSO information's authentication method selected in the SSO settings page. Can be edited.
   6, Logo, Displays the SSO information's logo selected in the SSO settings page. Can be edited.
   7, Display flag, Displays the SSO information's display flag selected in the SSO settings page. Can be edited.
   8, SSO Attribute information settings button, Saves the input content and moves the user to the SSO attribute information tab.

.. raw:: html

   <div style="clear:both;"></div>


The Edit provider(SSO Attribute information) tab and it's structure is as following.

.. figure:: /images/ja/sso_info/sso_info_08.png
   :scale: 40%
   :align: left

   Figure 2.1-8 Tab structure


The Edit provider(SSO Attribute information) tab structure components and their functions are as following.

.. csv-table:: Table 2.1-8 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Operation page name, Displays the name of the current page.
   2, Close button, closes the window and returns the user to the SSO settings page.
   3, Operation tab name, Name of the current tab.
   4, clientId, Displays the SSO information's authentication client identifier selected in the SSO settings page. Can be edited.
   5, clientSecret, Displays the Authentication client secret selected in the SSO settings page. Can be edited.
   6, authorizationUri, Displays the SSO information's end point for user authentication selected in the SSO settings page. Can be edited.
   7, accessTokenUri, Displays the SSO information's endpoint for acquiring accessTokens selected in the SSO settings page. Can be edited.
   8, resourceOwnerUri, Displays the SSO information's endpoint for acquiring User information selected in the SSO settings page. Can be edited.
   9, scope, Displays the SSO information's user information display scope selected in the SSO settings page. Can be edited.
   10, id, Displays the SSO information's user ID key name selected in the SSO settings page. Can be edited.
   11, name, Displays the SSO information's user name key name selected in the SSO settings page. Can be edited.
   12, email, Displays the SSO information's user mail address key name selected in the SSO settings page. Can be edited.
   13, imageUrl,  Displays the SSO information's User picture URL key name selected in the SSO settings page. Can be edited.
   14, proxy, Displays the SSO information's proxy selected in the SSO settings page. Can be edited.
   15, Cancel button,Closes the window and returns the user to the SSO settings page.
   16, Save button, Saves the input information and returns the user to the SSO settings page.

.. raw:: html

   <div style="clear:both;"></div>


SSO settings page
=====================

This section explains how to operate the SSO settings page.

(1)SSO settings page
--------------
| This page displays all registered SSO information.
| The "Add new" button is displayed depending on the user's access permissions.

Display more information button
^^^^^^^^^^^^^^

Displays more information regarding the the selected Provider name.

.. figure:: /images/ja/sso_info/sso_info_09.png
   :scale: 60%
   :align: center

   Figure 2.2-1-1 When The :program:`GitHub`  "Display more information" button is pressed.

List
^^^^
.. figure:: /images/ja/sso_info/sso_info_10.png
   :scale: 60%
   :align: center

   Figure 2.2-1-2 SSO settings page items


.. csv-table:: Table 2.2-1-2 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Provider name, Displays the Proider name.
   2, Last updated by, Displays the user who last updated the SSO settings information.
   3, Last updated time, Displays the last time the SSO settings information was udpated.

.. note::
   | The "Add new" button will not be displayed unless the user has :program:`Can edit` permissions for the SSO settings page.


(2) Add new page(SSO Basic information)
----------------------------
The "Add new" page is not be displayed unless the user has :program:`Can edit` permissions for the SSO settings page.

Input fields
^^^^^^

.. figure:: /images/ja/sso_info/sso_info_11.png
   :scale: 40%
   :align: left

   Figure 2.2-2-1 Add new page(SSO Basic information)


.. csv-table:: Table 2.2-2-1 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Close button, Closes the "Add new" page and returns the user to the SSO settings page.
   2, Provider name, Required input field.。Can cotnain maximum 128 characters.
   3, Authentication method, Required input field.。Select an Authentication method from the pulldown selection.
   4, Logo, Optional input field.The file name of the upload file can contain maximum 64 characters.
   5, Display flag, Required input field. Select from the pulldown selection.
   6, SSO Attribute information settings button, Saves the input information and moves the user to the SSP Attribute information tab.

.. raw:: html

   <div style="clear:both;"></div>


(3)Add new page(SSO Attribute information)
-------------------------------
The "Add new" page is not be displayed unless the user has :program:`Can edit` permissions for the SSO settings page.

Input fields
^^^^^^

.. figure:: /images/ja/sso_info/sso_info_12.png
   :scale: 40%
   :align: left

   Figure 2.2-3-1 Add new page(SSO Attribute information)


.. csv-table:: Table 2.2-3-1 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Close button, Closes the current page and returns the user to the SSO settings page.
   2, clientId, Required input field. Can contain maximum 256 characters.
   3, clientSecret, Required input field.。Can contain maximum 256 characters.
   4, authorizationUri, Required input field.。Can contain maximum 256 characters.
   5, accessTokenUri, Required input field.。Can contain maximum 256 characters.
   6, resourceOwnerUri, Required input field.。Can contain maximum 256 characters.
   7, scope, Optional input field.Can contain maximum 256 characters.
   8, id, Required input field.Can contain maximum 256 characters.
   9, name, Required input field.Can contain maximum 256 characters.
   10, email, Optional input field. Can contain maximum 256 characters.
   11, imageUrl, Optional input field.Can contain maximum 256 characters.
   12, proxy, Optional input field.Can contain maximum 256 characters.
   13, Cancel button, Closes the page and returns the user to the SSO settings page.
   14, Save button, Saves the contents and returns the user to the SSO settings page.

.. raw:: html

   <div style="clear:both;"></div>



(4)Provider information screen
-----------------------
The "Edit/Delete" button is not displayed unless the user has :program:`Can edit` permissions for the SSO settings page.

.. figure:: /images/ja/sso_info/sso_info_14.png
   :scale: 40%
   :align: left

   Figure 2.2-4-1 Provider information page


.. csv-table:: Table 2.2-4-1 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Close button, Closes the Provider information page and returns the user to the SSO settings page.
   2, Delete button, Deletes the selected SSO information and returns the user to the SSO settings page.
   3, Edit button, Allows users to edit the selected SSO information.

.. raw:: html

   <div style="clear:both;"></div>


(5)Edit provider(SSO Basic information) page
------------------------------------

.. figure:: /images/ja/sso_info/sso_info_13.png
   :scale: 40%
   :align: left

   Figure 2.2-5-1 Edit provider(SSO Basic information) page


.. csv-table:: Table 2.2-5-1 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Close button, Deletes all edited contents and returns the user to the SSO settings screen.
   2, Provider name, Displays the SSO information's provider name selected in the SSO settings. Can be edited.Required input field. Can contain maximum 128 characters.
   3, Authentication name, Displays the SSO information's Authentication method selected in the SSO settings. Can be edited.Required input field. Select from Pulldown.
   4, Logo, Displays the SSO information's Logo selected in the SSO settings. Optional input field. The file name of the upload file can contain maximum 64 characters.
   5, Display flag, Displays the SSO information's Display flag selected in the SSO settings. Can be edited. Required input field. Select from Pulldown.
   6, SSO Attribute information settings button, Saves the input information and moves the user to the SSP Attribute information tab.

.. raw:: html

   <div style="clear:both;"></div>


(6)Edit provider(SSO Attribute information) page
------------------------------------

.. figure:: /images/ja/sso_info/sso_info_15.png
   :scale: 40%
   :align: left

   Figure 2.2-6-1 Edit provider(SSO Attribute information) page


.. csv-table:: Table 2.2-6-1 Function description
   :header: No., Structure component, Description
   :widths: 5, 20, 60

   1, Close button, Deletes all edited contents and returns the user to the SSO settings screen.
   2, clientId, Displays the SSO information's authentication client identifier selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   3, clientSecret, Displays the SSO information's Authentication client secret selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   4, authorizationUri, Displays the SSO information's user authentication endpoint selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   5, accessTokenUri, Displays the SSO information's Endpoint for acquiring accessToken selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   6, resourceOwnerUri, Displays the SSO information's endpoint for acquiring user information selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   7, scope, Displays the SSO information's user information display scope selected in the SSO settings. Can be edited. Optional input field.Can contain maximum 256 characters.
   8, id, Displays the SSO information's user ID key name selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   9, name, Displays the SSO information's user name key name selected in the SSO settings. Can be edited. Required input field.。Can contain maximum 256 characters.
   10, email, Displays the SSO information's user mail address key name selected in the SSO settings. Can be edited. Optional input field.Can contain maximum 256 characters.
   11, imageUrl, Displays the SSO information's User picture URL key name selected in the SSO settings. Can be edited. Optional input field.Can contain maximum 256 characters.
   12, proxy, Displays the SSO information's Proxy selected in the SSO settings. Can be edited. Optional input field.Can contain maximum 256 characters.
   13, Cancel button, Discards all edited contents and returns the user to the SSO settings page.
   14, Save button, Saves all edited contents and returns the user to the SSO settings page. The Save button is not displayed if there are no changes.

.. raw:: html

   <div style="clear:both;"></div>

