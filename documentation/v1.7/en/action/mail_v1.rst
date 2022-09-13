==============
Mail Driver
==============

| The mail driver notifies users when an event is detected by the monitor applications.
| It is possible to connect multiple mail servers to a single decision table.

New registrations
========

| Go to the :menuselection:`System --> Action settings` page.
| Press the :guilabel:` Add Action target` button on top of the page.
| Select :menuselection:`mail Driver ver1` .

.. tip::
    | The user must have "Edit" permissions in the Action settings menu in order to add Action settings.


.. figure:: /images/ja/action/action_06.png
   :scale: 80%
   :align: center

   Select Action settings

| Fill in the Mail Driver setting items

.. figure:: /images/ja/action/action_09.png
   :scale: 35%
   :align: left

   Mail Driver(ver. 1) settings page


.. csv-table:: Mail Driver(ver. 1) setting items
   :header: Settings name, Description
   :widths: 20, 60

   Name, Specify a name for the Mail Driver.
   Protocol, Select either "smtp" or "smtp_auth" for the Mail server's connection protocol.
   smtp server, Input the Mail server's FQDN or IP Address.
   Port, Input the Port number used when connecting to the Mail server.
   User name, Input the Mail account's user name.
   Password, Input the Mail account's password.

.. raw:: html

   <div style="clear:both;"></div>

| After inputting all the required information, press the :guilabel:` Save` button.

Edit settings
========

| Open the  :menuselection:`System --> Action settinsg` menu and press the :menuselection:`Mail Driver ver1` tab.

.. figure:: /images/ja/action/action_03.png
   :scale: 60%
   :align: center

   Mail driver list

| Press the Action driver's Detailed information button :guilabel:``.

.. figure:: /images/ja/action/action_10.png
   :scale: 60%
   :align: center

   Mail driver information page

| Press the :guilabel:` Edit` button on the bottom of the screen and edit your desired information

.. figure:: /images/ja/action/action_11.png
   :scale: 60%
   :align: center

   Mail driver edit page

| After inputting all the required information, press the :guilabel:` Save` button.


メールテンプレート
==================

| メールテンプレート機能を使うことで、ルールごとに個別の宛先や件名、本文などでメール通知を行うことができます。

| 上メニューの :menuselection:`システム --> アクション設定` からアクション設定画面を開きます。
| :menuselection:`mail Driver ver1` タブを選択し、 :guilabel:` メールテンプレート` ボタンを押下します。


.. figure:: /images/ja/action/action_08.png
   :scale: 80%
   :align: center
   
   メールドライバ一覧画面

| :guilabel:` 新規追加` ボタンを押下します。

.. figure:: /images/ja/action/action_40.png
   :scale: 80%
   :align: center
   
   メールテンプレート一覧画面

| メールテンプレートの設定項目を入力します。

.. figure:: /images/ja/action/action_42.png
   :scale: 25%
   :align: left

   メールテンプレート設定画面

.. csv-table:: メールテンプレートの設定項目
   :header: 構成要素, 説明
   :widths: 20, 60

   テンプレート名, テンプレート名を入力します。
   宛先, 送信先のメールアドレスを入力します。
   CC, 送信先のメールアドレスを入力します。
   BCC, 送信先のメールアドレスを入力します。
   件名, メールの件名を入力します。
   本文, メールの本文を入力します。

.. raw:: html

   <div style="clear:both;"></div>

| メールテンプレートの詳細確認や編集を行う場合は、対象のメールテンプレートの詳細確認ボタン :guilabel:`` をクリックし、詳細画面から編集できます。

.. figure:: /images/ja/action/action_45.png
   :scale: 80%
   :align: center

   メールテンプレートの詳細画面

.. tip::
   | メールテンプレートの編集・削除にはアクション設定画面に対する「更新可能」のアクセス権限が必要です。
