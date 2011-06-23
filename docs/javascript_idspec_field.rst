=======================
opensocial.IdSpec.Field
=======================

.. js:class:: opensocial.IdSpec.Field

:js:class:`opensocial.IdSpec` で使用されるフィールドです。

opensocial.IdSpec.Field.GROUP_ID
================================

.. js:data:: opensocial.IdSpec.Field.GROUP_ID

対象とするグループの範囲。:js:class:`opensocial.IdSpec.GroupId` のフィールドが指定できます。
デフォルトは :js:data:`~opensocial.IdSpec.GroupId.SELF` です。

opensocial.IdSpec.Field.NETWORK_DISTANCE
========================================

.. js:data:: opensocial.IdSpec.Field.NETWORK_DISTANCE

**実装されていません** 取得する友人間の「距離」を指定します。1 であれば友人まで、2 であれば「友人の友人」までの範囲を取得します。

opensocial.IdSpec.Field.USER_ID
===============================

.. js:data:: opensocial.IdSpec.Field.USER_ID

対象となるメンバー。
メンバーID または :js:class:`opensocial.IdSpec.PersonId` のフィールド、またはそれらの配列が指定できます。

