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
