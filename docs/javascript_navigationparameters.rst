===============================
opensocial.NavigationParameters
===============================

.. js:class:: opensocial.NavigationParameters

:js:func:`opensocial.requestShareApp()` メソッドで、リクエスト後に移動させる場所を指示する (**実装されていません**) ために使用します。

このクラスのオブジェクトを生成する際には :js:func:`opensocial.newNavigationParameters()` メソッドを使用して下さい。

getField()
==========

.. js:function:: opensocial.NavigationParameters.getField(key[, opt_params])

  :param String key: 取得するデータのキー
  :param Map.<opensocial.DataRequest.DataRequestFields|Object> opt_params: 取得時に要求するパラメータ
  :returns: String

setField()
==========

.. js:function:: opensocial.NavigationParameters.setField(key, data)

  :param String key: 設定するデータのキー
  :param Object data: 設定するデータ

