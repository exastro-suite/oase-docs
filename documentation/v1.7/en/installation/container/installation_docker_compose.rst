==============
Docker Compose
==============

| The following manual explains how to implement the Docker version of Exastro OASE using Docker Compose.
| This version does not support redundant configurations. If needed, we recommend using a :doc:`installation_kubernetes` environment.
| For information regarding implementing Exastro OASE on non-container environments, please see :doc:`../installer/installation_online` or :doc:`../installer/installation_offline` .


Prerequisites
========
* The user will need a Docker environment.
* The user will need Docker Compose.
* The user will need to use git commands.

Run Container
============

Acquire files
----------

| Use the following Git command to acquire the required files for Docker Compose.

.. code-block:: bash

   git clone https://github.com/exastro-suite/oase-container.git

Start Docker Compose container
-----------------------------------

| Use docker-compose to run the Exastro OASE container in it's smallest configuration.

.. warning:: 
   | The containers used to link the monitoring application are not started when running the smallest Exastro OASE configuration.

.. code-block:: bash

    cd oase-container
    docker-compose up -d


| If the user wants to run container for the monitoring applications, specify the profile before starting them.
| The same can be done for Exastro IT Automation.

.. csv-table:: Profile list
   :header: Run container, Profile name
   :width: 40, 20

   Exastro IT Automation container, ita
   Zabbix link container, zabbix
   Prometheus link container, prometheus
   Grafana link container, grafana
   Datadog link container, datadog
   Mail link container, mail
   All containers, all

.. code-block:: bash

    cd oase-container

    # Start Exastro OASE and Exastro IT Automation container
    docker-compose --profile ita up -d

    # Start Exastro OASE and Zabbix link container
    docker-compose --profile zabbix up -d

    # Start Exastro OASE and Prometheus link container
    docker-compose --profile prometheus up -d

    # Start Exastro OASE and Grafana link container
    docker-compose --profile grafana up -d

    # Start Exastro OASE and Datadog link container
    docker-compose --profile datadog up -d

    # Start Exastro OASE and mail link container
    docker-compose --profile mail up -d

    # Start Exastro OASE and Exastro IT Automation container and Monitoring application link container
    docker-compose --profile all up -d

    # Start Exastro OASE and Exastro IT Automation container and Monitoring application link container
    docker-compose --profile ita --profile zabbix up -d

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

