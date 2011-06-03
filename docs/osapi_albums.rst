==============
osapi.albums.*
==============

osapi.albums.get()
==================

::

  osapi.albums.get({
    userId: "@me",
    groupId: "@self",
    albumId: []
  })

アルバムの一覧を取得します。アルバム内の画像を取得するには :doc:`/docs/osapi_mediaitems` と組み合わせて使う必要があります。
opAlbumPlugin がインストールされていないSNSではこのメソッドは使用できません。

使用例
======

アルバムの一覧を列挙する例:

.. code-block:: javascript

  if (!osapi.albums) {
    alert("osapi.albums.* が使用できません");
  } else {
    osapi.albums.get().execute(function (data) {
      if (data.error) {
        alert("取得に失敗しました");
        return;
      }
      for (var i = 0: i < data.list.length; i++) {
        // .....
      }
    });
  }

注意事項
========

osapi.albums.* は opAlbumPlugin がインストールされていないSNSでは利用できません。

