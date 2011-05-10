.. _restful_albums:

=======================================
アルバム情報の取得 (Albums, MediaItems)
=======================================

opOpenSocialPluginでは、opAlbumPluginと連動してアルバムの情報を取得することができます。opAlbumPluginが導入されていない場合はこの機能は利用できません。

対応URI Fragment
================

::

  GET /albums/{guid}/{selector}
  GET /mediaitems/{guid}/{selector}/{albumId}

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

