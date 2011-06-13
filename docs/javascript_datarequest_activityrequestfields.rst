============================================
opensocial.DataRequest.ActivityRequestFields
============================================

.. js:class:: opensocial.DataRequest.ActivityRequestFields

:js:func:`opensocial.DataRequest.newFetchActivitiesRequest` メソッドで使用されるパラメータです。

opensocial.DataRequest.ActivityRequestFields.FIRST
==================================================

.. js:data:: opensocial.DataRequest.ActivityRequestFields.FIRST

アクティビティを複数ページにわたって取得する場合に、何番目のアクティビティから取得するかを指定します。

opensocial.DataRequest.ActivityRequestFields.MAX
=================================================

.. js:data:: opensocial.DataRequest.ActivityRequestFields.MAX

一度に取得するアクティビティの件数を指定します。デフォルトでは20件です。

このパラメータで100以上を指定しても無視されます。この上限はSNSの管理者が変更可能です。

