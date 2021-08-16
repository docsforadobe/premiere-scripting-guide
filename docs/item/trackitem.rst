.. _trackItem:

TrackItem object
===================

|   ``app.project.sequences[index].audioTracks[index].clips[index]``
|   ``app.project.sequences[index].videoTracks[index].clips[index]``

**Description**

The **trackItem** object represents an item on a video or audio track, within a :ref:`sequence`.

----

==========
Attributes
==========

TrackItem.components
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components``

**Description**

The components associated with this trackItem. This can include intrinsic transformations, as well as video and audio effects.

**Type**

:ref:`componentCollection`, read-only;

----

TrackItem.duration
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].duration``
|   ``app.project.sequences[index].videoTracks[index].clips[index].duration``

**Description**

The duration of the trackItem.

**Type**

:ref:`time`, read-only.

----

TrackItem.end
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].end``
|   ``app.project.sequences[index].videoTracks[index].clips[index].end``

**Description**

The ending time of the trackItem. Note: This may differ, from the trackItem's out point.

**Type**

:ref:`time`, read/write.

----

TrackItem.inPoint
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].inPoint``
|   ``app.project.sequences[index].videoTracks[index].clips[index].inPoint``

**Description**

The in point for media, in this trackItem.

**Type**

:ref:`time`, read/write.

----

TrackItem.matchName
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].matchName``
|   ``app.project.sequences[index].videoTracks[index].clips[index].matchName``

**Description**

*Add a description*

**Type**

String; read-only.

----

TrackItem.mediaType
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].mediaType``
|   ``app.project.sequences[index].videoTracks[index].clips[index].mediaType``

**Description**

The mediaType of media provided by this trackItem.

**Type**

String, either **Audio** or **Video**.

----

TrackItem.name
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].name``
|   ``app.project.sequences[index].videoTracks[index].clips[index].name``

**Description**

The name of the track item.

**Type**

String; read/write.

----

TrackItem.nodeId
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].nodeId``
|   ``app.project.sequences[index].videoTracks[index].clips[index].nodeId``

**Description**

*Add a description*

**Type**

String.

----

TrackItem.outPoint
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].outPoint``
|   ``app.project.sequences[index].videoTracks[index].clips[index].outPoint``

**Description**

The out point for media, in this trackItem.

**Type**

:ref:`time`, read/write.

----

TrackItem.projectItem
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].projectItem``
|   ``app.project.sequences[index].videoTracks[index].clips[index].projectItem``

**Description**

The :ref:`projectItem` from which the media is being drawn.

**Type**

A :ref:`projectItem`. 

----

TrackItem.start
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].start``
|   ``app.project.sequences[index].videoTracks[index].clips[index].start``

**Description**

The starting time of the trackItem. Note: This may differ, from the trackItem's in point.

**Type**

:ref:`time`, read/write.

----

TrackItem.type
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].type``
|   ``app.project.sequences[index].videoTracks[index].clips[index].type``

**Description**

The type of media provided by this trackItem.

**Type**

Number, **1** means video, **2** means audio.

----

=======
Methods
=======

TrackItem.getSpeed()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].getSpeed()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].getSpeed()``

**Description**

Returns the speed multiplier applied to the ``trackItem``.

**Parameters**

None.

**Returns**

Returns the speed multiplier applied to the ``trackItem``, as a ``float``. No speed adjustment = ``1``.

----

TrackItem.isAdjustmentLayer()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].isAdjustmentLayer()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].isAdjustmentLayer()``

**Description**

Returns wheter the ``trackItem`` is an adjustment layer.

**Parameters**

None.

**Returns**

Returns ``true`` if the trackitem is an adjustment layer; ``false`` if not.

----

TrackItem.isReversed()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].isReversed()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].isReversed()``

**Description**

Returns whether the trackItem is reversed.

**Parameters**

None.

**Returns**

Returns **1** if ``trackItem`` is reversed; **0** if not.

----

TrackItem.isSelected()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].isSelected()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].isSelected()``

**Description**

Retrieves the current selection state of the trackItem.

**Parameters**

None.

**Returns**

Returns ``true`` if trackItem is selected; ``false`` if not.

----

TrackItem.setSelected()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].setSelected(state, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].setSelected(state, updateUI)``

**Description**

Sets the selection state of the trackItem.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``state``         ``Integer``  If ``1``, the track item will be selected; if ``0``, it will be deselected.
``updateUI``      ``Integer``  If ``1``, the Premiere Pro UI will be updated after this function call is made.
================  ===========  =======================

**Returns**

Returns **0** if successful.


----

TrackItem.getMatchName()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].getMatchName()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].getMatchName()``

**Description**

Retrieves the match name for the trackItem.

**Parameters**

None.

**Returns**

Returns the match name as a **String** if successful.

----

TrackItem.remove()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].remove(inRipple, inAlignToVideo)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].remove(inRipple, inAlignToVideo)``

**Description**

Sets the selection state of the trackItem.

**Parameters**

==================  ============  =======================
Argument            Type          Description
==================  ============  =======================
``inRipple``         ``Boolean``  If ``1``, later track items will be moved earlier, to fill the gap; if ``0``, later track items will remain in place.
``inAlignToVideo``   ``Boolean``  If ``1``, Premiere Pro will align moved track items to the start of the nearest video frame.
==================  ============  =======================

**Returns**

Returns **0** if successful.

----

.. _trackItem.disabled:

TrackItem.disabled()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].disabled(newDisableState)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].disabled(newDisableState)``

**Description**

Sets the disabled state of the trackItem.

**Parameters**

===================  ============  =======================
Argument             Type          Description
===================  ============  =======================
``newDisableState``  ``Boolean``   If ``true``, this trackItem will be disabled; if ``false``, trackItem will be enabled.
===================  ============  =======================

**Returns**

Returns **0** if successful.

----

.. _trackitem.move:

TrackItem.move()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].move(newInPoint)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].move(newInPoint)``

**Description**

Moves the inPoint of the track item to a new time.

**Parameters**

===================  ============  =======================
Argument             Type          Description
===================  ============  =======================
``newInPoint``       ``Time``      The time to which to move the track item's in point.
===================  ============  =======================

**Returns**

Returns **0** if successful.
