======================
opensocial.DataRequest
======================

.. js:class:: opensocial.DataRequest

メンバーのプロフィールやアクティビティなどの情報をSNSから取得するために使用します。
DataRequest オブジェクトの生成には :js:func:`opensocial.newDataRequest()` メソッドを使用して下さい。

これから新しくアプリを作成しようと考えている場合は、プロフィール等の取得に :doc:`OSAPI </docs/osapi_about>` の使用を検討してください。
OpenSocial v1.0 以降では DataRequest クラスを含む多くのクラス・メソッドが Deprecated とされています。

add()
=====

.. js:function:: opensocial.DataRequest.add(request, opt_key)

  :param Object request: 実行するリクエスト
  :param String opt_key: リクエストの結果を取得するために使用するキー

DataRequest オブジェクトで実行するリクエストを追加します。これによってリクエストを複数まとめて実行することが可能です。 ``opt_key`` は各リクエストの結果を取得するためのキーとして使用します。

newCreateAlbumRequest()
=======================

.. js:function:: opensocial.DataRequest.newCreateAlbumRequest(An, album)

  :param opensocial.IdSpec An: アルバムを作成するメンバーまたはグループ
  :param opensocial.Album album: 作成するアルバム
  :returns: リクエストオブジェクト

**実装されていません** 新規にアルバムを作成します。

newCreateMediaItemRequest()
===========================

.. js:function:: opensocial.DataRequest.newCreateMediaItemRequest(An, albumId, mediaItem)

  :param opensocial.IdSpec An: アルバムを所有するメンバーまたはグループ
  :param String albumId: 追加先のアルバム
  :param opensocial.MediaItem mediaItem: 追加するアイテム
  :returns: リクエストオブジェクト

**実装されていません** アルバムにアイテムを追加します。

newDeleteAlbumRequest()
=======================

.. js:function:: opensocial.DataRequest.newDeleteAlbumRequest(An, albumId)

  :param opensocial.IdSpec An: アルバムを所有するメンバーまたはグループ
  :param String albumId: 削除するアルバム
  :returns: リクエストオブジェクト

**実装されていません** アルバムを削除します。

newFetchActivitiesRequest()
===========================

.. js:function:: opensocial.DataRequest.newFetchActivitiesRequest(idSpec, opt_params)

  :param opensocial.IdSpec idSpec: アクティビティを取得する対象
  :param Map.<opensocial.DataRequest.ActivityRequestFields|Object> opt_params: アクティビティ取得のためのオプション
  :returns: リクエストオブジェクト

アクティビティを取得します。

newFetchAlbumsRequest()
=======================

.. js:function:: opensocial.DataRequest.newFetchAlbumsRequest(An, opt_params)

  :param opensocial.IdSpec An: 取得するアルバムの所有者
  :param Map.<String|String> opt_params: アルバム取得のためのオプション
  :returns: リクエストオブジェクト

アルバムを取得します。

newFetchMediaItemsRequest()
===========================

.. js:function:: opensocial.DataRequest.newFetchMediaItemsRequest(An, albumId, opt_params)

  :param opensocial.IdSpec An: 取得する MediaItem の所有者
  :param String albumId: 取得する MediaItem のアルバムID
  :param Map.<String|String> opt_params: MediaItem 取得のためのオプション
  :returns: リクエストオブジェクト

アルバム内の MediaItem を取得します。

newFetchPeopleRequest()
=======================

.. js:function:: opensocial.DataRequest.newFetchPeopleRequest(idSpec, opt_params)

  :param opensocial.IdSpec idSpec: 取得するメンバー
  :param Map.<opensocial.DataRequest.PeopleRequestFields|Object> opt_params: 取得時のオプション
  :returns: リクエストオブジェクト

.. note:: この処理は :doc:`/docs/osapi_people` で置き換え可能です。

メンバー情報の一覧を取得します。

newFetchPersonAppDataRequest()
==============================

.. js:function:: opensocial.DataRequest.newFetchPersonAppDataRequest(idSpec, keys, opt_params)

  :param opensocial.IdSpec idSpec: 取得する対象となるメンバー
  :param key: 取得するデータのキー
  :type key: Array.<String> | String
  :param Map.<opensocial.DataRequest.DataRequestFields|Object> opt_params: 取得時のオプション
  :returns: リクエストオブジェクト

.. note:: この処理は :doc:`/docs/osapi_appdata` で置き換え可能です。

アプリの保存しているデータを取得します。

newFetchPersonRequest()
=======================

.. js:function:: opensocial.DataRequest.newFetchPersonRequest(id, opt_params)

  :param String id: 取得するメンバーのID
  :param Map.<opensocial.DataRequest.PeopleRequestFields|Object> opt_params: 取得時のオプション
  :returns: リクエストオブジェクト

.. note:: この処理は :doc:`/docs/osapi_people` で置き換え可能です。

メンバー情報を取得します。

newRemovePersonAppDataRequest()
===============================

.. js:function:: opensocial.DataRequest.newRemovePersonAppDataRequest(keys)

  :param keys: 削除するデータのキー
  :type keys: Array.<String> | String
  :returns: リクエストオブジェクト

.. note:: この処理は :doc:`/docs/osapi_appdata` で置き換え可能です。

アプリの保存しているデータを削除します。

newUpdateAlbumRequest()
=======================

.. js:function:: opensocial.DataRequest.newUpdateAlbumRequest(An, albumId, fields)

  :param opensocial.IdSpec An: アルバムの所有者
  :param String albumId: アルバムID
  :param Map<opensocial.Album.Field|object> fields: 更新するフィールドと値の組
  :returns: リクエストオブジェクト

**実装されていません** アルバムの情報を更新します。

newUpdateMediaItemRequest()
===========================

.. js:function:: opensocial.DataRequest.newUpdateMediaItemRequest(An, albumId, mediaItemId, fields)

  :param opensocial.IdSpec An: MediaItem の所有者
  :param String albumId: アルバムID
  :param String mediaItemId: MediaItem のID
  :param Map<opensocial.MediaItem.Field|object> fields: 更新するフィールドと値の組
  :returns: リクエストオブジェクト

**実装されていません** アルバムに含まれる MediaItem の情報を更新します。

newUpdatePersonAppDataRequest()
===============================

.. js:function:: opensocial.DataRequest.newUpdatePersonAppDataRequest(key, value)

  :param String key: 更新するデータのキー
  :param Object value: 更新後のデータ
  :returns: リクエストオブジェクト

.. note:: この処理は :doc:`/docs/osapi_appdata` で置き換え可能です。

アプリの保存しているデータを更新します。

send()
======

.. js:function:: opensocial.DataRequest.send(opt_callback)

  :param Function opt_callback: コールバック

:js:func:`~opensocial.DataRequest.add()` メソッドにより追加されたリクエストを実行し、 ``opt_callback`` に指定されたコールバック関数に結果を渡します。

