.. highlight:: javascript

.. _Source:

Source object
==========================

``app.sourceMonitor``

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

Source.closeAllClips()
*********************************************

``app.sourceMonitor.closeAllClips()``

**Description**

Closes all clips in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _source.closeClip:

Source.closeClip()
*********************************************

``app.sourceMonitor.closeClip()``

**Description**

Closes the front-most clip in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _source.getPosition:

Source.getPosition()
*********************************************

``app.sourceMonitor.getPosition()``

**Description**

Retrieves the position of the Source monitor's current time indicator.

**Parameters**

None.

**Returns**

Returns a ``Time`` object containing the position of the Source monitor's current time indicator. 

----

.. _source.openFilePath:

Source.openFilePath()
*********************************************

``app.sourceMonitor.openFilePath(absolutePathToFile)``

**Description**

Open a file in the Source monitor.

**Parameters**

The absolute path to the file to open.

**Returns**

Returns 0 if successful.

----

.. _source.openProjectItem:

Source.openProjectItem()
*********************************************

``app.sourceMonitor.openProjectItem(projectItem)``

**Description**

Open a project item in the Source monitor.

**Parameters**

The :ref:`projectItem` to open.

**Returns**

Returns 0 if successful.

----

.. _source.play:

Source.play()
*********************************************

``app.sourceMonitor.play(playbackSpeed)``

**Description**

Begins playing back the Source monitor, at the specified playback speed.

**Parameters**

A ``float`` representing the playback speed.

**Returns**

Returns 0 if successful.
