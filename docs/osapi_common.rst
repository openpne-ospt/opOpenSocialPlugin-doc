=======
osapi.*
=======

.. _osapi.Request:

osapi.Request
=============

OSAPIで osapi.people.get() などを呼び出すと osapi.Request オブジェクトが生成されます。このオブジェクトを使用して取得を実行するためには ``execute()`` メソッドを呼び出す必要があります。

osapi.Request.execute()
-----------------------

.. js:function:: osapi.Request.execute(callback)

  :param Function callback: 取得完了後に呼び出されるコールバック関数。エラー時でも呼び出されます。

コールバック関数に渡される値の例
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1件のみ取得の場合::

  {
    "id": "1",
    "isOwner": true,
    "isViewer": true,
    "hasApp": true,
    "displayName": "OpenPNE\u541b",
    "thumbnailUrl": "http://sns.example.com/cache/img/jpg/w_h/m_1_70481ff86b46bdb146bc78781a4c2a2d9a1581f6_jpg.jpg",
    "profileUrl": "http://sns.example.com/member/1",
    "gender": "male"
  }

複数件取得の場合::

  {
    "startIndex": 0,
    "totalResults": 3,
    "itemsPerPage": 10,
    "list": [
      {
        "displayName": "Alice",
        "hasApp": false,
        "id": "2",
        "isOwner": false,
        "isViewer": false,
        "profileUrl": "http://sns.localhost/sqlite/member/2",
        "thumbnailUrl": "",
        "gender": ""
      },
      {
        "displayName": "Bob",
        "hasApp": false,
        "id": "3",
        "isOwner": false,
        "isViewer": false,
        "profileUrl": "http://sns.localhost/sqlite/member/3",
        "thumbnailUrl": "",
        "gender": ""
      },
      {
        "displayName": "Carol",
        "hasApp": false,
        "id": "4",
        "isOwner": false,
        "isViewer": false,
        "profileUrl": "http://sns.localhost/sqlite/member/4",
        "thumbnailUrl": "",
        "gender": ""
      }
    ]
  }

取得時にエラーが返された場合::

  {
    "id": "people.get",
    "error": {
      "code": 501,
      "message": "Not implemented"
    }
  }

使用例
------

.. code-block:: javascript

  osapi.people.getViewerFriends().execute(function (data) {
    if (data.error) {
      alert(data.error.message);
    } else {
      alert('現在フレンドは ' + data.totalResults + ' 人います'):
    }
  });

バッチリクエスト
================

OSAPI のバッチリクエストでは、SNSに対して複数のリクエストを一度に送信することができます。

osapi.newBatch()
----------------

.. js:function:: osapi.newBatch()

  :return: osapi.BatchRequest オブジェクト

新しいバッチリクエストのためのオブジェクトを作成します。

osapi.BatchRequest.add()
------------------------

.. js:function:: osapi.BatchRequest.add(key, request)

  :param String key: リクエスト完了時に結果を取得するためのキー
  :param osapi.Request request: 実行するリクエスト
  :return: osapi.BatchRequest オブジェクト

バッチリクエストで処理するリクエストを追加します。このメソッドが ``osapi.BatchRequest`` を返しているのは、リクエストの追加をメソッドチェインで記述できるようにするためです。

osapi.BatchRequest.execute()
----------------------------

.. js:function:: osapi.BatchRequest.execute(callback)

  :param Function callback: コールバック関数

バッチリクエストを実行します。

使用例
------

OWNER と VIEWER のフレンドを一度に取得し、共通のフレンドを列挙するコードの例

.. code-block:: javascript

  osapi.newBatch()
    .add('ownerFriends', osapi.people.getOwnerFriends({count: 100}))
    .add('viewerFriends', osapi.people.getViewerFriends({count: 100}))
    .execute(function (data) {
      if (data.error || data.ownerFriends.error || data.viewerFriends.error) {
        alert('取得に失敗しました');
      }

      var ownerFriends = data.ownerFriends.list;
      var viewerFriends = data.viewerFriends.list;

      var ownerPos = 0, viewerPos = 0;
      var items = '';

      while (true) {
        var ownerPosId = ownerFriends[ownerPos] ? ownerFriends[ownerPos].id : Number.MAX_VALUE;
        var viewerPosId = viewerFriends[viewerPos] ? viewerFriends[viewerPos].id : Number.MAX_VALUE;

        if (ownerPosId === Number.MAX_VALUE && viewerPosId === Number.MAX_VALUE) {
          break;
        }

        if (ownerPosId < viewerPosId) {
          ownerPos++;
        } else if (ownerPosId > viewerPosId) {
          viewerPos++;
        } else {
          items += '<li>' + ownerFriends[ownerPos].displayName + '</li>\n';
          ownerPos++;
          viewerPos++;
        }
      }

      document.getElementById('friendList').innerHTML = items;
    });

.. note::

  実際にはフレンドが100人以上のメンバーも考慮する必要があるため、実装するためのコードはより長く複雑になります。

