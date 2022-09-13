========
Environment settings
========

Log file output destination
====================

If the date has changed or the file size exceeds 10MB, the log will be rotated.

.. csv-table:: Log file
   :header: Process name, Path, Storage period(Default), Can/cannot be changed from UI
   :widths: 30, 80, 30, 15

   Web App, :file:`{<oase_directory>}/OASE/oase-root/logs/webaplogs/webap.log`, 14 days, Cannot be changed
   Agent process, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_agent/oase_agent.log`,  7 days, Can be changed
   Action process, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_action/oase_action.log`, 7 days, Can be changed
   Apply process, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_apply/oase_apply.log`, 7 days, Can be changed
   Accept process, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_accept/oase_accept.log`, 7 days, Can be changed
   Active Directory link, :file:`{<oase_directory>}/OASE/oase-root/logs/ad_collaboration/ad_collaboration.log`, 7 days, Can be changed
   Monitor application link, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/oase_monitoring/oase_monitoring.log`, 7 days ※Common adapter settings, Can be changed
   ITA link driver, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/exastro_collaboration/exastro_collaboration.log`,14 days, Cannot be changed
   ServiceNow link driver, :file:`{<oase_directory>}/OASE/oase-root/logs/backyardlogs/servicenow_notification/servicenow_notification.log`,14 days, Cannot be changed


Stateful data storage location
============================

.. csv-table:: Stateful data storage location
   :header: Stateful data, Path, Default
   :widths: 40, 50, 40

   Decision table file deployment destination1, :file:`{<rulefile_rootpath>}` ※Specified during installation, :file:`/exastro/rule`
   Decision table file deployment destination2, :file:`{<oase_directory>}/OASE/oase-root/temp/rule`, :file:`/exastro/OASE/oase-root/temp/rule`
   Session file, :file:`{<oase_directory>}/OASE/oase-root/temp/sessions`, :file:`/exastro/OASE/oase-root/temp/sessions`
   JBoss project, :file:`{<jboss_root_directory>}` ※Specified during installation, :file:`/exastro/JBoss`
   M2 repository, :file:`/root/.m2/repository/com/oase`, :file:`/root/.m2/repository/com/oase`
   MariaDB, :file:`/var/lib/mysql`, :file:`/var/lib/mysql`
   RabbitMQ, :file:`/var/lib/rabbitmq`, :file:`/var/lib/rabbitmq`

.. note::
   |The following are specified during installation: :file:`{<oase_directory>}`, :file:`{<rulefile_rootpath>}`, :file:`{<jboss_root_directory>}` 