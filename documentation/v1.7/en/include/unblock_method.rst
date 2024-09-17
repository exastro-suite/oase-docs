
| Use the Django framework settings to temporarily deactivate the IP Block function and add the IP Address to the white list.

.. warning::
   | Doing this will allow blocked IPs to access Exastro OASE during the period the block function is deactivated.

| Follow the steps below to edit the Django framework settings file to deactivate the IP Block function.

| Django framework settings file: :file:`<OASE_DIRECTORY>/OASE/oase-root/confs/frameworkconfs/settings.py`

.. tip::
   | The :file:`<OASE_DIRECTORY>` is the Install directory of Exastro OASE specified during installation.
   | The default is :file:`/exastro/OASE/oase-root/confs/frameworkconfs/settings.py`.

.. code-block:: python

   # Deactivate IP Block function
   # DISABLE_WHITE_BLACK_LIST = Flase
   DISABLE_WHITE_BLACK_LIST = True


| Re-start Apache in order for the settings to take effect.

.. code-block:: bash

   systemctl restart httpd

| Follow the White list manual :ref:`whitelist_manual` and add the accessing IP Address to the white list.

| Edit the settings file to re-activate the IP Block function.

.. code-block:: python

   # Activate IP Block function
   DISABLE_WHITE_BLACK_LIST = False

| Re-start Apache in order for the settings to take effect.

.. code-block:: bash

   systemctl restart httpd
