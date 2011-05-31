=======
osapi.*
=======

.. _osapi.Request_single:

osapi.Request (シングルリクエスト)
==================================

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
~~~~~~

.. code-block:: javascript

  osapi.people.getViewerFriends().execute(function (data) {
    if (data.error) {
      alert(data.error.message);
    } else {
      alert('現在フレンドは ' + data.totalResults + ' 人います'):
    }
  });

