===================
opensocial.Activity
===================

.. js:class:: opensocial.Activity

アクティビティを表すクラスです。アクティビティの取得・投稿時に使用します。

Activity オブジェクトを作成する場合は :js:func:`opensocial.newActivity()` メソッドを使用して下さい。

getField()
==========

.. js:function:: opensocial.Activity.getField(key, opt_params)

  :param opensocial.Activity.Field key: 取得するフィールド
  :param Map.<opensocial.DataRequest.DataRequestFields|Object> opt_params: 取得時のオプション
  :returns: String

アクティビティのフィールドの値を取得します。

getId()
=======

.. js:function:: opensocial.Activity.getId()

  :returns: String

アクティビティのIDを取得します。
このメソッドは ``getField(opensocial.Activity.Field.ID)`` の短縮形です。

setField()
==========

.. js:function:: opensocial.Activity.setField(key, data)

  :param opensocial.Activity.Field key: 設定するフィールド
  :param String data: 設定するデータ

アクティビティのフィールドに値を設定します。

