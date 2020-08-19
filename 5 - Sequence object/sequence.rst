.. highlight:: javascript

.. _sequence:

Sequence object
===================

``app.project.sequences[index]``

**Description**

The **Sequence** object represents sequences of media (a.k.a. "timelines"), in Premiere Pro.

----

==========
Attributes
==========

.. _sequence.audioDisplayFormat:

Sequence.audioDisplayFormat
*********************************************

``app.project.sequences[index].audioDisplayFormat``

**Description**

*Add a description*

**Type**

Number.

----

.. _sequence.audioTracks:

Sequence.audioTracks
*********************************************

``app.project.sequences[index].audioTracks``

**Description**

An array of audio tracks, within the sequence.

**Type**

Array; read-only; (TrackCollection object).

----

.. _sequence.end:

Sequence.end
*********************************************

``app.project.sequences[index].end``

**Description**

The time, in Ticks, of the end of the sequence.

**Type**

String; read-only.

----

.. _sequence.frameSizeHorizontal:

Sequence.frameSizeHorizontal
*********************************************

``app.project.sequences[index].frameSizeHorizontal``

**Description**

The horizontal width of frames, from the sequence.

**Type**

Integer; read-only.

----

.. _sequence.frameSizeVertical:

Sequence.frameSizeVertical
*********************************************

``app.project.sequences[index].frameSizeVertical``

**Description**

The vertical height of frames, from the sequence.

**Type**

Integer; read-only.

----

.. _sequence.id:

Sequence.id
*********************************************

``app.project.sequences[index].id``

**Description**

This is the ordinal assigned to the sequence, upon creation. If this is the thirty-third sequence created within the project during a given Premiere Pro session, this value will be '33'.

**Type**

Integer, read-only.

----

.. _sequence.markers:

Sequence.markers
*********************************************

``app.project.sequences[index].markers``

**Description**

The :ref:`Marker <marker>` objects associated with this sequence.

**Type**

Array; read-only; (MarkerCollection object).

----

.. _sequence.name:

Sequence.name
*********************************************

``app.project.sequences[index].name``

**Description**

The name of the sequence.

**Type**

String; read/write.

----

.. _sequence.projectItem:

Sequence.projectItem
*********************************************

``app.project.sequences[index].projectItem``

**Description**

The :ref:`projectItem` associated with this sequence.

**Type**

**projectItem**; read-only.

----

.. _sequence.sequenceID:

Sequence.sequenceID
*********************************************

``app.project.sequences[index].sequenceID``

**Description**

The unique identifier assigned to this sequence, at the time of its creation, in form of ``xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx``.

**Type**

String; read-only.

----

.. _sequence.timebase:

Sequence.timebase
*********************************************

``app.project.sequences[index].timebase``

**Description**

The number of Ticks per frame, in the sequence.

**Type**

String; read-only.

----

.. _sequence.videoDisplayFormat:

Sequence.videoDisplayFormat
*********************************************

``app.project.sequences[index].videoDisplayFormat``

**Description**

*Add a description*

**Type**

Number.

----

.. _sequence.videoTracks:

Sequence.videoTracks
*********************************************

``app.project.sequences[index].videoTracks``

**Description**

An array of video tracks, within the sequence.

**Type**

Array; read-only; (TrackCollection object).

----

.. _sequence.zeroPoint:

Sequence.zeroPoint
*********************************************

``app.project.sequences[index].zeroPoint``

**Description**

The starting time, in Ticks, of the sequence.

**Type**

String; read-only.

----

=======
Methods
=======

.. _sequence.autoReframeSequence:

Sequence.autoReframeSequence()
*******************************************************************************************************

``app.project.sequences[index].autoReframeSequence(numerator, denominator, motionPreset, newName, useNestedSequences)``

**Description**

Generates a new, auto-reframed sequence. 

**Parameters**

+----------------------------+------------------------------------------------------------------------+
| ``numerator``              | Numerator of desired frame aspect ratio.                               |
+----------------------------+------------------------------------------------------------------------+
| ``denominator``            | Denominator of desired frame aspect ratio.                             |
+----------------------------+------------------------------------------------------------------------+
| ``motionPreset``           | Valid values: `'slower'`, `'default'`, or `'faster'` motion.           |
+----------------------------+------------------------------------------------------------------------+
| ``newName``                | Name for newly-created sequence.                                       |
+----------------------------+------------------------------------------------------------------------+
| ``useNestedSequences``     | Boolean indicating whether to honor nested sequence.                   |
+----------------------------+------------------------------------------------------------------------+

**Returns**

Returns the new Sequence object, if successful; `0` if unsuccessful.

----

.. _sequence.clone:

Sequence.clone()
*********************************************

``app.project.sequences[index].clone()``

**Description**

Creates a clone of the given sequence.

**Parameters**

None.

**Returns**

Returns a :ref:`sequence` if successful, **0** if not.

----

.. _sequence.createSubsequence:

Sequence.createSubsequence()
***********************************************

``app.project.sequences[index].createSubsequence(ignoreChannelMapping)``

**Description**

Creates a new sequence, which is a sub-sequence of the existing sequence.

**Parameters**

A ``Boolean`` indicating whether the new sequence should ignore the channel mapping present in the original sequence.

**Returns**

Returns 0 if successful.

----

.. _sequence.exportAsFinalCutProXML:

Sequence.exportAsFinalCutProXML()
*********************************************

``app.project.sequences[index].exportAsFinalCutProXML(outputPath)``

**Description**

Creates a new FCP XML representation of the sequence, and its constituent media.

**Parameters**

String ``outputPath`` specifying the output path for the new FCP XML file.

**Returns**

Returns 0 if successful.

----

.. _sequence.exportAsMediaDirect:

