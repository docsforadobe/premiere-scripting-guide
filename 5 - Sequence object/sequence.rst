.. highlight:: javascript

.. _sequence:

Sequence object
===================

``Sequence``

**Description**

The **Sequence** object represents sequences of media (a.k.a. "timelines"), in Premiere Pro. 

----

==========
Attributes
==========

.. _sequence.name:

name
*********************************************

``sequence.name``

**Description**

The name of the sequence.

**Type**

String; read/write.


----

.. _sequence.id:

id
*********************************************

``sequence.id``

**Description**

This is the ordinal assigned to the sequence, upon creation. If this is the thirty-third sequence created within the project during a given Premiere Pro session, this value will be '33'.

**Type**

Integer, read-only.

----

.. _sequence.sequenceID:

sequenceID
*********************************************

``sequence.sequenceID``

**Description**

The unique identifier assigned to this sequence, at the time of its creation.

**Type**

String; read-only.


----

.. _sequence.audioTracks:

audioTracks
*********************************************

``sequence.audioTracks``

**Description**

An array of audio tracks, within the sequence.

**Type**

Array; read-only.



----

.. _sequence.videoTracks:

videoTracks
*********************************************

``sequence.videoTracks``

**Description**

An array of video tracks, within the sequence.

**Type**

Array; read-only.



----

.. _sequence.frameSizeHorizontal:

frameSizeHorizontal
*********************************************

``sequence.frameSizeHorizontal``

**Description**

The horizontal width of frames, from the sequence.

**Type**

Integer; read-only.


----

.. _sequence.frameSizeVertical:

frameSizeVertical
*********************************************

``sequence.frameSizeVertical``

**Description**

The vertical height of frames, from the sequence.

**Type**

Integer; read-only.









----

.. _sequence.timebase:

timebase
*********************************************

``sequence.timebase``

**Description**

The number of Ticks per frame, in the sequence.

**Type**

Integer; read-only.



----

.. _sequence.zeroPoint:

zeroPoint
*********************************************

``sequence.zeroPoint``

**Description**

The starting time, in Ticks, of the sequence.

**Type**

Integer; read-only.

----

.. _sequence.setZeroPoint:

setZeroPoint
*********************************************

``sequence.setZeroPoint(newZeroPoint)``

**Description**

Set the starting time of the sequence.

**Parameters**

An integer, specifying the new zero point, in Ticks.

**Type**

Integer; read-only.

**Returns**

Returns **0** if successful.

----

.. _sequence.end:

end
*********************************************

``sequence.end``

**Description**

The time, in Ticks, of the end of the sequence.

**Type**

Integer; read-only.



----

.. _sequence.markers:

markers
*********************************************

``sequence.markers``

**Description**

The markers associated with this sequence.

**Type**

Array; read-only.


----

.. _sequence.projectItem:

projectItem
*********************************************

``sequence.projectItem``

**Description**

The projectItem associated with this sequence.

**Type**

**projectItem**; read-only.


=======
Methods
=======

.. _sequence.getPlayerPosition:

getPlayerPosition()
*********************************************

``projectItem.getPlayerPosition()``

**Description**

Retrieves the current player position, in Ticks.

**Parameters**

None

**Returns**

Returns a Time object, representing the current player position. 



----


.. _sequence.setPlayerPosition:

setPlayerPosition(newTimeInTicks)
*********************************************

``projectItem.setPlayerPosition()``

**Description**

Specifies a new player position, in Ticks.

**Parameters**

An integer, **newTimeInTicks**.

**Returns**

Returns **0** if successful.

----

.. _sequence.getInPoint:

getInPoint()
*********************************************

``projectItem.getInPoint()``

**Description**

Retrieves the current sequence in point, in seconds.

**Parameters**

None.

**Returns**

Returns a Real representing the in point, in seconds.

----

.. _sequence.getOutPoint:

getOutPoint()
*********************************************

``projectItem.getOutPoint()``

**Description**

Retrieves the current sequence out point, in seconds.

**Parameters**

None.

**Returns**

Returns a Real representing the out point, in seconds.


----

.. _sequence.getInPointAsTime:

getInPointAsTime()
*********************************************

``projectItem.getInPointAsTime()``

**Description**

Retrieves the current sequence in point.

**Parameters**

None.

**Returns**

Returns a Time representing the in point, in seconds.

----

.. _sequence.getOutPointAsTime:

getOutPointAsTime()
*********************************************

``projectItem.getOutPointAsTime()``

**Description**

Retrieves the current sequence out point.

**Parameters**

None.

**Returns**

Returns a Time representing the out point, in seconds.


----

.. _sequence.setInPoint:

setInPoint(newTimeInTicks)
*********************************************

``projectItem.setInPoint()``

**Description**

Specifies a new sequence in point.

**Parameters**

An integer, **newTimeInTicks**.

**Returns**

Returns **0** if successful.

----

.. _sequence.setOutPoint:

setOutPoint(newTimeInTicks)
*********************************************

``projectItem.setOutPoint()``

**Description**

Specifies a new sequence out point.

**Parameters**

An integer, **newTimeInTicks**.

**Returns**

Returns **0** if successful.

----

.. _sequence.clone:

clone()
*********************************************

``projectItem.clone()``

**Description**

Creates a clone of the given sequence.

**Parameters**

None.

**Returns**

Returns a **Sequence** if successful, **0** if not.

----

.. _sequence.exportAsProject:

exportAsProject(outputPath)
*********************************************

``projectItem.exportAsProject(outputPath)``

**Description**

Creates a new project containing only the given sequence, and its constituent media.

**Parameters**

String ``outputPath`` specifying the output path for the new project.

**Returns**

Returns 0 if successful.

----

.. _sequence.exportAsFinalCutProXML:

exportAsFinalCutProXML(outputPath)
*********************************************

``projectItem.exportAsFinalCutProXML(outputPath)``

**Description**

Creates a new FCP XML representation of the sequence, and its constituent media.

**Parameters**

String ``outputPath`` specifying the output path for the new FCP XML file.

**Returns**

Returns 0 if successful.

----

.. _sequence.exportAsMediaDirect:

exportAsMediaDirect(outputPath)
*********************************************

``projectItem.exportAsMediaDirect(outputPath, presetPath, workAreaType)``

**Description**

Creates a new FCP XML representation of the sequence, and its constituent media.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``outputPath``             | **String**, Name of property to be added.         |
+----------------------------+---------------------------------------------------+
| ``presetPath``             | **String**, Label of property to be added.        |
+----------------------------+---------------------------------------------------+
| ``workAreaType``           | Must be one of the following:                     |
|                            |    - 0 ENCODE_ENTIRE                              |
|                            |    - 1 ENCODE_IN_TO_OUT                           |
|                            |    - 2 ENCODE_WORK_AREA                           |
+----------------------------+---------------------------------------------------+

String ``outputPath`` specifying the output path for the new FCP XML file.

**Returns**

Returns 0 if successful.

----

.. _sequence.getExportFileExtension:

getExportFileExtension()
*********************************************

``projectItem.getExportFileExtension(outputPresetPath)``

**Description**

Retrieves the file extension associated with the current sequence.

**Parameters**

String ``outputPresetPath`` specifying the output preset to be used.

**Returns**

Returns a **String** containing the output file extension, or **0** if unsuccessful.

