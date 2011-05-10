.. _restful_albums:

=======================================
アルバム情報の取得 (Albums, MediaItems)
=======================================

opOpenSocialPluginでは、opAlbumPluginと連動してアルバムの情報を取得することができます。opAlbumPluginが導入されていない場合はこの機能は利用できません。

URI Fragment
============

Albums API
~~~~~~~~~~

======================================  ===============================================
``GET /albums/@me/@self``               アルバムの一覧を取得する
``POST /albums/@me/@self``              **実装されていません** 新しいアルバムを作成する
``GET /albums/@me/@self/{albumId}``     **実装されていません** {albumId} を取得する
``PUT /albums/@me/@self/{albumId}``     **実装されていません** {albumId} を更新する
``DELETE /albums/@me/@self/{albumId}``  **実装されていません** {albumId} を削除する
======================================  ===============================================

MediaItems API
~~~~~~~~~~~~~~

========================================================  ==========================================================================
``GET /mediaitems/@me/@self/{albumId}``                   {albumId} に含まれるメディアの一覧を取得する
``POST /mediaitems/@me/@self/{albumId}``                  **実装されていません** {albumId} に新しくメディアを追加する
``GET /mediaitems/@me/@self/{albumId}/{mediaItemId}``     **実装されていません** {albumId} に含まれる {mediaItemId} の内容を取得する
``PUT /mediaitems/@me/@self/{albumId}/{mediaItemId}``     **実装されていません** {albumId} に含まれる {mediaItemId} を更新する
``DELETE /mediaitems/@me/@self/{albumId}/{mediaItemId}``  **実装されていません** {albumId} に含まれる {mediaItemId} を削除する
========================================================  ==========================================================================

例
==

GET http://sns.example.com/api.php/social/rest/albums/@me/@self ::

  {
    "entry": [
      {
        "id":"1",
        "title":"album title",
        "description":"foo",
        "mediaItemCount":2,
        "ownerId":"1",
        "thumbnailUrl":"http:\/\/sns.example.com\/cache\/img\/jpg\/w180_h180\/d906f3049dfc809473603132dade9b8484a31887_gif.jpg",
        "mediaType":"IMAGE"
      }
    ],
    "startIndex":0,
    "totalResults":1,
    "itemsPerPage":20
  }

アルバム自体の情報の取得が可能です。

アルバムの内容を取得したい場合は、以下のようにします。

GET http://sns.example.com/api.php/social/rest/mediaitems/@me/@self/1 ::

  {
    "entry":  [
      {
        "albumId":"1",
        "created":"2009-11-30 22:57:00",
        "description":"foo",
        "fileSize":"0",
        "id":"1",
        "lastUpdated":"2009-11-30 22:57:00",
        "thumbnailUrl":"http:\/\/sns.example.com\/cache\/img\/jpg\/w180_h180\/a_1_7b0e61f64a2ee2ef183b05f1c9d8161f251d139a_jpg.jpg",
        "title":"title",
        "type":"IMAGE",
        "url":"http:\/\/sns.example.com\/cache\/img\/jpg\/w_h\/a_1_7b0e61f64a2ee2ef183b05f1c9d8161f251d139a_jpg.jpg"
      },
      {
        "albumId":"1",
        "created":"2009-11-30 22:57:00",
        "description":"bar",
        "fileSize":"0",
        "id":"2",
        "lastUpdated":"2009-11-30 22:57:00",
        "thumbnailUrl":"http:\/\/sns.example.com\/cache\/img\/jpg\/w180_h180\/a_1_7b0e61f64a2ee2ef183b05f1c9d8161f251d139a_jpg.jpg",
        "title":"title",
        "type":"IMAGE",
        "url":"http:\/\/sns.example.com\/cache\/img\/jpg\/w_h\/a_1_7b0e61f64a2ee2ef183b05f1c9d8161f251d139a_jpg.jpg"
      }
    ],
    "startIndex":0,
    "totalResults":1,
    "itemsPerPage":20
  }

注意事項
========

opAlbumPlugin がインストールされていない場合は対応しているURIの形式であっても Not implemented が返ります。

