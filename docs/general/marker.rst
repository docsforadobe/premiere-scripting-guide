.. highlight:: javascript

.. _marker:

Marker object
==========================

|   ``app.project.activeSequence.markers.getFirstMarker()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker()``

**Description**

Both :ref:`Project items <projectItem>` and :ref:`sequences <sequence>` have associated **marker** objects, which represent their associated markers.

----

==========
Attributes
==========

.. _marker.comments:

Marker.comments
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().comments``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().comments``

**Description**

The comments within the marker.

**Type**

String; read/write.

----

.. _marker.end:

Marker.end
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().end``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().end``

**Description**

A :ref:`time` containing the value of the ending of the marker.

**Type**

:ref:`time`; read/write.

----

.. _marker.guid:

Marker.guid
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().guid``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().guid``

**Description**

The unique identifier of the marker, created at time of instantiation.

**Type**

String; read-only.

----

.. _marker.name:

Marker.name
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().name``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().name``

**Description**

The name of the marker.

**Type**

String; read/write.

----

.. _marker.start:

Marker.start
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().start``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().start``

**Description**

A :ref:`time` containing the value of the beginning of the marker.

**Type**

:ref:`time`; read/write.

----

.. _marker.type:

Marker.type
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().type``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().type``

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

|   ``app.project.activeSequence.markers.getFirstMarker().getColorByIndex(index)``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().getColorByIndex(index)``

.. note::
    This functionality was added in Adobe Premire Pro 13.x.

**Description**

Gets the marker color index.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``index``         ``Integer``  Index of the marker to be read.
================  ===========  =======================

**Returns**

Returns the color index as an ``Integer``.

----

.. _marker.getWebLinkFrameTarget:

Marker.getWebLinkFrameTarget()
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().getWebLinkFrameTarget()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkFrameTarget()``

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

|   ``app.project.activeSequence.markers.getFirstMarker().getWebLinkURL()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkURL()``

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

|   ``app.project.activeSequence.markers.getFirstMarker().setColorByIndex(colorIndex, markerIndex)``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setColorByIndex(colorIndex, markerIndex)``

.. note::
    This functionality was added in Adobe Premire Pro 13.x.

**Description**

Sets the marker color by index. Color indexies listed below.

* 0 = Green
* 1 = Red
* 2 = Purple
* 3 = Orange
* 4 = Yellow
* 5 = White
* 6 = Blue
* 7 = Cyan

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``colorIndex``    ``Integer``  Index of the color to apply to the marker.
``markerIndex``   ``Integer``  Index of the marker to be set.
================  ===========  =======================

**Returns**

Returns ``undefined``.

----

.. _marker.setTypeAsChapter:

Marker.setTypeAsChapter()
*********************************************

|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsChapter()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsChapter()``

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

|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsComment()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsComment()``

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

|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsSegmentation()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsSegmentation()``

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

|   ``app.project.activeSequence.markers.getFirstMarker().setTypeAsWebLink()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsWebLink()``

**Description**

Sets the type of the marker to "WebLink".

**Parameters**

None.

**Returns**

Returns **0** if successful.
