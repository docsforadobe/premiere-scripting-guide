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

``sequence.getPlayerPosition()``

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

``sequence.setPlayerPosition()``

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

``sequence.getInPoint()``

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

``sequence.getOutPoint()``

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

``sequence.getInPointAsTime()``

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

``sequence.getOutPointAsTime()``

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

``sequence.setInPoint()``

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

``sequence.setOutPoint()``

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

``sequence.clone()``

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

``sequence.exportAsProject(outputPath)``

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

``sequence.exportAsFinalCutProXML(outputPath)``

**Description**

Creates a new FCP XML representation of the sequence, and its constituent media.

**Parameters**

String ``outputPath`` specifying the output path for the new FCP XML file.

**Returns**

Returns 0 if successful.

----

.. _sequence.exportAsMediaDirect:

exportAsMediaDirect(outputPath, presetPath, workAreaType)
*********************************************

``sequence.exportAsMediaDirect(outputPath, presetPath, workAreaType)``

**Description**

Renders the sequence to the specified output path, using the specified output preset (.epr file), and honoring the specified work area type.

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

String ``outputPath`` specifying the output path, to which to render the media.

**Returns**

Returns 0 if successful.

----

.. _sequence.getExportFileExtension:

getExportFileExtension()
*********************************************

``sequence.getExportFileExtension(outputPresetPath)``

**Description**

Retrieves the file extension associated with the current sequence.

**Parameters**

String ``outputPresetPath`` specifying the output preset to be used.

**Returns**

Returns a **String** containing the output file extension, or **0** if unsuccessful.


----

.. _sequence.getSettings:

getSettings()
*********************************************

``sequence.getSettings()``

**Description**

Retrieves the settings of the current sequence.

**Parameters**

None.

**Returns**

Returns a sequence settings structure.




