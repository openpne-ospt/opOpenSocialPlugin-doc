=================================
opensocial.DataRequest.FilterType
=================================

.. js:class:: opensocial.DataRequest.FilterType

:js:func:`opensocial.DataRequest.newFetchPeopleRequest` メソッドのパラメータに :js:data:`opensocial.DataRequest.PeopleRequestFields.FILTER` を使用する際に指定するフィルタの種類です。

opensocial.DataRequest.FilterType.ALL
=====================================

.. js:data:: opensocial.DataRequest.FilterType.ALL

絞り込みを行わずにすべてのメンバーを取得します。

opensocial.DataRequest.FilterType.HAS_APP
=========================================

.. js:data:: opensocial.DataRequest.FilterType.HAS_APP

同じアプリを所有しているメンバーのみを取得します。

opensocial.DataRequest.FilterType.IS_FRIENDS_WITH
=================================================

.. js:data:: opensocial.DataRequest.FilterType.IS_FRIENDS_WITH

**実装されていません** オプションにより指定されたメンバーのフレンドのみを取得します。

このフィルタで使用するメンバーは :js:data:`opensocial.DataRequest.PeopleRequestFields.FILTER_OPTIONS` で :js:class:`opensocial.IdSpec` を使用して指定して下さい。

opensocial.DataRequest.FilterType.TOP_FRIENDS
=============================================

.. js:data:: opensocial.DataRequest.FilterType.TOP_FRIENDS

**実装されていません** メンバーの *親友* のみを取得します。このフィルタの定義は実装するSNSによって異なります。

