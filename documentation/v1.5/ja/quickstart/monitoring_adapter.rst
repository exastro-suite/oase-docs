==================
監視アダプタの作成
==================

| 新規監視アダプタの作成方法について ZABBIX監視アダプタの導入を例に説明します。
| Exastro OASE における監視アダプタとは、監視アプリケーションからアラート情報を取得するための機能を指します。


ZABBIX監視アダプタの追加
========================

| 監視アダプタの設定は、画面上部のメニューの :menuselection:`システム --> 監視アダプタ` から行えます。
| 新たに監視アダプタを登録するために、:guilabel:` 監視先の追加` をクリックします。

| :menuselection:`監視先の追加` 設定フォームから設定を行います。

.. figure:: ../images/quickstart/new_monitoring_adapter_01.png
   :width: 400px
   :align: left

   監視先の追加

.. glossary::

   監視先の選択 : か
      | 監視アプリケーション(Zabbix)に対応する監視アダプタを選択します。
      | :guilabel:`ZABBIX Adapter ver1` を選択します。

.. raw:: html

   <div style="clear:both;"></div>

| :menuselection:`ZABBIX Adapter ver1` 設定フォームで、連携する監視アプリケーション(Zabbix)に対する接続情報とデシジョンテーブル連携のための設定を行います。

.. figure:: ../images/quickstart/new_monitoring_adapter_02.png
   :width: 400px
   :align: left

   ZABBIX Adapter ver1

.. glossary::

   名前 : な
      | 監視アダプタ名を入力します。
      |  :program:`新規ZABBIX監視アダプタ` として登録します。

   プロトコル : は
      | 監視アプリケーション(Zabbix)との接続のための通信プロトコルを選択します。
      |  :program:`http` を選択します。

   ホスト/IP : は
      | 監視アプリケーション(Zabbix)に接続するためのホスト名、もしくは、IPアドレスを指定します。

   ポート : は
      | 監視アプリケーション(Zabbix)と接続時に使用するポート番号を指定します。
      |  :program:`80` 番ポートを使用します。

   ユーザ名 : や
      | 監視アプリケーション(Zabbix)にログインで使用するユーザを入力します。

.. tip:: 監視アラートを閲覧できるユーザを指定する必要があります。

.. glossary::

   パスワード : は
      | 監視アプリケーション(Zabbix)にログインするためのパスワードを入力します。

   デシジョンテーブル名選択 : た
      | 監視連携する対象のデシジョンテーブルを選択します。
      | :doc:`decision_table` で作成したディシジョンテーブルを選択します。

   突合情報 : た
      | ディシジョンテーブルで突合する監視アプリケーションの項目を選択します。
      |  :program:`description` を選択します。


.. raw:: html

   <div style="clear:both;"></div>


| 全ての項目の入力が完了したら、:guilabel:` 保存` をクリックします。
| 新規に追加した監視アダプタが一覧画面に表示されます。

.. figure:: ../images/quickstart/new_monitoring_adapter_03.png
   :width: 800px
   :align: center

   監視アダプタ一覧

監視アプリケーション連携確認
============================

| 監視アプリケーションとの連携は、画面上部のメニューの :menuselection:`ルール --> リクエスト履歴` から行えます。
| Zabbix でアラートが発生している状態では、下図のようにリクエスト履歴に対応するアラート(イベント情報)が表示されます。

.. figure:: ../images/quickstart/new_monitoring_adapter_04.png
   :width: 800px
   :align: center

   リクエスト履歴

| Zabbix でアラート表示にされているにも関わらず :menuselection:`リクエスト履歴` に表示されない場合、連携に失敗している可能性があります。
| 設定内容やネットワークの到達性、ユーザの権限などを確認して下さい。