+----------------------------+------------------------------------------------------------+
| ``audioChannelCount``      | The number of audio channels in the sequence.              |
+----------------------------+------------------------------------------------------------+
| ``audioChannelType``       | Audio channel type in use. One of the following:           |
|                            |    - 0 AUDIOCHANNELTYPE_Mono                               |
|                            |    - 1 AUDIOCHANNELTYPE_Stereo                             |
|                            |    - 2 AUDIOCHANNELTYPE_51                                 |
|                            |    - 3 AUDIOCHANNELTYPE_Multichannel                       |
|                            |    - 4 AUDIOCHANNELTYPE_4Channel                           |
|                            |    - 5 AUDIOCHANNELTYPE_8Channel                           |
+----------------------------+------------------------------------------------------------+
| ``audioDisplayFormat``     | Audio timecode display format. One of the following:       |
|                            |    - 100 TIMEDISPLAY_24Timecode                            |
|                            |    - 101 TIMEDISPLAY_25Timecode                            |
|                            |    - 102 TIMEDISPLAY_2997DropTimecode                      |
|                            |    - 103 TIMEDISPLAY_2997NonDropTimecode                   |
|                            |    - 104 TIMEDISPLAY_30Timecode                            |
|                            |    - 105 TIMEDISPLAY_50Timecode                            |
|                            |    - 106 TIMEDISPLAY_5994DropTimecode                      |
|                            |    - 107 TIMEDISPLAY_5994NonDropTimecode                   |
|                            |    - 108 TIMEDISPLAY_60Timecode                            |
|                            |    - 109 TIMEDISPLAY_Frames                                |
|                            |    - 110 TIMEDISPLAY_23976Timecode                         |
|                            |    - 111 TIMEDISPLAY_16mmFeetFrames                        |
|                            |    - 112 TIMEDISPLAY_35mmFeetFrames                        |
|                            |    - 113 TIMEDISPLAY_48Timecode                            |
|                            |    - 200 TIMEDISPLAY_AudioSamplesTimecode                  |
|                            |    - 201 TIMEDISPLAY_AudioMsTimecode                       |
+----------------------------+------------------------------------------------------------+
| ``audioSampleRate``        | The audio sample rate in the sequence, as an ``int``.      |
+----------------------------+------------------------------------------------------------+
| ``compositeLinearColor``   | Whether sequence is composited in linear color. 1 if true. |
+----------------------------+------------------------------------------------------------+
| ``editingMode``            | The GUID of the editing mode in use.                       |
+----------------------------+------------------------------------------------------------+
| ``maximumBitDepth``        | Whether sequence is composited at maximum depth; 1 if true.|
+----------------------------+------------------------------------------------------------+
| ``maximumRenderQuality``   | Whether sequence is rendered at maximum quality; 1 if true.|
+----------------------------+------------------------------------------------------------+
| ``previewCodec``           | Four character code of preview codec in use.               |
+----------------------------+------------------------------------------------------------+
| ``previewFrameWidth``      | Width of preview frame.                                    |
+----------------------------+------------------------------------------------------------+
| ``previewFrameHeight``     | Height of preview frame.                                   |
+----------------------------+------------------------------------------------------------+
| ``previewFileFormat``      | Path to the output preset (.epr file) being used for       |
|                            | preview file rendering.                                    |
| 							 |                                                            |
| 							 |                                                            |
+----------------------------+------------------------------------------------------------+
| ``videoDisplayFormat``     | Video time display format. One of the following:           |
|                            |    - 100 TIMEDISPLAY_24Timecode                            |
|                            |    - 101 TIMEDISPLAY_25Timecode                            |
|                            |    - 102 TIMEDISPLAY_2997DropTimecode                      |
|                            |    - 103 TIMEDISPLAY_2997NonDropTimecode                   |
|                            |    - 104 TIMEDISPLAY_30Timecode                            |
|                            |    - 105 TIMEDISPLAY_50Timecode                            |
|                            |    - 106 TIMEDISPLAY_5994DropTimecode                      |
|                            |    - 107 TIMEDISPLAY_5994NonDropTimecode                   |
|                            |    - 108 TIMEDISPLAY_60Timecode                            |
|                            |    - 109 TIMEDISPLAY_Frames                                |
|                            |    - 110 TIMEDISPLAY_23976Timecode                         |
|                            |    - 111 TIMEDISPLAY_16mmFeetFrames                        |
|                            |    - 112 TIMEDISPLAY_35mmFeetFrames                        |
|                            |    - 113 TIMEDISPLAY_48Timecode                            |
|                            |    - 200 TIMEDISPLAY_AudioSamplesTimecode                  |
|                            |    - 201 TIMEDISPLAY_AudioMsTimecode                       |
+----------------------------+------------------------------------------------------------+
| ``videoFieldType``         |  Video field type in use in sequence. One of these:        |
|                            |    - -1 FIELDTYPE_DEFAULT                                  |
|                            |    - 0 FIELDTYPE_PROGRESSIVE                               |
|                            |    - 1 ALPHACHANNEL_UPPERFIRST                             |
|                            |    - 2 ALPHACHANNEL_LOWERFIRST                             |
+----------------------------+------------------------------------------------------------+
| ``videoFrameHeight``       | Height of sequence video frame.                            |
+----------------------------+------------------------------------------------------------+
| ``videoFrameWidth``        | Height of sequence video frame.                            |
+----------------------------+------------------------------------------------------------+
| ``videoPixelAspectRatio``  | The pixel aspect ratio, as floating point.                 |
+----------------------------+------------------------------------------------------------+
| ``vrHorzCapturedView``     |                                                            |
+----------------------------+------------------------------------------------------------+
| ``vrVertCapturedView``     |                                                            |
+----------------------------+------------------------------------------------------------+
| ``vrLayout``               | The layout of footage in use, for VR. One of these:        |
|                            |    - 0 VR_LAYOUT_MONOSCOPIC                                |
|                            |    - 1 VR_LAYOUT_STEREO_OVER_UNDER                         |
|                            |    - 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE                       |
+----------------------------+------------------------------------------------------------+
| ``vrProjection``           | The projection type in use, for VR footage. One of these:  |
|                            |    - 0 VR_LAYOUT_MONOSCOPIC                                |
|                            |    - 1 VR_LAYOUT_STEREO_OVER_UNDER                         |
|                            |    - 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE                       |
+----------------------------+------------------------------------------------------------+
| ``videoFieldType``         | Field type in sequence. One of the following:              |
|                            |    - -1 FIELDTYPE_DEFAULT                                  |
|                            |    - 0 FIELDTYPE_PROGRESSIVE                               |
|                            |    - 1 ALPHACHANNEL_UPPERFIRST                             |
|                            |    - 2 ALPHACHANNEL_LOWERFIRST                             |
+----------------------------+------------------------------------------------------------+
----

.. _sequence.setSettings:

setSettings()
*********************************************

``sequence.setSettings(sequenceSettings)``

**Description**

Sets the settings of the current sequence. *[Editorial: I apologize for any perceived pedantry; sometimes, obvious documentation needs to be obvious. -bbb]*

**Parameters**

``sequenceSettings`` is a sequence settings structure, obtained via `sequence.getSettings_`.  

**Returns**

Returns 0 if successful.



----

.. _sequence.createSubsequence:

createSubsequence(ignoreChannelMapping)
*********************************************

``sequence.createSubsequence(ignoreChannelMapping)``

**Description**

Creates a new sequence, which is a sub-sequence of the existing sequence. 

**Parameters**

A ``Boolean`` indicating whether the new sequence should ignore the channel mapping present in the original sequence.

**Returns**

Returns 0 if successful.