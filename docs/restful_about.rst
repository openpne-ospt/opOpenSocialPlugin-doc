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

.. _rest_common_params:

共通のパラメータ
================

================================= =================================================================================================================================
count={count}                     1 ページあたりの取得件数。この上限は管理画面から設定可能です (デフォルトでは 100 件)。
filterBy={fieldname}              **実装されていません** 取得するデータの絞り込みに使用するフィールド
filterOp={operation}              **実装されていません** 取得するデータの絞り込み方法
filterValue={value}               **実装されていません** 取得するデータの絞り込みに使用する値
format={format}                   取得するデータの出力方式 (atom, json, xml のいずれか)。指定されなかった場合は json で出力されます
fields={-join|,|field}            取得するフィールドをカンマ区切りで指定したリスト。 ``@all`` は使用できません
networkDistance={networkDistance} **実装されていません** ``@friends`` などに含めるフレンドの距離 (友達の友達など)
sortBy={fieldname}                **実装されていません** 取得するデータの並べ替えに使用するフィールド
sortOrder={order}                 **実装されていません** 取得するデータの並べ替えの順序 (``ascending`` または ``descending``)。指定されなかった場合は昇順になります
startIndex={startIndex}           ページの開始位置
updatedSince={xsdDateTime}        **実装されていません** 指定した日付以降に更新されたデータのみを取得する
================================= =================================================================================================================================

