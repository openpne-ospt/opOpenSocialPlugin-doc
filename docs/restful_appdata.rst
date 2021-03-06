.. _restful_appdata:

====================
永続データ (AppData)
====================

永続データはアプリを所有する人同士での情報の共有などで利用することの出来る機能です。

アプリ・メンバーごとにKey-Valueの組み合わせで情報を管理します。

情報の書き出し、削除は自分のIDにしか行うことができません。取得は、対象者が取得者のフレンドかつアプリ所有をしていた場合に行うことができます。

**この機能は、アプリごとに発行したコンシューマキーを利用してAPIアクセスをする必要があります。**

URI Fragment
============

========================================  ====================================================
``GET /appData/{guid}/@self/{appid}``     {guid} に対する {appid} の永続データを取得
``POST /appData/{guid}/@self/{appid}``    {guid} に対する {appid} の永続データを保存
``DELETE /appData/{guid}/@self/{appid}``  {guid} に対する {appid} の永続データを削除
``GET /appData/{guid}/@friends/{appid}``  {guid} のフレンドに対する {appid} の永続データを取得
========================================  ====================================================

{appid} には ``@app`` またはアプリの ID を指定します。使用したコンシューマキーに対応するアプリ以外の ID は指定できません。

例
==

永続データの作成は
POST http://sns.example.com/api.php/social/rest/appdata/@me/@self/@app で以下のような内容を送信することにより行うことができます。
このとき Content-Type は application/json として下さい。

::

  {
    "foo1":"bar1",
    "foo2":"bar2",
    "foo3":"bar3"
  }

foo1=bar1、foo2=bar2が保存されます。すでに、当該キーが存在する場合は上書きされます。

取得は以下のように行えます。

GET http://sns.example.com/api.php/social/rest/appdata/@me/@self/@app::

  {
    "entry": {
      "1": {
        "foo1":"bar1",
        "foo2":"bar2",
        "foo3":"boo3"
      }
    }
  }

他人の永続データを取得する場合は、その人がVIEWERのフレンドであり、かつアプリを所有している必要があります。

削除は

DELETE http://sns.example.com/api.php/social/rest/appdata/@me/@self/@app?fields=foo1,foo2

のように :ref:`fields <rest_common_params>` パラメータにカンマ区切りでキーを指定するにより削除を行うことができます。

fieldsパラメータが存在しない場合は、そのメンバーのアプリについての永続データが全て削除されます。


