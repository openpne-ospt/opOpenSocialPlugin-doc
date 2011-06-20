=====================
opensocial.Collection
=====================

.. js:class:: opensocial.Collection

複数のアイテムが格納されるコレクションクラスです。 :js:class:`opensocial.DataRequest` でメンバーやアクティビティ等のコレクションをリクエストすると、このクラスのオブジェクトが取得されます。

asArray()
=========

.. js:function:: opensocial.Collection.asArray()

  :returns: Array.<Object>

コレクションの内容を配列で返します。

each()
======

.. js:function:: opensocial.Collection.each(fn)

  :param Function fn: コールバック関数

指定されたコールバック関数の引数にコレクションの内容を 1 個ずつ渡して呼び出します。
jQuery や prototype.js に実装されている each メソッドに近い動作をします。

getById()
=========

.. js:function:: opensocial.Collection.getById(id)

  :param String id: 取得するアイテムのID
  :returns: Object

コレクションの中から指定されたIDを持つアイテムを取得します。見つからなかった場合は null が返されます。

このメソッドは実行するたびにコレクション内を線形探索する実装となっているため、パフォーマンスが要求される場面で多用すべきではありません。

getOffset()
===========

.. js:function:: opensocial.Collection.getOffset()

  :returns: Integer

コレクションのオフセット (0 から開始) を取得します。

例えば、全 200 件のアクティビティのうち 50 件目から 99 件目までを取得した場合、getOffset() は 49 を返します。

getTotalSize()
==============

.. js:function:: opensocial.Collection.getTotalSize()

  :returns: Integer

このコレクションの元となった結果セットの全体の件数を取得します。

例えば、全 200 件のアクティビティのうち 50 件目から 99 件目までを取得した場合、getTotalSize() は 200 を返します。

size()
======

.. js:function:: opensocial.Collection.size()

  :returns: Integer

このコレクションに含まれているアイテムの件数を取得します。

例えば、全 200 件のアクティビティのうち 50 件目から 99 件目までを取得した場合、size() は 50 を返します。

