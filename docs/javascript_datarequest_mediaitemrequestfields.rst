=============================================
opensocial.DataRequest.MediaItemRequestFields
=============================================

.. js:class:: opensocial.DataRequest.MediaItemRequestFields

:js:func:`opensocial.DataRequest.newFetchMediaItemsRequest` メソッドで使用するパラメータです。

opensocial.DataRequest.MediaItemRequestFields.FIRST
===================================================

.. js:data:: opensocial.DataRequest.MediaItemRequestFields.FIRST

MediaItem を複数ページにわたって取得する場合に、何番目のアイテムから取得するかを指定します。

opensocial.DataRequest.MediaItemRequestFields.MAX
=================================================

.. js:data:: opensocial.DataRequest.MediaItemRequestFields.MAX

一度に取得する MediaItem の件数を指定します。デフォルトでは20件です。

このパラメータで100以上を指定しても無視されます。この上限はSNSの管理者が変更可能です。

