=================
opensocial.IdSpec
=================

.. js:class:: opensocial.IdSpec

:js:class:`~opensocial.DataRequest` クラスなどで、対象となるメンバーを指定するために使用するクラスです。対象として 1 人または複数人のメンバーを指定することができます。

IdSpec オブジェクトを作成する場合は :js:func:`opensocial.newIdSpec()` メソッドを使用して下さい。

getField()
==========

.. js:function:: opensocial.IdSpec.getField(key, opt_params)

  :param opensocial.IdSpec.Field key: 取得するフィールド
  :param Map.<opensocial.DataRequest.DataRequestFields|Object> opt_params: 取得時のオプション
  :returns: String

IdSpec オブジェクトのフィールドの値を取得します。

setField()
==========

.. js:function:: opensocial.IdSpec.setField(key, data)

  :param opensocial.IdSpec.Field key: 設定するフィールド
  :param String data: 設定するデータ

IdSpec オブジェクトのフィールドに値をセットします。

