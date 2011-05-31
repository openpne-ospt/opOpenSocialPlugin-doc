==============
osapi.people.*
==============

osapi.people.get()
==================

::

  osapi.people.get({
    userId: "@me",
    groupId: "@self",
    fields: [],
    count: 20,
    startIndex: 0,
    startPage: 0
  })

メンバーの情報を取得します。デフォルトでは VIEWER 自身の情報が取得されます。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでメンバー情報の取得は **行われません** 。取得方法は :ref:`osapi.Request_single` を参照して下さい。

パラメータ
----------

userId (String または Array.<String>)
  ユーザIDまたはユーザIDの配列。 ``@me`` を指定するとVIEWERのIDを指定したことと同じ意味になります。デフォルトは ``@me`` です。
groupId (String)
  取得するグループの種別。単にuserIdで指定したユーザのみを取得する場合は ``@self`` 、userIdで指定したユーザの友人 (本人は含まない) を取得する場合は ``@friends`` を指定します。デフォルトは ``@self`` です。
fields (Array.<String>)
  取得するフィールドを列挙した配列。取得可能なフィールドは :ref:`People API の取得可能フィールド<people_api_fields>` と同じで、 ``id``, ``isOwner``, ``isViewer``, ``hasApp``, ``displayName``, ``thumbnailUrl``, ``profileUrl`` 以外のフィールドを取得する場合のみこのパラメータを使用します。
count (int)
  一度に取得する人数の上限。デフォルトではcountに 100 以上を指定しても無視されます (この上限はSNS管理人が変更可能)。
startIndex (int)
  取得するデータの位置 (0 番目から開始) を指定します。例えば、1回目で20人のフレンドを取得して2回目で続きの20件を取得する、という場合はstartIndexを20ずつ増やして繰り返し取得します。
startPage (int)
  **実装されていません** 取得するページ位置を指定します。

osapi.people.getViewer()
========================

::

  osapi.people.getViewer({
    fields: []
  })

VIEWER の情報を取得します。このメソッドは ``osapi.people.get({userId: '@viewer', groupId: '@self'})`` の短縮形です。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでメンバー情報の取得は **行われません** 。取得方法は :ref:`osapi.Request_single` を参照して下さい。

osapi.people.getViewerFriends()
===============================

::

  osapi.people.getViewerFriends({
    fields: [],
    count: 20,
    startIndex: 0,
    startPage: 0
  })

VIEWER の友人の情報を取得します。このメソッドは ``osapi.people.get({userId: '@viewer', groupId: '@friends'})`` の短縮形です。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでメンバー情報の取得は **行われません** 。取得方法は :ref:`osapi.Request_single` を参照して下さい。

osapi.people.getOwner()
=======================

::

  osapi.people.getOwner({
    fields: []
  })

OWNER の情報を取得します。このメソッドは ``osapi.people.get({userId: '@owner', groupId: '@self'})`` の短縮形です。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでメンバー情報の取得は **行われません** 。取得方法は :ref:`osapi.Request_single` を参照して下さい。

osapi.people.getOwnerFriends()
==============================

::

  osapi.people.getOwnerFriends({
    fields: [],
    count: 20,
    startIndex: 0,
    startPage: 0
  })

OWNER の友人の情報を取得します。このメソッドは ``osapi.people.get({userId: '@owner', groupId: '@friends'})`` の短縮形です。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでメンバー情報の取得は **行われません** 。取得方法は :ref:`osapi.Request_single` を参照して下さい。

