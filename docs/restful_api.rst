.. _restful_api:

===========
RESTful API
===========

マッシュアップサイト作成や、モバイルアプリ用のリソースアクセスの手段として OpenSocial RESTful API を利用するという手段があるでしょう。

この章ではOpenSocial RESTful APIについて解説します。

About RESTful API
=================

RESTful APIは `OpenSocial RESTful Protocol Specification v0.9`_ を基準にしています。

.. _`OpenSocial RESTful Protocol Specification v0.9`: http://www.opensocial.org/Technical-Resources/opensocial-spec-v09/REST-API.html

エンドポイント
==============

RESTful APIのエンドポイントは以下になります::

  http://sns.example.com/api.php/social/rest

OAuth
=====

APIへのアクセス認可にはOAuthを利用します。

OpenPNE3 + opOpenSocialPlugin でのOAuthコンシューマは以下の3種類が挙げられます。

* 利用者側で登録されたコンシューマ
* 管理者画面側で登録されたコンシューマ
* アプリ提供者が登録したコンシューマ (認可手段は2-legged OAuthのみ)

管理者側の認可によって発行されたアクセストークンを利用する場合は、どの利用者の情報を取得するのかを明示する必要があります。そのため、最終的にAPIにアクセスするときに *xoauth_requestor_id* でメンバーIDを指定する必要があります。

また、 `2-legged OAuth`_ を利用することができますが、利用者側で登録されたコンシューマであった場合、 *xoauth_requestor_id* は、その利用者自身のメンバーIDでなければいけません。

OpenPNE上のOAuth認可については、 http://sandbox.ebihara.dazai.pne.jp/oauth.ja.html を参照してください。

.. _`2-legged OAuth`: http://oauth.googlecode.com/svn/spec/ext/consumer_request/1.0/drafts/1/spec.html

レスポンスのフォーマット
========================

レスポンスの形式は、JSON・XML・ATOMに対応しています。それぞれリクエストのformatパラメータに、json, xml, atomを設定することにより形式を切り替えることができます。指定しない場合はJSONになります。

共通のパラメータ
================

.. まだ実際の動作の確認ができてない

