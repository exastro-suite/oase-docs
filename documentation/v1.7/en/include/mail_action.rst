Mail Action parameters
------------------------

+----------------+-------------------------+-------------------------------------------------------------------------------------+---------------------------------------+
| Parameter type | Parameter variable          | Parameter value                                                                        | Input example                                |
+================+=========================+=====================================================================================+=======================================+
| Driver name     | MAIL_NAME               | Mail driver name.                                                                    | MAIL_NAME=management-mail             |
+                +                         +                                                                                     +                                       +
|                |                         | Required item.                                                                      |                                       |
+----------------+-------------------------+-------------------------------------------------------------------------------------+---------------------------------------+
| Notification reciever         | MAIL_TO                 | Specify the Destination envelope "To" email address.                                    | MAIL_TO=maintener@example.com         |
+                +                         +                                                                                     +                                       +
|                |                         | Required item.                                                                      |                                       |
+                +-------------------------+-------------------------------------------------------------------------------------+---------------------------------------+
|                | MAIL_CC                 | Specify CC Mail address.                                                    | MAIL_CC=dev-team@example.com          |
+                +                         +                                                                                     +                                       +
|                |                         | Is required but can be blank.                                |                                       |
+                +-------------------------+-------------------------------------------------------------------------------------+---------------------------------------+
|                | MAIL_BCC                | Specify BCC Mail address.                                                   | MAIL_BCC=                             |
+                +                         +                                                                                     +                                       +
|                |                         | Is required but can be blank.                                |                                       |
+----------------+-------------------------+-------------------------------------------------------------------------------------+---------------------------------------+
| Template   | MAIL_TEMPLATE           | Specify the template from Action settings- Mail template                     | MAIL_TO=maintener@example.com         |
+                +                         +                                                                                     +                                       +
|                |                         | Is required but can be blank.                                |                                       |
+----------------+-------------------------+-------------------------------------------------------------------------------------+---------------------------------------+

.. note::
   | The user must either specify a MAIL_TO mail address or use a mail address in the MAIL_TEMPLATE template.

