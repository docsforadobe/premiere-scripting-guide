.. highlight:: javascript

.. _trackItem:

Track Item object
===================

``Track Item``

**Description**

The **trackItem** object represents an item on a video or audio track, within a sequence.

==========
Attributes
==========

.. _trackItem.name:

name
*********************************************

``trackItem.name``

**Description**

The name of the track item.

**Type**

String; read/write.


----

.. _trackItem.duration:

duration
*********************************************

``trackItem.duration``

**Description**

The duration of the trackItem.

**Type**

Time object, read-only.

----

.. _trackItem.start:

start
*********************************************

``trackItem.start``

**Description**

The starting time of the trackItem. Note: This may differ, from the trackItem's in point.

**Type**

Time object, read/write.

----

.. _trackItem.end:

end
*********************************************

``trackItem.end``

**Description**

The ending time of the trackItem. Note: This may differ, from the trackItem's out point.

**Type**

Time object, read/write.


----

.. _trackItem.inPoint:

inPoint
*********************************************

``trackItem.inPoint``

**Description**

The in point for media, in this trackItem.

**Type**

Time object, read/write.


----

.. _trackItem.outPoint:

outPoint
*********************************************

``trackItem.outPoint``

**Description**

The out point for media, in this trackItem.

**Type**

Time object, read/write.



----

.. _trackItem.type:

type
*********************************************

``trackItem.type``

**Description**

The type of media provided by this trackItem.

**Type**

**1** means video, **2** means audio.

----

.. _trackItem.mediaType:

mediaType
*********************************************

``trackItem.mediaType``

**Description**

The mediaType of media provided by this trackItem.

**Type**

This will either be **"audio"** or **"video"**.


----

.. _trackItem.projectItem:

projectItem
*********************************************

``trackItem.projectItem``

**Description**

The projectItem from which the media is being drawn.

**Type**

A **projectItem**. 

----

.. _trackItem.components:

components
*********************************************

``trackItem.components``

**Description**

The components associated with this trackItem. This can include intrinsic transformations, as well as video and audio effects.

**Type**

An Array of components; read-only.



=======
Methods
=======


.. _trackItem.isSelected:

isSelected
*********************************************

``trackItem.isSelected()``

**Description**

Retrieves the current selection state of the trackItem.

**Parameters**

None.

**Returns**

Returns ``true`` if trackItem is selected; ``false`` if not.

----

.. _trackItem.setSelected:

setSelected
*********************************************

``trackItem.setSelected(selectionState, updateUI)``

**Description**

Sets the selection state of the trackItem.

**Parameters**

If selectionState is **1**, the trackItem will be selected; if **0**, it will be deselected. If updateUI is **1**, the Premiere Pro UI will be updated after this function call is made.

**Returns**

Returns **0** if successful.


----

.. _trackItem.isReversed:

isReversed
*********************************************

``trackItem.isReversed()``

**Description**

Returns whether the trackItem is reversed.

**Parameters**

None.

**Returns**

Returns **1** if ``trackItem`` is reversed; **0** if not.



----

.. _trackItem.getSpeed:

getSpeed
*********************************************

``trackItem.getSpeed()``

**Description**

Returns the speed multiplier applied to the ``trackItem``.

**Parameters**

None.

**Returns**

Returns the speed multiplier applied to the ``trackItem``, as a ``float``. No speed adjustment = 1.




----

.. _trackItem.isAdjustmentLayer:

isAdjustmentLayer
*********************************************

``trackItem.isAdjustmentLayer()``

**Description**

Returns wheter the ``trackItem`` is an adjustment layer.

**Parameters**

None.

**Returns**

Returns ``true`` if the trackitem is an adjustment layer; ``false`` if not.



