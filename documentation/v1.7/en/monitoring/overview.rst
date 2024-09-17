==============================
Monitor application link overview
==============================

| Exastro OASE uses alert messages as triggers amd matches the contents of the alert messages with the conditions written in the Condition tables before reacting.
| There are 2 different methods of recieving Alert messages, Actively and Passively. For Passively acquiring Alert messages, use the Exastro OASE :doc:`../api/api` to call messages. For Actively acquiring messages, use an Exastro OASE **監視アダプタ** to acquire messages from external monitoring applications.
| This manual explains how to acquire messages actively using a **Monitor adapter**.

.. figure:: /images/ja/introduction/oase_chain_image.png
   :scale: 60%
   :align: center

   Application link
