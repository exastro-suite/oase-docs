==========
ルール作成
==========

| 監視アダプタや Web API により取得したメッセージに対する対処の紐付けをルールとして管理します。
| ディシジョンテーブルファイルはこのルールを定義するためのスプレッドシートのことです。


ディシジョンテーブルファイルの取得
==================================

| 新規追加したディシジョンテーブルのディシジョンテーブルファイルの取得には、:menuselection:`ルール --> ディシジョンテーブル` 画面を開き、作成対象のディシジョンテーブルの :guilabel:`` ボタンを押下します。

.. figure:: /images/ja/decision_table/decision_table_04.png
   :scale: 50%
   :align: center

   新規ディシジョンテーブルファイルのダウンロード
 
| 登録済みディシジョンテーブルのディシジョンテーブルファイルの取得には、:menuselection:`ルール --> ルール` 画面を開き、更新対象のディシジョンテーブルの :guilabel:`` ボタンを押下します。

.. figure:: /images/ja/rule/rule_03_07.png
   :scale: 50%
   :align: center

   登録済みディシジョンテーブルファイルのダウンロード


ルールの記述とアクションの実行
==============================

| あるメッセージがルールの条件にマッチした場合、アクション部で指定された対処を実施します。
| あるメッセージが、復数のルールの条件にマッチした場合、通常はディシジョンテーブルの上部に記載のものから対処が実施されます。

ルール
   | Exastro OASE が受信、もしくは、取得したメッセージが満たすべき条件とそのときの対処内容の定義のこと。
   | Exastro OASE では、ディシジョンテーブルファイルによってルールの管理をします。

マッチ
   | Exastro OASE が受信、もしくは、取得したメッセージがルールで定義された条件を満たす状態のこと。
      

| :numref:`rule_and_action` のようなルールがディシジョンテーブルに適用されている場合の具体例を示します。

| **パターン1** : "mysql is down" というアラート名のメッセージを取得した場合、Rule 2 の条件のみにマッチするため、DB 障害発生メールが送信されます。
| **パターン2** : "httpd is down" というアラート名のメッセージを取得した場合、Rule 1 と Rule 2 の両方の条件にマッチするため、Web 障害発生メールが送信され、メールの送信処理完了後、Rule 3 の対処である Apache の起動を実行されます。

.. csv-table:: 疑似的なルール
   :name: rule_and_action
   :escape: \
   :header: 条件名, 条件, 対処
   :widths: 30, 60, 50

   Rule 1, アラート名が "httpd is down" である場合, Web 障害発生メールを送信する
   Rule 2, アラート名が "mysql is down" である場合, DB 障害発生メールを送信する
   Rule 3, アラート名が "httpd is down" である場合, Apache を起動する

.. note::
   | :doc:`correlation` 利用時は、上記の動きとは異なります。

ディシジョンテーブルファイルの構成
==================================

| ディシジョンテーブルファイルは、2つのシートから構成されており、それぞれのシートの説明は下記の通りです。

Tables シート
   | ディシジョンテーブルファイル内にあるルールを定義するためのシートです。

example シート
   | ディシジョンテーブルファイル内にあるルールの記載例をまとめたシートです。

ルールの記載方法
================

テストリクエストおよびルールマッチング結果によるアクションの実行を行うため、ディシジョンテーブルファイルのTablesシートに判定の基準となる条件を記述する必要があります。

.. figure:: /images/ja/decision_table/decision_table_20.png
   :scale: 100%
   :align: center

   ディシジョンテーブルファイル(Tablesシート)


.. csv-table:: Tablesシート(ルール管理シート)の構成
   :header: 構成要素, 説明
   :widths: 20, 60

   コメント部,背景色緑色の箇所で、ユーザが任意に文字列を入力可能な項目です。
   条件部(条件式),背景色水色の箇所で、アラートメッセージの評価対象となる条件式定義する項目です。
   アクション部,背景色黄色の箇所で、対処内容について定義する項目です。
   アクション条件部,背景色赤色の箇所で、ルールの適用条件を定義する項目です。

| 以降は、各項目について説明をします。


コメント部
----------

| :menuselection:`Tablesシート` の背景色緑色の箇所で、ユーザが任意に文字列を入力可能な項目です。
| ここに記載した内容はシステムに一切の影響を与えません。

.. figure:: /images/ja/decision_table/decision_table_30.png
   :scale: 75%
   :align: center

   コメント部

.. csv-table:: コメント部の構成
   :header: 項目名, 説明, 記入例
   :widths: 20, 100, 20

   ルール説明,ユーザが任意に文字列を記載可能な箇所です。記載した内容はシステムに一切の影響を与えません。ルールに対するコメント欄として利用します。,ログ取得


条件部
------

| :menuselection:`Tablesシート` の背景色水色の箇所で、アラートメッセージの評価対象となる条件式定義する項目です。
| ディシジョンテーブルの新規作成時に設定した条件式と対応する項目が表示されます。

.. include:: ../include/decision_table_conditions.rst

.. figure:: /images/ja/decision_table/decision_table_31.png
   :scale: 75%
   :align: center

   条件部

