.. highlight:: javascript

.. _track:

Track object
===================

``Track``

**Description**

The **Track** object represents a video or audio track, within a :ref:`sequence`.

----

==========
Attributes
==========

.. _track.clips:

clips
*********************************************

``track.clips``

**Description**

An array of :ref:`Track item <trackItem>` objects, contained within the track, in temporal order.

**Type**

Array; read-only.

----

.. _track.id:

id
*********************************************

``track.id``

**Description**

This is the ordinal assigned to the track, upon creation.

**Type**

Integer, read-only.

----

.. _track.mediaType:

mediaType
*********************************************

``track.mediaType``

**Description**

The type of media, contained in this track.

**Type**

String, read-only; valid values are ``Audio`` and ``Video``.

----

.. _track.name:

name
*********************************************

``track.name``

**Description**

The name of the track.

**Type**

String; read-only.

----

.. _track.transitions:

transitions
*********************************************

``track.transitions``

**Description**

An array of transitions objects, contained within the track, in temporal order.

**Type**

Array; read-only.

----

=======
Methods
=======

.. _track.insertClip:

insertClip()
*********************************************

``track.insertClip(srcProjectItem, time)``

**Description**

Adds a 'clip' (media segment from a :ref:`projectItem`) to the track, at the specified time. Media will be inserted, at that time.

**Parameters**

A :ref:`projectItem` from which to get media, and the time at which to add it, in Ticks.

**Returns**

None.

----

.. _track.isMuted:

isMuted()
*********************************************

``track.isMuted()``

**Description**

Retrieves the current mute state, of the track.

**Parameters**

None.

**Returns**

Returns **true** if track is currently muted; **false** if not.

----

.. _track.overwriteClip:

overwriteClip()
*********************************************

``track.overwriteClip(srcProjectItem, time)``

**Description**

Adds a 'clip' (media segment from a :ref:`projectItem`) to the track, at the specified time. This will overwrite any existing media, at that time.

**Parameters**

A :ref:`projectItem` from which to get media, and the time at which to add it, in Ticks.

**Returns**

Returns ``true``.

----

.. _track.setMute:

setMute()
*********************************************

``track.setMute(isMuted)``

**Description**

Sets the mute state, of the track.

**Parameters**

Integer; if **1**, mute the track. If ``isMuted`` is **0**, the track will be unmuted.

**Returns**

Returns 0 if successful.
