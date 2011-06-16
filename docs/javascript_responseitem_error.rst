=============================
opensocial.ResponseItem.Error
=============================

.. js:class:: opensocial.ResponseItem.Error

レスポンスに含まれるエラーとして利用される項目です。エラーの種類によっては、ここに含まれていない独自のエラーコードがレスポンスとして返される場合もあります。

opensocial.ResponseItem.Error.BAD_REQUEST
=========================================

.. js:data:: opensocial.ResponseItem.Error.BAD_REQUEST

不正なリクエストが送信された場合に返されます。

opensocial.ResponseItem.Error.FORBIDDEN
=======================================

.. js:data:: opensocial.ResponseItem.Error.FORBIDDEN

リクエストされたデータにアクセスする権限がないときに返されます。

opensocial.ResponseItem.Error.INTERNAL_ERROR
============================================

.. js:data:: opensocial.ResponseItem.Error.INTERNAL_ERROR

リクエストの実行時に予期しないエラーが発生した場合に返されます。

opensocial.ResponseItem.Error.LIMIT_EXCEEDED
============================================

.. js:data:: opensocial.ResponseItem.Error.LIMIT_EXCEEDED

制限を超える量のリクエストが送られた場合に返されます。

opensocial.ResponseItem.Error.NOT_IMPLEMENTED
=============================================

.. js:data:: opensocial.ResponseItem.Error.NOT_IMPLEMENTED

コンテナがサポートしていないリクエストが送られた場合に返されます。

opensocial.ResponseItem.Error.UNAUTHORIZED
==========================================

.. js:data:: opensocial.ResponseItem.Error.UNAUTHORIZED

未認証のためにリクエストされたデータにアクセスする権限がないときに返されます。権限を取得するためには :js:func:`opensocial.requestPermission()` メソッドを使用して下さい。

