======
Docker
======

| The following manual explains how to implement the Docker version of Exastro OASE.
| The Docker version is currently used for verification and can easily be implemented. 
| Note that this version does not support Data persistence or redundant configurations. If needed, we recommend using :doc:`installation_docker_compose` or :doc:`installation_kubernetes` environments.
| The Docker version of OASE allows users to use OASE right after running the container.
| For information regarding implementing Exastro OASE on non-container environments, please see :doc:`../installer/installation_online` or :doc:`../installer/installation_offline` .


Prerequisites
========
The user will need a Docker environment.


Start Container
============

Container
------------

| Use Docker commands to start the OASE Container.

.. code-block:: bash

   docker run --privileged --hostname="exastro-oase" -d exastro/oase -p <port>:80 -p <port>:443

.. warning::
   | The options :kbd:`--privileged` and :kbd:`--hostname="exastro-oase"` are required.
   | Make sure to change the ports to fit your environment.

docker-compose
--------------

| Use docker-compose to start the OASE Container
| Create a :file:`docker-compose.yml` file with the contents below.

.. code-block:: yaml
   :caption: docker-compose.yaml

   version: "3"
   services:
      oase:
         container_name: exastro-oase
         hostname: exastro-oase
         privileged: true
         restart: always
         tty: true
         image: exastro/oase:latest
         ports:
            - "<http_port>:80"
            - "<https_port>:443"

| Start Container.

.. code-block:: bash

   docker-compose up -d oase

.. warning::
   | The options :program:`privileged: true` and :program:`hostname: exastro-oase` are required.
   | Make sure to change the ports to fit your environment.


Check connection
========

.. include:: ../../include/confirm_login.rst


Environment information
========

Environment variables
--------

.. csv-table::
   :header: Setting name, Setting value, Description
   :widths: 16,     25,   25

   OASE_ROOT_DIR, :file:`{<oase_directory>}/OASE/oase-root`,
   PYTHON_MODULE, :file:`/usr/bin/python3`,
   PYTHONPATH,    :file:`$OASE_ROOT_DIR`,
   JAVA_HOME,     :file:`/usr/lib/jvm/java-1.8.0-openjdk`,
   PATH,          :file:`/opt/apache-maven/bin:$JAVA_HOME/bin:/usr/bin`,
   CLASSPATH,     :file:`$JAVA_HOME/jre/lib:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar`,
   M2_HOME,       :file:`/opt/apache-maven-3.6.1`,
   JBOSS_HOME,    :file:`{<jboss_root_directory>}`,

Configuration file settings
----------------------

None

