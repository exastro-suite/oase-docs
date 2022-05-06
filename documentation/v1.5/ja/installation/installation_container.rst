========================
インストール (コンテナ)
========================

| Docker 版 Exastro OASE の導入方法について説明します。
| Docker 版は、現時点ではデモ用となっているため、データの永続化や冗長構成には非対応です。
| Docker 版 OASE を使うことで、コンテナ起動後、すぐに OASE を利用できます。
| 本番環境における導入の場合には、:doc:`installation_online` か :doc:`installation_offline` を参照して下さい。


前提条件
========
Docker 環境が必要となります。


コンテナ起動
============

コンテナ単体
------------

| docker コマンドを利用して OASE コンテナを起動します。

.. code-block:: bash

   docker run --privileged --hostname="exastro-oase" -d exastro/oase -p <port>:80 -p <port>:443

.. warning::
   | :command:`--privileged` および :command:`--hostname="exastro-oase"` は必須のオプションとなります。
   | また、サービス接続用のポートは環境に応じて変更をしてください。

docker-compose
--------------

| docker-compose を利用して OASE コンテナを起動します。
| 下記のような、 :file:`docker-compose.yml` ファイルを予め作成しておきます。

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
            - "<port>:80"
            - "<port>:443"

| コンテナを起動します。

.. code-block:: bash

   docker-compose up -d oase

.. warning::
   | :program:`privileged` および :program:`hostname: exastro-oase` は必須項目となります。
   | また、サービス接続用のポートは環境に応じて変更をしてください。


接続確認
========

.. include:: ../include/confirm_login.rst


環境情報
========

環境変数
--------

.. csv-table::
   :header: 設定名, 設定値, 説明
   :widths: 16,     25,   25

   OASE_ROOT_DIR, :file:`{<oase_directory>}/OASE/oase-root`,
   PYTHON_MODULE, :file:`/usr/bin/python3`,
   PYTHONPATH,    :file:`$OASE_ROOT_DIR`,
   JAVA_HOME,     :file:`/usr/lib/jvm/java-1.8.0-openjdk`,
   PATH,          :file:`/opt/apache-maven/bin:$JAVA_HOME/bin:/usr/bin`,
   CLASSPATH,     :file:`$JAVA_HOME/jre/lib:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar`,
   M2_HOME,       :file:`/opt/apache-maven-3.6.1`,
   JBOSS_HOME,    :file:`{<jboss_root_directory>}`,

コンフィグファイル設定
----------------------

なし

