.. _restful_activities:

===========================
アクティビティ (Activities)
===========================

アプリの活動状況等を共有する仕組みとしてアクティビティが存在します。


URI Fragment
============

.. 動作確認未完了

=====================================================   ==================================================================================
``GET /activities/{guid}/@self``                        {guid} のアクティビティ
``GET /activities/{guid}/@self/{appid}``                {appid} によって投稿された {guid} のアクティビティ
``GET /activities/{guid}/@friends``                     {guid} のフレンドのアクティビティ
``GET /activities/{guid}/@friends/{appid}``             {appid} によって投稿された {guid} のフレンドのアクティビティ
``GET /activities/{guid}/{groupid}``                    {uid} の属している {groupid} のメンバーのアクティビティ
``GET /activities/{guid}/{groupid}/{appid}``            {appid} によって投稿された {uid} の属している {groupid} のメンバーのアクティビティ
``GET /activities/{guid}/@self/{appid}/{activityid}``   指定されたアクティビティ (1 件) の取得
``GET /activities/@supportedFields``                    Activity オブジェクトでサポートされているフィールドの一覧
=====================================================   ==================================================================================

例
==

アクティビティの投稿は、
POST http://sns.example.com/api.php/social/rest/activities/@me/@self で以下のような内容を送信することにより行うことができます。
このとき Content-Type は application/json として下さい。

::

  {
    "title": "hello!",
    "url": "http://sns.example.com/..."
  }

「hello!」 という内容のActivityが送信されます。APIでのアクティビティの投稿間隔には制限があります。デフォルトでは30秒以内の間隔で投稿することはできません。この秒数はSNSの管理画面より変更することができます。
この制限により、投稿が失敗した場合はレスポンスコード500のエラーを返します。

アクティビティの公開範囲は、利用者が設定したアプリの公開範囲に準じます。

オプションとして、アクティビティにURL情報を付加することができますが、そのURLはSNSのドメインと同一である必要があります。

アクティビティの取得は以下のように行います

GET http://sns.example.com/api.php/social/rest/activities/@me/@self::

  {
    "entry": [
      {
        "id":"2",
        "userId":"1",
        "title":"hogehoge",
        "postedTime":"2010-04-21T21:02:56+09:00"
      },
      {
        "id":"1",
        "userId":"1",
        "title":"foobar",
        "postedTime":"2010-04-21T19:09:19+09:00"
      }
    ],
    "startIndex":0,
    "totalResults":2,
    "itemsPerPage":20
  }

この状態では、アプリを指定していないので、発行元の関係なく指定のメンバーのアクティビティストリームを取得ができます。

**アプリごとに発行しているコンシューマキーを利用してアクセスしている場合** は以下が利用できます。

GET http://sns.example.com/api.php/social/rest/activities/@me/@self/@app::

  {
    "entry": [
      {
        "id":"2",
        "userId":"1",
        "title":"hogehoge",
        "postedTime":"2010-04-21T21:02:56+09:00"
      },
    ],
    "startIndex":0,
    "totalResults":1,
    "itemsPerPage":20
  }

これにより、アプリが発行したアクティビティのみを表示することができます。

