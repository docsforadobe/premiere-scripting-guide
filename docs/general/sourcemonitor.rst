.. highlight:: javascript

.. _SourceMonitor:

SourceMonitor object
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

.. _sourceMonitor.closeAllClips:

SourceMonitor.closeAllClips()
*********************************************

``app.sourceMonitor.closeAllClips()``

**Description**

Closes all clips in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _sourceMonitor.closeClip:

SourceMonitor.closeClip()
*********************************************

``app.sourceMonitor.closeClip()``

**Description**

Closes the front-most clip in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _sourceMonitor.getPosition:

SourceMonitor.getPosition()
*********************************************

``app.sourceMonitor.getPosition()``

**Description**

Retrieves the position of the Source monitor's current time indicator.

**Parameters**

None.

**Returns**

Returns a :ref:`time` containing the position of the Source monitor's current time indicator. 

----

.. _sourceMonitor.openFilePath:

SourceMonitor.openFilePath()
*********************************************

``app.sourceMonitor.openFilePath(path)``

**Description**

Open a file in the Source monitor.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``path``          ``String``   A path to the file to open.
================  ===========  =======================

**Returns**

Returns 0 if successful.

----

.. _sourceMonitor.openProjectItem:

SourceMonitor.openProjectItem()
*********************************************

``app.sourceMonitor.openProjectItem(projectItem)``

**Description**

Open a project item in the Source monitor.

**Parameters**

================  ==================  =======================
Argument          Type                Description
================  ==================  =======================
``projectItem``   :ref:`projectItem`  A project item to open.
================  ==================  =======================

**Returns**

Returns 0 if successful.

----

.. _sourceMonitor.play:

SourceMonitor.play()
*********************************************

``app.sourceMonitor.play(playbackSpeed)``

**Description**

Begins playing back the Source monitor, at the specified playback speed.

**Parameters**

==================  ===========  =======================
Argument            Type         Description
==================  ===========  =======================
``playbackSpeed``   ``Float``    The playback speed.
==================  ===========  =======================

**Returns**

Returns 0 if successful.
