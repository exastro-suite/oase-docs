==========
Kubernetes
==========

| The following manual explains how to implement the Docker version of Exastro OASE using Kubernetes.
| For information regarding implementing Exastro OASE on non-container environments, please see :doc:`../installer/installation_online` or :doc:`../installer/installation_offline` .


Prerequisites
========
* The user will need a Kubernetes environment.
* The user will need to use kubectl commands.
* The user will need to use git commands.


Run Container(Simplified version)
====================

| This section explains how to use the Kubernetes manifest file on GitHub using kubectl commands.
| While it is easy to deploy, since it is using hostPath, the reusability and expandability.

Create directory for persistent data
------------------------------

| Create directory to store persistent data.

.. code-block:: bash

   # Create Volume(Implemented with Worker nodes)
   mkdir -p /tmp/oase/{business-central/data,logs,mariadb/data,rabbitmq/data,share}
   chmod -R 777 /tmp/oase

Deploy
--------

| Deploy Exastro OASE on the Kubernetes cluster.

.. code-block:: bash

    kubectl apply -f https://raw.githubusercontent.com/exastro-suite/oase-container/main/kubernetes.yaml


Run Container(Customized version)
========================

| This section explains how to deploy a Kubernetes manifest on GitHub to a user's environment using `kustomize <https://kustomize.io/>`_.
| While storage and network settings can be configured to suit the environment, the user will need to configure settings such as storage in advance.

Acquire Kubernetes manifest
-----------------------------

| Acquire Kubernetes Manifest from GitHub.

.. code-block:: bash

   git clone https://github.com/exastro-suite/oase-container.git

Update settings file.
------------------

| Change the Manifest file to fit the user's environment.
| When using kustomize, deploy the :file:`kustomization.yaml` under :file:`oase-container/kubernetes/overlays`.

Applying Customized verion's Manifest file
--------------------------------------

| Use Kustomize and apply the Manifest file to the Kubernetes cluster.

.. code-block:: bash

    cd oase-container
    kubectl apply -k kubernetes/overlays


Check connection
========

.. include:: ../../include/confirm_login.rst


Environment information
========

Environment variables
--------

.. csv-table::
   :header: Setting name, Default value, Description
   :widths: 16,     25,   25

      DB_ROOT_PASSWORD, Ch@ngeMe, Specifies MariaDB root password.
      DB_HOST, mariadb, Specifies MariaDB's FQDN(IP Address) used by Exastro OASE.
      DB_PORT, 3306, Specifies MariaDB's connection port used by Exastro OASE.
      DB_DATABASE, OASE_DB, Specifies MariaDB's database name used by Exastro OASE.
      DB_USER, OASE_USER, Specifies MariaDB's user name used by Exastro OASE.
      DB_PASSWORD, Ch@ngeMe, Specifies MariaDB's user password used by Exastro OASE.
      BUSINESS_CENTRAL_ENDPOINT, central:8080, Specifies the Business Central endpoint used by Exastro OASE.
      KIE_SERVER_ENDPOINT, server:8080, Specifies KIE server endpoint and port number used by Exastro OASE.
      JBOSS_USER, admin, Specifies Business Central user name used by Exastro OASE.
      JBOSS_PASSWORD, admin, Specifies Business Central user password used by Exastro OASE.
      MQ_HOST, rabbitmq, Specifies RabbitMQ's FQDN(IP Address) used by Exastro OASE.
      MQ_USER, admin, Specifies RabbitMQ user name used by Exastro OASE.
      MQ_PASSWORD, Ch@ngeMe, Specifies RabbitMQ user password used by Exastro OASE.
      MAIL_SMTP, {}, Specifies Mail server information linked to Exastro OASE.
      INTERVAL_TIME_<ANY>, 10, Backyard type processes' interval time.
      RABBITMQ_DEFAULT_USER, admin, Configures RabbitMQ user name.
      RABBITMQ_DEFAULT_PASS, Ch@ngeMe, Configures RabbitMQ user password.
      MARIADB_ROOT_PASSWORD, Ch@ngeMe, Configures MariaDB root password.
      MARIADB_DATABASE, OASE_DB, Configures Database name.
      MARIADB_USER, OASE_USER, Configures user name connected to the Database.
      MARIADB_PASSWORD, Ch@ngeMe, Configures user password connected to the Database.
      MARIADB_ROOT_HOST, "%", Configures host to the MariaDB which can be root logged in to.
      KIE_SERVER_LOCATION, http://kie-server:8080/kie-server/services/rest/server, Specifies KIE server endpoint.
      KIE_SERVER_CONTROLLER, http://business-central:8080/business-central/rest/controller, Specifies KIE server controller endpoint.
      KIE_MAVEN_REPO, http://business-central:8080/business-central/maven2, Specifies Maven repository endpoint.

Configuration file settings
----------------------

None

