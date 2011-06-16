=======================
opensocial.ResponseItem
=======================

.. js:class:: opensocial.ResponseItem

サーバーからのレスポンスを表すクラスです。 :js:class:`opensocial.DataResponse` などで使用されます。

getData()
=========

.. js:function:: opensocial.ResponseItem.getData()

  :returns: Object

レスポンスの内容を取得します。

getErrorCode()
==============

.. js:function:: opensocial.ResponseItem.getErrorCode()

  :returns: String

リクエスト中にエラーが発生していた場合、エラーコードを返します。返されるエラーコードはSNS独自のものや :js:class:`opensocial.ResponseItem.Error` で定義されているものがあります。

getErrorMessage()
=================

.. js:function:: opensocial.ResponseItem.getErrorMessage()

  :returns: String

リクエスト中にエラーが発生していた場合、エラーメッセージを返します。

getOriginalDataRequest()
========================

.. js:function:: opensocial.ResponseItem.getOriginalDataRequest()

  :returns: opensocial.DataRequest

このオブジェクトのリクエストに使用した :js:class:`~opensocial.DataRequest` オブジェクトを返します。

hadError()
==========

.. js:function:: opensocial.ResponseItem.hadError()

  :returns: エラーが発生していれば true、そうでなければ false。

リクエスト中にエラーが発生していたかどうかを返します。

