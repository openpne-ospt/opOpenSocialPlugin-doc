============
osapi.http.*
============

osapi.http.head()
=================

::

  osapi.http.head({
    href: "",
    headers: {},
    format: "json",
    refreshInterval: 1209587,
    authz: "none",
    sign_viewer: true,
    sign_owner: true,
    oauth_service_name: "",
    oauth_token_name: "",
    oauth_request_token: "",
    oauth_request_token_secret: "",
    oauth_use_token: ""
  })

指定された URL へ HEAD リクエストを送信します。

パラメータ
----------

href
  リクエストの送信先URL
headers
  リクエストヘッダに追加する項目
format
  レスポンスのフォーマット。 ``json`` または ``text`` が指定できます。
refreshInterval
  レスポンスをキャッシュする最長期間
authz
  リクエスト時に必要な認証の種類。 ``none``, ``signed``, ``oauth`` が指定できます。
sign_viewer, sign_owner, oauth_service_name, oauth_token_name, oauth_request_token, oauth_request_token_secret, oauth_use_token
  **実装されていません**


osapi.http.get()
================

::

  osapi.http.get({
    href: "",
    headers: {},
    format: "json",
    refreshInterval: 1209587,
    authz: "none",
    sign_viewer: true,
    sign_owner: true,
    oauth_service_name: "",
    oauth_token_name: "",
    oauth_request_token: "",
    oauth_request_token_secret: "",
    oauth_use_token: ""
  })

指定された URL へ GET リクエストを送信します。

パラメータ
----------

href
  リクエストの送信先URL
headers
  リクエストヘッダに追加する項目
format
  レスポンスのフォーマット。 ``json`` または ``text`` が指定できます。
refreshInterval
  レスポンスをキャッシュする最長期間
authz
  リクエスト時に必要な認証の種類。 ``none``, ``signed``, ``oauth`` が指定できます。
sign_viewer, sign_owner, oauth_service_name, oauth_token_name, oauth_request_token, oauth_request_token_secret, oauth_use_token
  **実装されていません**

osapi.http.put()
=================

::

  osapi.http.put({
    href: "",
    headers: {},
    format: "json",
    refreshInterval: 1209587,
    authz: "none",
    sign_viewer: true,
    sign_owner: true,
    oauth_service_name: "",
    oauth_token_name: "",
    oauth_request_token: "",
    oauth_request_token_secret: "",
    oauth_use_token: ""
  })

指定された URL へ PUT リクエストを送信します。

パラメータ
----------

href
  リクエストの送信先URL
headers
  リクエストヘッダに追加する項目
format
  レスポンスのフォーマット。 ``json`` または ``text`` が指定できます。
refreshInterval
  レスポンスをキャッシュする最長期間
authz
  リクエスト時に必要な認証の種類。 ``none``, ``signed``, ``oauth`` が指定できます。
sign_viewer, sign_owner, oauth_service_name, oauth_token_name, oauth_request_token, oauth_request_token_secret, oauth_use_token
  **実装されていません**

osapi.http.post()
=================

::

  osapi.http.post({
    href: "",
    headers: {},
    format: "json",
    refreshInterval: 1209587,
    authz: "none",
    sign_viewer: true,
    sign_owner: true,
    oauth_service_name: "",
    oauth_token_name: "",
    oauth_request_token: "",
    oauth_request_token_secret: "",
    oauth_use_token: ""
  })

指定された URL へ POST リクエストを送信します。

パラメータ
----------

href
  リクエストの送信先URL
headers
  リクエストヘッダに追加する項目
format
  レスポンスのフォーマット。 ``json`` または ``text`` が指定できます。
refreshInterval
  レスポンスをキャッシュする最長期間
authz
  リクエスト時に必要な認証の種類。 ``none``, ``signed``, ``oauth`` が指定できます。
sign_viewer, sign_owner, oauth_service_name, oauth_token_name, oauth_request_token, oauth_request_token_secret, oauth_use_token
  **実装されていません**

osapi.http.delete()
===================

::

  osapi.http.delete({
    href: "",
    headers: {},
    format: "json",
    refreshInterval: 1209587,
    authz: "none",
    sign_viewer: true,
    sign_owner: true,
    oauth_service_name: "",
    oauth_token_name: "",
    oauth_request_token: "",
    oauth_request_token_secret: "",
    oauth_use_token: ""
  })

指定された URL へ DELETE リクエストを送信します。

パラメータ
----------

href
  リクエストの送信先URL
headers
  リクエストヘッダに追加する項目
format
  レスポンスのフォーマット。 ``json`` または ``text`` が指定できます。
refreshInterval
  レスポンスをキャッシュする最長期間
authz
  リクエスト時に必要な認証の種類。 ``none``, ``signed``, ``oauth`` が指定できます。
sign_viewer, sign_owner, oauth_service_name, oauth_token_name, oauth_request_token, oauth_request_token_secret, oauth_use_token
  **実装されていません**

使用例
======

TwitterのPublic Timeline最新20件を取得する例:

.. code-block:: javascript

  var api_url = 'https://api.twitter.com/1/statuses/public_timeline.json';
  osapi.http.get({href: api_url}).execute(function (data) {
    if (result.error) {
      alert("取得に失敗しました: " + result.error.message):
      return;
    }
    if (result.status == "200") {
      alert("取得に失敗しました: HTTPステータス " + result.status);
    }

    for (var i = 0; i < result.content.length; i++) {
      var tweet = result.content[i];
      // .....
    }
  });