.. note::
   | ディシジョンテーブル画面で新規追加および複製時に入力した"時間[HH:mm](From-to)"は、エクセルファイルでは"[HH:mm](from)"と"[HH:mm](to)"の2列に分かれます。開始日時と終了日時をそれぞれ入力して下さい。

.. note::
   | 条件部を空欄にすると、どのような値でも条件にマッチしますが、1つのルールに対して全ての条件部を空欄にすることはできません。


アクション部
------------

| :menuselection:`Tablesシート` の背景色黄色の箇所で、対処内容について定義する項目です。
| アクション部ではアクションに対して下記のような設定を加えることができます。

* アクションを実行前の事前承認メールの設定
* アクションの実行が失敗した場合のリトライ回数と間隔の設定
* 大量のアラートメッセージを受信した場合に同一のアクションの実行を抑止する間隔および回数を設定

.. figure:: /images/ja/decision_table/decision_table_32.png
   :scale: 100%
   :align: center

   アクション部

| 下記の :numref:`action_part` にアクション部の各項目の概要を記載します。
|  :doc:`action`、 :doc:`suppression` 、 :doc:`correlation` については、次節以降を参照して下さい。

.. csv-table:: アクション部の構成
   :name: action_part
   :escape: \
   :header: 項目名, 説明, 記入例
   :widths: 30, 60, 50

   ルール名（必須）, ルールの名前を指定します。,プロセス再起動
   発生事象,想定する発生事象についての説明を記載する箇所です。アクション履歴やServiceNowのインシデント管理の説明欄に記載されます。,プロセスの無応答を検知しました。
   対処概要,対処内容についての説明を記載する箇所です。アクション履歴やServiceNowのインシデント管理の説明欄に記載されます。,プロセスを再起動を実施します。
   アクション種別,対処を行うドライバの選択をします。詳細は :doc:`action` を確認してください。,ITA(ver1)
   アクションパラメータ情報,ドライバに渡すパラメータ情報を記載します。詳細は :doc:`action` を確認してください。,CONDUCTOR_CLASS_ID=1\,OPERATION_ID=1
   承認メールパラメータ情報,承認メール送信時のパラメータ情報を記載します。詳細は :doc:`approval` を確認してください。,MAIL_NAME=oasetest\,MAIL_TO=aaa@aaa.com;bbb@bbb.com\,MAIL_CC=ccc@ccc.com\,MAIL_BCC=ddd@ddd.com\,MAIL_TEMPLATE=test_template
   リトライ間隔,対処に失敗した場合の次回実行までの待ち時間(秒)を記載します。,5
   リトライ回数,対処を試行する回数を記載します。例えば、2と入力した場合は1回のリトライが発生します。,1
   抑止間隔, :doc:`suppression` で使用します。大量に同一のアラートを受信した場合には、同一のアクションが何度も実行されることを防ぐための :doc:`suppression` があります。同一のアラートの実行を抑止する間隔(秒)を記載します。,120
   抑止回数, :doc:`suppression` で使用します。同一のアラートの実行を抑止する回数を記載します。抑止回数を超えた場合、次の抑止間隔が始まるまで都度ルール内の対処が実行されます。,100
   条件回数, :doc:`correlation` で使用します。この値が設定されたルールにマッチするメッセージの数が条件回数に達した場合、ルールが真となります。,2
   条件期間(秒), :doc:`correlation` で使用します。条件回数を評価する期間を記載します,600
   大グループ, :doc:`correlation` で使用します。コリレーション分析をする小グループをグルーピングします。,Group1
   優先順位, :doc:`correlation` で使用します。小グループに対する優先順位です。小グループがどちらも真となった場合、この優先順位が最も高い小グループのルールが実行されます。数値が小さいほど優先順には高いです。,1
   小グループ, :doc:`correlation` で使用します。コリレーション分析をする対象ルールをグルーピングします。,Group1-2
   優先順位, :doc:`correlation` で使用します。小グループ内のルールに対する優先順位です。この優先順位が最も高いルールがコリレーション分析開始のトリガーとなり、最も低いルールのアクションが実行されます。数値が小さいほど優先順には高いです。,2



アクション条件部
----------------

| :menuselection:`Tablesシート` の背景色赤色の箇所で、ルールが有効・無効となる日時について定義する項目です。

.. figure:: /images/ja/decision_table/decision_table_33.png
   :scale: 75%
   :align: center

   アクション条件部

| 下記の :numref:`action_condition` にアクション部の各項目の概要を記載します。

.. csv-table:: アクション条件部の構成
   :name: action_condition
   :escape: \
   :header: 項目名, 説明, 記入例
   :widths: 30, 60, 50

   有効日,ルールの有効日を :program:`yyyy-mm-dd HH:mm` 形式で設定できます。有効日を設定しない場合は空欄にします。有効日を2020-01-01 01:00に設定した場合、2020-01-01 01:00:01以降のイベントにマッチします。,2020-01-01 01:00
   無効日,ルールの無効日を :program:`yyyy-mm-dd HH:mm` 形式で設定できます。無効日を設定しない場合は空欄にします。無効日を2020-01-01 01:00に設定した場合、2020-01-01 01:00:00以降のイベントにはマッチしません。,2020-01-01 01:00
