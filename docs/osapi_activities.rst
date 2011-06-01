==================
osapi.activities.*
==================

osapi.activities.get()
======================

::

  osapi.activities.get({
    userId: "@me",
    groupId: "@self",
    appId: "",
    activityIds: [],
    fields: [],
    count: 20,
    startIndex: 0,
    startPage: 0
  })

アクティビティの取得を行います。デフォルトでは VIEWER のアクティビティが取得されます。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでアクティビティの取得は **行われません** 。取得方法は :ref:`osapi.Request` を参照して下さい。

パラメータ
----------

userId (String または Array.<String>)
  ユーザIDまたはユーザIDの配列。 ``@me`` を指定するとVIEWERのIDを指定したことと同じ意味になります。デフォルトは ``@me`` です。
groupId (String)
  取得するグループの種別。単にuserIdで指定したユーザのみを取得する場合は ``@self`` 、userIdで指定したユーザの友人 (本人は含まない) を取得する場合は ``@friends`` を指定します。デフォルトは ``@self`` です。
appId (String)
  取得するアクティビティのアプリID。実行中のアプリID (``@app`` を指定しても同じ) のみ指定できます。
activityIds (Array.<String>)
  取得するアクティビティのIDの配列。
fields (Array.<String>)
  取得するフィールドを列挙した配列。アクティビティでは追加で指定できるフィールドはありません。
count (int)
  一度に取得する人数の上限。デフォルトではcountに 100 以上を指定しても無視されます (この上限はSNS管理人が変更可能)。
startIndex (int)
  取得するデータの位置 (0 番目から開始) を指定します。例えば、1回目で20件を取得して2回目で続きの20件を取得する、という場合はstartIndexを20ずつ増やして繰り返し取得します。
startPage (int)
  **実装されていません** 取得するページ位置を指定します。

osapi.activities.create()
=========================

::

  osapi.activities.create({
    userId: "@me",
    groupId: "@self",
    appId: "@app",
    activity: {
      "title": "",
      "url": "",
      "mediaItems": []
    }
  })

アクティビティの投稿を行います。

このメソッドを実行しただけでは ``osapi.Request`` オブジェクトが返るだけでアクティビティの投稿は **行われません** 。詳しくは :ref:`osapi.Request` を参照して下さい。

パラメータ
----------

title (String)
  投稿するアクティビティの内容。
url (String)
  アクティビティに設定するURL。アクティビティの閲覧時にリンクとして表示されます。このURLのドメインはSNSのドメインと同一である必要があります。
mediaItems (Array.<opensocial.MediaItem>)
  アクティビティに設定するメディア。画像のURLを指定するとアクティビティ閲覧時に指定された画像が表示されます。 ``{url: "http://example.com/image.png", mimeType: "image/png"}`` のように指定してください。

使用例
======

アクティビティの取得を行う例:

.. code-block:: javascript

  osapi.activities.get().execute(function (data) {
    if (data.error) {
      alert("取得に失敗しました");
      return;
    }
    var activities = data.list;
    for (var i = 0; i < activities.length; i++) {
      // ....
    }
  });

アクティビティの投稿を行う例:

.. code-block:: javascript

  var params = {
    activity: {
      title: "hello!",
      url: "http://sns.example.com/application/canvas/1",
      mediaItems: [
        {
          url: "http://example.com/image.png",
          mediaType: "image/png"
        }
      ]
    }
  };
  osapi.activities.create(params).execute(function (data) {
    if (data && data.error) {
      alert("投稿に失敗しました");
      return;
    }
  });

