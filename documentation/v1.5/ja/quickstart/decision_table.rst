========================
デシジョンテーブルの作成
========================

| 新規デシジョンテーブルの設定方法について説明します。
| Exastro OASE におけるデシジョンテーブルとは、メッセージに対する判断を行う仕組みのことを指します。


デシジョンテーブルの追加
========================

| デシジョンテーブルの設定は、画面上部のメニューの :menuselection:`ルール --> デシジョンテーブル` から行えます。
| 新たにデシジョンテーブルを作成するために、:guilabel:`新規追加` をクリックします。

| :menuselection:`基本情報・権限` 設定フォームから設定を行います。

.. figure:: ../images/quickstart/new_decision_table_01.png
   :width: 400px
   :align: left

   基本情報・権限設定

.. glossary::

   デシジョンテーブル名 : た
      | デシジョンテーブル名を入力して下さい。マルチバイト含む文字列の入力が可能です。
      |  :program:`新規デシジョンテーブル` として登録します。

   権限の設定 : か
      | グループに割り当てる権限を定義します。
      | クイックスタートでは全項目を更新可能に設定します。
  
      .. warning::
         | 簡単のために全ての項目に更新可能権限を割り当てています。
         | 本番で運用する際には、適切なグループの作成と権限の割当を行ってください。

.. raw:: html

   <div style="clear:both;"></div>

| 入力が完了したら、:guilabel:`条件式の設定へ` をクリックします。
| :menuselection:`条件式` 設定フォームで、アラートメッセージに対する条件式を設定を行います。

.. figure:: ../images/quickstart/new_decision_table_02.png
   :width: 400px
   :align: left

   条件式

.. glossary::

   条件名 : さ
      | 条件に対する名前を入力して下さい。
      |  :program:`アラートメッセージ` として登録します。

   条件式 : さ
      | 条件式は、監視アプリケーションから取得したイベント(メッセージ)を評価するための式です。
      | デシジョンテーブルに記載の値との関係を表します。
      | アラートメッセージがこの条件式に一致する場合、Exastro OASE はアクションを実行します。
      |  :program:`正規表現に一致する` を選択します。


.. raw:: html

   <div style="clear:both;"></div>

| 入力が完了したら、:guilabel:`未知事象通知の設定へ` をクリックします。
| :menuselection:`未知事象通知` 設定フォームで、通知先の設定を行います。

.. figure:: ../images/quickstart/new_decision_table_03.png
   :width: 400px
   :align: left

   未知事象通知

.. glossary::

   未知事象通知 : ま
      | 未知事象(ルールに定義されていないイベント)が発生した場合の通知先を設定します。
      |  :program:`通知しない` として登録します。

.. raw:: html

   <div style="clear:both;"></div>

| 全ての項目の入力が完了したら、:guilabel:`保存` をクリックします。
| 新規に追加したディシジョンテーブルが一覧画面に表示されます。

.. figure:: ../images/quickstart/new_decision_table_04.png
   :width: 800px
   :align: center

   デシジョンテーブル一覧
