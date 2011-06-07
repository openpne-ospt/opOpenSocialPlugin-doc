======================
opensocial.Environment
======================

.. js:class:: opensocial.Environment

アプリが動作している環境の情報を表すクラスです。 :js:func:`opensocial.getEnvironment()` メソッドで取得できます。

getDomain()
===========

.. js:function:: opensocial.Environment.getDomain()

  :returns: ドメイン名の文字列

現在のドメイン名を取得します。

supportsField()
===============

.. js:function:: opensocial.Environment.supportsField(objectType, fieldName)

  :param opensocial.Environment.ObjectType objectType: オブジェクトの種類
  :param String fieldName: フィールド名
  :return: サポートされていれば true、そうでなければ false。

指定されたフィールドがSNSでサポートされているかどうかを調べます。 ``objectType`` に指定できるパラメータの一覧は :js:class:`opensocial.Environment.ObjectType` を参照して下さい。
