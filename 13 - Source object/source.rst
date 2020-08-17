.. highlight:: javascript

.. _Source:

Source object
==========================

``Source``

**Description**

The Source object represents Premiere Pro's Source monitor.

----

==========
Attributes
==========

None.

----

=======
Methods
=======

.. _source.closeAllClips:

closeAllClips
*********************************************

``source.closeAllClips()``

**Description**

Closes all clips in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _source.closeClip:

closeClip
*********************************************

``source.closeClip()``

**Description**

Closes the front-most clip in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _source.getPosition:

getPosition
*********************************************

``source.getPosition()``

**Description**

Retrieves the position of the Source monitor's current time indicator.

**Parameters**

None.

**Returns**

Returns a ``Time`` object containing the position of the Source monitor's current time indicator. 

----

.. _source.openFilePath:

openFilePath
*********************************************

``source.openFilePath(absolutePathToFile)``

**Description**

Open a file in the Source monitor.

**Parameters**

The absolute path to the file to open.

**Returns**

Returns 0 if successful.

----

.. _source.openProjectItem:

openProjectItem
*********************************************

``source.openProjectItem(projectItem)``

**Description**

Open a project item in the Source monitor.

**Parameters**

The ``projectItem`` to open.

**Returns**

Returns 0 if successful.

----

.. _source.play:

play
*********************************************

``source.play(playbackSpeed)``

**Description**

Begins playing back the Source monitor, at the specified playback speed.

**Parameters**

A ``float`` representing the playback speed.

**Returns**

Returns 0 if successful.
