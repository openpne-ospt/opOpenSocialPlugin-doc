===================
軽量 JavaScript API
===================

OSAPI は SNS の情報 (メンバー情報、アクティビティなど) や外部のコンテンツを取得するために使用する JavaScript API です。

この API は、メンバーのフレンドと連動する機能やアプリ上で起きたイベントをアクティビティに投稿するといった機能を実現するために、アプリ開発者が自由に使うことができます。
API を活用することで SNS と連動したさまざまなアプリを作成することができ、アプリによる表現の幅がより一層広がります。

OSAPI を利用するためには、Gadget XML の ModulePrefs 以下に

::

  <Require feature="osapi" />

を追加する必要があります。

旧来の JavaScirpt API との比較
==============================

OSAPI では旧来の JavaScript API よりも簡単で簡潔に呼び出すことができるようになっています。

例として、VIEWER のフレンドを取得するコードを OSAPI で置き換えます。

.. code-block:: javascript

  var idSpecParams = {};
  idSpecParams[opensocial.IdSpec.Field.USER_ID] = opensocial.IdSpec.PersonId.VIEWER;
  idSpecParams[opensocial.IdSpec.Field.GROUP_ID] = opensocial.IdSpec.GroupId.FRIENDS;
  var idSpec = opensocial.newIdSpec(idSpecParams);
  var req = opensocial.newDataRequest();
  req.add(req.newFetchPeopleRequest(idSpec), "friends");
  req.send(function (data) {
    if (data.hadError()) return;

    var list = document.getElementById('friendList');
    var items = '';
    var friends = data.get('friends').getData();
    friends.each(function (friend) {
      items += '<li>' + friend.getDisplayName() + '</li>\n';
    });
    list.innerHTML = items;
  });

このコードは下記のように置き換え可能です。どちらも全く同じ出力結果となります。

.. code-block:: javascript

  osapi.people.getViewerFriends().execute(function (data) {
    if (data.error) return;

    var list = document.getElementById('friendList');
    var items = '';
    var friends = data.list;
    for (var i = 0; i < friends.length; i++) {
      items += '<li>' + friends[i].displayName + '</li>\n';
    }
    list.innerHTML = items;
  });

