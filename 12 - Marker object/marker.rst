.. highlight:: javascript

.. _marker:

Marker object
==========================

``Marker``

**Description**

Both :ref:`Project items <projectItem>` and :ref:`sequences <sequence>` have associated **marker** objects, which represent their associated markers.

----

==========
Attributes
==========

.. _marker.comments:

Marker.comments
*********************************************

``marker.comments``

**Description**

The comments within the marker.

**Type**

String; read/write.

----

.. _marker.end:

Marker.end
*********************************************

``marker.end``

**Description**

A **Time** object containing the value of the ending of the marker.

**Type**

``Time``; read/write.

----

.. _marker.guid:

Marker.guid
*********************************************

``marker.guid``

**Description**

The unique identifier of the marker, created at time of instantiation.

**Type**

String; read-only.

----

.. _marker.name:

Marker.name
*********************************************

``marker.name``

**Description**

The name of the marker.

**Type**

String; read/write.

----

.. _marker.start:

Marker.start
*********************************************

``marker.start``

**Description**

A **Time** object containing the value of the beginning of the marker.

**Type**

``Time``; read/write.

----

.. _marker.type:

Marker.type
*********************************************

``marker.type``

**Description**

The type of marker; either "Comment", "Chapter", "Segmentation", or "WebLink". Note: Premiere Pro can import some marker types, which cannot be created from within Premiere Pro.

**Type**

String; read-only.

----

=======
Methods
=======

.. _marker.getColorByIndex:

Marker.getColorByIndex()
*********************************************

``marker.getColorByIndex(markerIndex)``

**Description**

Gets the marker color index. (added in 13.x)

**Parameters**

===================   ==============================================

``markerIndex``       Index of the marker to be read.

===================   ==============================================

**Returns**

Returns the color index as an ``Integer``.

----

.. _marker.getWebLinkFrameTarget:

Marker.getWebLinkFrameTarget()
*********************************************

``marker.getWebLinkFrameTarget()``

**Description**

Retrieves the frame target, from the marker's FrameTarget field.

**Parameters**

None.

**Returns**

Returns a ``String`` containing the frame target, or **0** if unsuccessful.

----

.. _marker.getWebLinkURL:

Marker.getWebLinkURL()
*********************************************

``marker.getWebLinkURL()``

**Description**

Retrieves the URL, from the marker's URL field.

**Parameters**

None.

**Returns**

Returns a ``String`` containing the URL, or **0** if unsuccessful.

----

.. _marker.setColorByIndex:

Marker.setColorByIndex()
*********************************************

``marker.setColorByIndex(colorIndex, markerIndex)``

**Description**

Sets the marker color by index. Color indexies listed below. (added in 13.x)

* 0 = Green
* 1 = Red
* 2 = Purple
* 3 = Orange
* 4 = Yellow
* 5 = White
* 6 = Blue
* 7 = Cyan

**Parameters**

===================   ==============================================

``colorIndex``        Index of the color to apply to the marker.

``markerIndex``        Index of the marker to be set.

===================   ==============================================

**Returns**

Returns ``undefined``.

----

.. _marker.setTypeAsChapter:

Marker.setTypeAsChapter()
*********************************************

``marker.setTypeAsChapter()``

**Description**

Sets the type of the marker to "Chapter".

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _marker.setTypeAsComment:

Marker.setTypeAsComment()
*********************************************

``marker.setTypeAsComment()``

**Description**

Sets the type of the marker to "Comment".

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _marker.setTypeAsSegmentation:

Marker.setTypeAsSegmentation()
*********************************************

``marker.setTypeAsSegmentation()``

**Description**

Sets the type of the marker to "Segmentation".

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _marker.setTypeAsWebLink:

Marker.setTypeAsWebLink()
*********************************************

``marker.setTypeAsWebLink()``

**Description**

Sets the type of the marker to "WebLink".

**Parameters**

None.

**Returns**

Returns **0** if successful.
