.. highlight:: javascript

.. _track:

Track object
===================

|   ``app.project.sequences[index].audioTracks[index]``
|   ``app.project.sequences[index].videoTracks[index]``

#### Description

The **Track** object represents a video or audio track, within a :ref:`sequence`.

----

==========
Attributes
==========

.. _track.clips:

Track.clips
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips``
|   ``app.project.sequences[index].videoTracks[index].clips``

#### Description

An array of :ref:`Track item <trackItem>` objects, contained within the track, in temporal order.

#### Type

:ref:`trackItemCollection`, read-only;

----

.. _track.id:

Track.id
*********************************************

|   ``app.project.sequences[index].audioTracks[index].id``
|   ``app.project.sequences[index].videoTracks[index].id``

#### Description

This is the ordinal assigned to the track, upon creation.

#### Type

Integer, read-only.

----

.. _track.mediaType:

Track.mediaType
*********************************************

|   ``app.project.sequences[index].audioTracks[index].mediaType``
|   ``app.project.sequences[index].videoTracks[index].mediaType``

#### Description

The type of media, contained in this track.

#### Type

String, read-only; valid values are ``Audio`` and ``Video``.

----

.. _track.name:

Track.name
*********************************************

|   ``app.project.sequences[index].audioTracks[index].name``
|   ``app.project.sequences[index].videoTracks[index].name``

#### Description

The name of the track.

#### Type

String; read-only.

----

.. _track.transitions:

Track.transitions
*********************************************

|   ``app.project.sequences[index].audioTracks[index].transitions``
|   ``app.project.sequences[index].videoTracks[index].transitions``

#### Description

An array of transitions objects, contained within the track, in temporal order.

#### Type

:ref:`trackItemCollection`, read-only;

----

=======
Methods
=======

.. _track.insertClip:

Track.insertClip()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].insertClip(projectItem, time, vTrackIndex, aTrackIndex)``
|   ``app.project.sequences[index].videoTracks[index].insertClip(projectItem, time, vTrackIndex, aTrackIndex)``

#### Description

Adds a 'clip' (media segment from a :ref:`projectItem`) to the track, at the specified time. Media will be inserted, at that time.

#### Parameters

================  ===================  =======================
Argument          Type                 Description
================  ===================  =======================
``projectItem``   :ref:`projectItem`   A project item from which to get media.
``time``          `String`           The time at which to add project item, in **Ticks**.
``vTrackIndex``   ``int``              The (zero-based) track index, into which to insert video.
``aTrackIndex``   ``int``              The (zero-based) track index, into which to insert audio.
================  ===================  =======================

#### Returns

None.

----

.. _track.isMuted:

Track.isMuted()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].isMuted()``
|   ``app.project.sequences[index].videoTracks[index].isMuted()``

#### Description

Retrieves the current mute state, of the track.

#### Parameters

None.

#### Returns

Returns **true** if track is currently muted; **false** if not.

----

.. _track.overwriteClip:

Track.overwriteClip()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].overwriteClip(projectItem, time)``
|   ``app.project.sequences[index].videoTracks[index].overwriteClip(projectItem, time)``

#### Description

Adds a 'clip' (media segment from a :ref:`projectItem`) to the track, at the specified time. This will overwrite any existing media, at that time.

#### Parameters

================  ===================  =======================
Argument          Type                 Description
================  ===================  =======================
``projectItem``   :ref:`projectItem`   A project item from which to get media.
``time``          `String`           The time at which to add project item, in **Ticks**.
================  ===================  =======================

#### Returns

Returns ``true``.

----

.. _track.setMute:

Track.setMute()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].setMute(isMuted)``
|   ``app.project.sequences[index].videoTracks[index].setMute(isMuted)``

#### Description

Sets the mute state, of the track.

#### Parameters

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``isMuted``       `Integer`  If ``1``, mute the track. If ``0``, the track will be unmuted.
================  ===========  =======================

#### Returns

Returns 0 if successful.
