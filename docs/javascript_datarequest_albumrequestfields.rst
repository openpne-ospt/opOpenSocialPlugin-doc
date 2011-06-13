=========================================
opensocial.DataRequest.AlbumRequestFields
=========================================

.. js:class:: opensocial.DataRequest.AlbumRequestFields

:js:func:`opensocial.DataRequest.newFetchAlbumsRequest` メソッドで使用されるパラメータです。

opensocial.DataRequest.AlbumRequestFields.FIRST
===============================================

.. js:data:: opensocial.DataRequest.AlbumRequestFields.FIRST

アルバムを複数ページにわたって取得する場合に、何番目のアルバムから取得するかを指定します。

opensocial.DataRequest.AlbumRequestFields.MAX
=============================================

.. js:data:: opensocial.DataRequest.AlbumRequestFields.MAX

一度に取得するアルバムの件数を指定します。デフォルトでは20件です。

このパラメータで100以上を指定しても無視されます。この上限はSNSの管理者が変更可能です。

