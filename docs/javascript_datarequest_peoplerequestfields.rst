==========================================
opensocial.DataRequest.PeopleRequestFields
==========================================

.. js:class:: opensocial.DataRequest.PeopleRequestFields

:js:func:`opensocial.DataRequest.newFetchPeopleRequest` メソッドや :js:func:`opensocial.DataRequest.newFetchPersonRequest` メソッドで使用するパラメータです。

opensocial.DataRequest.PeopleRequestFields.APP_DATA
===================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.APP_DATA

**実装されていません** メンバー情報とともに指定されたキーの AppData を取得します。

opensocial.DataRequest.PeopleRequestFields.ESCAPE_TYPE
======================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.ESCAPE_TYPE

取得したデータのエスケープ方法を指定します。 :js:class:`opensocial.EscapeType` で定義された値を指定して下さい。

デフォルトでは :js:data:`~opensocial.EscapeType.HTML_ESCAPE` です。

opensocial.DataRequest.PeopleRequestFields.FILTER
=================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.FILTER

取得するメンバーを絞り込むためのフィルターを指定します。使用できるフィルターは :js:class:`opensocial.DataRequest.FilterType` を参照して下さい。

opensocial.DataRequest.PeopleRequestFields.FILTER_OPTIONS
=========================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.FILTER_OPTIONS

:js:data:`~opensocial.DataRequest.PeopleRequestFields.FILTER` で指定されたフィルターで使用するオプション項目。フィルターにより使用できるオプションの種類が異なります。

opensocial.DataRequest.PeopleRequestFields.FIRST
================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.FIRST

メンバー情報を複数ページにわたって取得する場合に、何番目のメンバーから取得するかを指定します。

opensocial.DataRequest.PeopleRequestFields.MAX
==============================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.MAX

一度に取得するメンバー情報の件数を指定します。デフォルトでは20件です。

このパラメータで100以上を指定しても無視されます。この上限はSNSの管理者が変更可能です。

opensocial.DataRequest.PeopleRequestFields.PROFILE_DETAILS
==========================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.PROFILE_DETAILS

取得するプロフィール情報を指定します。指定できるフィールドは :js:class:`opensocial.Person.Field` を参照して下さい。
また、SNS でサポートされているプロフィール項目を調べる場合は :js:func:`opensocial.Environment.supportsField` メソッドを使用して下さい。

opensocial.DataRequest.PeopleRequestFields.SORT_ORDER
=====================================================

.. js:data:: opensocial.DataRequest.PeopleRequestFields.SORT_ORDER

**実装されていません** メンバー情報の並び替え順を指定します。指定できる並び替え方法は :js:class:`opensocial.DataRequest.SortOrder` を参照して下さい。

