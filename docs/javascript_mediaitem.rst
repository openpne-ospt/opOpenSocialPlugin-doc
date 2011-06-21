====================
opensocial.MediaItem
====================

.. js:class:: opensocial.MediaItem

画像や動画、音声などのメディアを表すクラスです。

ただし、現在 opOpenSocialPlugin では画像以外の MediaItem を扱うことは出来ません。

getField()
==========

.. js:function:: opensocial.MediaItem.getField(key, opt_params)

  :param opensocial.MediaItem.Field key: 取得するフィールド
  :param Map.<opensocial.DataRequest.DataRequestFields|Object> opt_params: 取得時のオプション
  :returns: String

MediaItem のフィールドの値を取得します。

setField()
==========

.. js:function:: opensocial.MediaItem.setField(key, data)

  :param opensocial.MediaItem.Field key: 設定するフィールド
  :param String data: 設定するデータ

MediaItem のフィールドの値を設定します。

