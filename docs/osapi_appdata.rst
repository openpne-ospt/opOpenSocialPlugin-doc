===============
osapi.appdata.*
===============

osapi.appdata.update()
======================

::

  osapi.appdata.update({
    userId: "@me",
    groupId: "@self",
    appId: "@app",
    data: {}
  })

アプリで使用するデータを保存します。保存したデータは同じアプリを所有するメンバー同士で共有することも可能です。 ``data`` には Map.<String, String> の形式で保存するデータを指定できます。

osapi.appdata.get()
===================

::

  osapi.appdata.get({
    userId: "@me",
    groupId: "@self",
    appId: "@app",
    keys: []
  })

アプリで保存したデータを取得します。 ``keys`` に保存したデータのキーを列挙することで取得するキーを限定することができます。

osapi.appdata.delete()
======================

::

  osapi.appdata.delete({
    userId: "@me",
    groupId: "@self",
    appId: "@app",
    keys: []
  })

アプリで保存したキーを削除します。 ``keys`` に削除するデータのキーを指定して下さい。

取得されるデータの例
====================

::

  {
    "1": {
      "foo": "hogehoge",
      "bar": "hogehogehoge"
    },
    "2": {
      "foo": "aaaa"
    }
  }

キーの "1" や "2" はメンバーIDです。
groupId に @friends を指定した場合はこのように複数人のデータが一度に取得されます。

使用例
======

アプリからデータを保存する例:

.. code-block:: javascript

  var params = {
    data: {
      foo: "aaa",
      bar: "bbb"
    }
  };
  osapi.appdata.update(params).execute(function (data) {
    if (data.error) {
      // 保存に失敗した場合の処理
      return;
    }

    // 保存に成功した後の処理
  });

保存したデータを読み出す例:

.. code-block:: javascript

  osapi.appdata.get({keys: ["foo"]}).execute(function (data) {
    if (data.error) {
      // 取得に失敗した場合の処理
    }

    for (var member_id in data) {
      var appdata = data[member_id];

      // 取得したデータに対する処理
      // appdata['foo'] のように読み出す。
    }
  });

他のメンバーのデータを読み出す場合は、そのメンバーが VIEWER のフレンドかつアプリを所有している必要があります。

保存したデータを削除する例:

.. code-block:: javascript

  osapi.appdata.delete({keys: ["bar"]}).execute(function (data) {
    if (data.error) {
      // 削除に失敗した場合の処理
      return;
    }

    // 削除に成功した後の処理
  });

keys を省略すると、保存されている全てのデータが削除されます。
