=======================
opensocial.DataResponse
=======================

.. js:class:: opensocial.DataResponse

:js:class:`opensocial.DataRequest` クラスによるリクエストの完了時に :js:func:`~opensocial.DataRequest.send()` メソッドで指定されたコールバック関数に渡されるレスポンスオブジェクト。

get()
=====

.. js:function:: opensocial.DataResponse.get(key)

  :param String key: 取得するレスポンスのキー
  :returns: opensocial.ResponseItem

DataResponse オブジェクトからレスポンスを取得します。
:js:func:`opensocial.DataRequest.add` で ``opt_key`` に指定したキーを指定することで、キーに対応するリクエストのレスポンスが取得できます。

getErrorMessage()
=================

.. js:function:: opensocial.DataResponse.getErrorMessage()

  :returns: エラーメッセージ

データ取得時に発生したエラーのメッセージが返されます。

hadError()
==========

.. js:function:: opensocial.DataResponse.hadError()

  :returns: エラーが発生していた場合は true、そうでなければ false。

リクエスト時にエラーが発生したか否かを返します。