Sequence.exportAsMediaDirect()
*********************************************************

``app.project.sequences[index].exportAsMediaDirect(outputPath, presetPath, workAreaType)``

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

.. _sequence.exportAsProject:

Sequence.exportAsProject()
*********************************************

``app.project.sequences[index].exportAsProject(outputPath)``

**Description**

Creates a new :ref:`project` containing only the given sequence, and its constituent media.

**Parameters**

String ``outputPath`` specifying the output path for the new project.

**Returns**

Returns 0 if successful.

----

.. _sequence.getExportFileExtension:

Sequence.getExportFileExtension()
*********************************************

``app.project.sequences[index].getExportFileExtension(outputPresetPath)``

**Description**

Retrieves the file extension associated with the current sequence.

**Parameters**

String ``outputPresetPath`` specifying the output preset to be used.

**Returns**

Returns a **String** containing the output file extension, or **0** if unsuccessful.

----

.. _sequence.getInPoint:

Sequence.getInPoint()
*********************************************

``app.project.sequences[index].getInPoint()``

**Description**

Retrieves the current sequence in point, in seconds.

**Parameters**

None.

**Returns**

Returns a Real representing the in point, in seconds.

----

.. _sequence.getInPointAsTime:

Sequence.getInPointAsTime()
*********************************************

``app.project.sequences[index].getInPointAsTime()``

**Description**

Retrieves the current sequence in point.

**Parameters**

None.

**Returns**

Returns a :ref:`time` representing the in point, in seconds.

----

.. _sequence.getOutPoint:

Sequence.getOutPoint()
*********************************************

``app.project.sequences[index].getOutPoint()``

**Description**

Retrieves the current sequence out point, in seconds.

**Parameters**

None.

**Returns**

Returns a Real representing the out point, in seconds.

----

.. _sequence.getOutPointAsTime:

Sequence.getOutPointAsTime()
*********************************************

``app.project.sequences[index].getOutPointAsTime()``

**Description**

Retrieves the current sequence out point.

**Parameters**

None.

**Returns**

Returns a :ref:`time` representing the out point, in seconds.

----

.. _sequence.getPlayerPosition:

Sequence.getPlayerPosition()
*********************************************

``app.project.sequences[index].getPlayerPosition()``

**Description**

Retrieves the current player position, in Ticks.

**Parameters**

None

**Returns**

Returns a :ref:`time`, representing the current player position.

----

.. _sequence.getSettings:

Sequence.getSettings()
*********************************************

``app.project.sequences[index].getSettings()``

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
| ``videoPixelAspectRatio``  | The pixel aspect ratio, as a ratio, as a String.           |
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

.. _sequence.isDoneAnalyzingForVideoEffects:

Sequence.isDoneAnalyzingForVideoEffects()
*******************************************************************************************************

``app.project.sequences[index].isDoneAnalyzingForVideoEffects()``

**Description**

Returns whether or not the sequence is done analyzing for video effects.

**Parameters**

None.

**Returns**

Returns ``true`` if analysis is complete.

----

.. _sequence.performSceneEditDetectionOnSelection:

Sequence.performSceneEditDetectionOnSelection()
*******************************************************************************************************

``app.project.sequences[index].performSceneEditDetectionOnSelection(actionDesired, ApplyCutsToLinkedAudio, sensitivity)``

**Description**

Performs cut detection on the sequence selection. 

**Parameters**

+----------------------------+------------------------------------------------------------------------+
| ``actionDesired``          | `'CreateMarkers'` or `'ApplyCuts'`.                                    |
+----------------------------+------------------------------------------------------------------------+
| ``ApplyCutsToLinkedAudio`` | Boolean.                                                               |
+----------------------------+------------------------------------------------------------------------+
| ``sensitivity``            | `'LowSensitivity'`, `'MediumSensitivity'`, or `'HighSensitivity'`.     |
+----------------------------+------------------------------------------------------------------------+

**Returns**

Returns `true` if successful.

----

.. _sequence.setInPoint:

Sequence.setInPoint()
*********************************************

``app.project.sequences[index].setInPoint(newTimeInTicks)``

**Description**

Specifies a new sequence in point.

**Parameters**

An integer, **newTimeInTicks**.

**Returns**

Returns **0** if successful.

----

.. _sequence.setOutPoint:

Sequence.setOutPoint()
*********************************************

``app.project.sequences[index].setOutPoint(newTimeInTicks)``

**Description**

Specifies a new sequence out point.

**Parameters**

An integer, **newTimeInTicks**.

**Returns**

Returns **0** if successful.

----

.. _sequence.setPlayerPosition:

Sequence.setPlayerPosition()
*********************************************

``app.project.sequences[index].setPlayerPosition(newTimeInTicks)``

**Description**

Specifies a new player position, in Ticks, as a String.

**Parameters**

A String referenced the **newTimeInTicks**.

**Returns**

Returns **0** if successful.

----

.. _sequence.setSettings:

Sequence.setSettings()
*********************************************

``app.project.sequences[index].setSettings(sequenceSettings)``

**Description**

Sets the settings of the current sequence. *[Editorial: I apologize for any perceived pedantry; sometimes, obvious documentation needs to be obvious. -bbb]*

**Parameters**

``sequenceSettings`` is a sequence settings structure, obtained via :ref:`sequence.getSettings() <sequence.getSettings>`.

**Returns**

Returns 0 if successful.

.. _sequence.setZeroPoint:

Sequence.setZeroPoint()
*********************************************

``app.project.sequences[index].setZeroPoint(newZeroPoint)``

**Description**

Set the starting time of the sequence.

**Parameters**

An integer, specifying the new zero point, in ticks, as a String.

**Type**

Integer; read-only.

**Returns**

Returns **0** if successful.
