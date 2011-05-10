.. _restful_people:

===========================
メンバー情報の取得 (People)
===========================

URI Fragment
============

================================= ======================================================================================
``GET /people/{guid}/@all``       **実装されていません** {guid} に関連するすべてのメンバー
``GET /people/{guid}/@friends``   {guid} のすべてのフレンド
``GET /people/{guid}/{groupid}``  **実装されていません** {guid} に関連し、{groupid} のグループに含まれるすべてのメンバー
``GET /people/{guid}/@all/{pid}`` {guid} から見た {pid} のプロフィール情報
``GET /people/{guid}/@self``      {guid} のプロフィール情報
``GET /people/@me/@self``         アプリを実行中の自分自身のプロフィール情報
``GET /people/@supportedFields``  **実装されていません** People オブジェクトでサポートされているフィールドの一覧
================================= ======================================================================================

*{guid}* はメンバーIDか、 @me を指定することができます。
  GET http://sns.example.com/api.php/social/rest/people/\ *{guid}*\ /\ *{selector}*

例1
---

GET http://sns.example.com/api.php/social/rest/people/@me/@self ::

  {
    "entry": {
    "isOwner":true,
    "isViewer":true,
    "hasApp":true,
    "id":"1",
    "displayName": "OpenPNE\u541b",
    "thumbnailUrl":"http:\/\/sns.example.com\/cache\/img\/jpg\/w_h\/m_1_70481ff86b46bdb146bc78781a4c2a2d9a1581f6_jpg.jpg",
    "profileUrl":"http:\/\/sns.example.com\/member\/1"
    }
  }

例2
---

GET http://sns.example.com/api.php/social/rest/people/@me/@friends ::

  {
    "entry": [
      {
        "displayName": "Alice",
        "hasApp": false,
        "id": "2",
        "isOwner": false,
        "isViewer": false,
        "profileUrl": "http://sns.localhost/sqlite/member/2",
        "thumbnailUrl": ""
      },
      {
        "displayName": "Bob",
        "hasApp": false,
        "id": "3",
        "isOwner": false,
        "isViewer": false,
        "profileUrl": "http://sns.localhost/sqlite/member/3",
        "thumbnailUrl": ""
      },
      {
        "displayName": "Carol",
        "hasApp": false,
        "id": "4",
        "isOwner": false,
        "isViewer": false,
        "profileUrl": "http://sns.localhost/sqlite/member/4",
        "thumbnailUrl": ""
      }
    ],
    "itemsPerPage": 10,
    "startIndex": 0,
    "totalResults": 3
  }

取得可能フィールド
==================

id
  メンバーID
isOwner
  アプリ所有者であればtrue
isViewer
  閲覧者であればtrue
hasApp
  アプリを所有していればtrue
displayName
  表示名(ニックネーム)
thumbnailUrl
  プロフィール画像URL
profileUrl
  プロフィールURL

オプション
----------

上記のフィールド以外の情報を取得する場合は fields パラメータにフィールド名をカンマ区切りで指定します。このパラメータで指定できるフィールドは以下の通りです。

aboutMe
  自己紹介
addresses
  住所 (県名)
age
  年齢

  非公開に設定されている場合は空の文字列が入ります
birthday
  誕生日

  (例) ``"1990-01-01"``, ``"0000-05-01"`` (年齢非公開の場合)
languagesSpoken
  言語
gender
  性別

  (例) ``"male"``, ``"female"``, ``""`` (性別非公開の場合)

これらのオプションは、OpenPNE3.4 + opOpenSocialPlugin1.2.x のセットアップ直後に利用可能な項目です。

