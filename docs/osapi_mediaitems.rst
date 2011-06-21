==================
osapi.mediaitems.*
==================

osapi.mediaitems.get()
======================

::

  osapi.mediaitems.get({
    userId: "@me",
    groupId: "@self",
    albumId: "",
  })

アルバムに登録されている画像を取得します。
opAlbumPlugin がインストールされていないSNSでは使用できません。

取得されるデータの例
====================

::

  {
    "startIndex": 0,
    "totalResults": 2,
    "itemsPerPage": 20,
    "list": [
      {
        "albumId": "1",
        "created": "2011-06-03 20:54:18",
        "description": "foo",
        "fileSize": "0",
        "id": "1",
        "lastUpdated": "2011-06-03 20:54:18",
        "thumbnailUrl": "http://sns.example.com/cache/img/png/w180_h180/a_1_36faf228906a240477755f171051290b018d5a17_png.png",
        "title": "foo",
        "type": "IMAGE",
        "url": "http://sns.example.com/cache/img/png/w_h/a_1_36faf228906a240477755f171051290b018d5a17_png.png"
      },
      {
        "albumId": "1",
        "created": "2011-06-03 20:55:15",
        "description": "bar",
        "fileSize": "0",
        "id": "2",
        "lastUpdated": "2011-06-03 20:55:15",
        "thumbnailUrl": "http://sns.example.com/cache/img/png/w180_h180/a_1_18a0cf3b55454e165743349fc63b43bcc45fb417_png.png",
        "title": "bar",
        "type": "IMAGE",
        "url": "http://sns.example.com/cache/img/png/w_h/a_1_18a0cf3b55454e165743349fc63b43bcc45fb417_png.png"
      }
    ]
  }

使用例
======

VIEWER が所有するアルバムから画像の一覧を取得する例:

.. code-block:: javascript

  if (!(osapi.albums && osapi.mediaitems)) {
    alert("osapi.albums または osapi.mediaitems が使用できません");
  } else {
    osapi.albums.get().execute(function (albums) {
      if (albums.error) {
        alert("アルバムの取得に失敗しました");
        return;
      }
      if (albums.list.length < 1) {
        alert("アルバムがありません");
        return;
      }

      var album_id = albums.list[0].id;
      osapi.mediaitems.get({albumId: album_id}).execute(function (mediaitems) {
        if (mediaitems.error) {
          alert("画像の取得に失敗しました");
          return;
        }

        for (var i = 0; i < mediaitems.list.length; i++) {
          // .....
        }
      });
    });
  }


注意事項
========

osapi.mediaitems.* は opAlbumPlugin がインストールされていないSNSでは利用できません。
