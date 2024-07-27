.. highlight:: javascript

.. _sequence:

Sequence object
===================

``app.project.sequences[index]``

**Description**

The **Sequence** object represents sequences of media, or 'timelines', in Premiere Pro.

----

==========
Attributes
==========

.. _sequence.audioDisplayFormat:

Sequence.audioDisplayFormat
***************************

``app.project.sequences[index].audioDisplayFormat``

**Description**

The audio display format of the sequence.

Set this attribute with the :ref:`sequence.setsettings` method. 

**Type**

An enumerated value; read/write. One of:
         
=======  =============
``200``  Audio Samples
``201``  Milliseconds
=======  =============

----

.. _sequence.audioTracks:

Sequence.audioTracks
********************

``app.project.sequences[index].audioTracks``

**Description**

An array of audio :ref:`Track <Track>` objects in the sequence.

**Type**

:ref:`trackCollection`; read-only.

----

.. _sequence.end:

Sequence.end
************

``app.project.sequences[index].end``

**Description**

The time, in **ticks**, of the end of the sequence.

**Type**

String; read-only.

----

.. _sequence.frameSizeHorizontal:

Sequence.frameSizeHorizontal
****************************

``app.project.sequences[index].frameSizeHorizontal``

**Description**

The horizontal frame size, or width, of the sequence.

Set this attribute with the :ref:`sequence.setsettings` method.

**Type**

Integer; read-only.

----

.. _sequence.frameSizeVertical:

Sequence.frameSizeVertical
**************************

``app.project.sequences[index].frameSizeVertical``

**Description**

The vertical frame size, or height, of the sequence.

Set this attribute with the :ref:`sequence.setsettings` method.

**Type**

Integer; read-only.

----

.. _sequence.id:

Sequence.id
***********

``app.project.sequences[index].id``

**Description**

This is the ordinal assigned to the sequence upon creation. If this is the thirty-third sequence created within the project during a given Premiere Pro session, this value will be ``33``

**Type**

Integer, read-only.

.. Note:: In testing, this attribute seems unstable and produces unreliable results. Recommend using :ref:`sequence.sequenceid` instead. 


----

.. _sequence.markers:

Sequence.markers
****************

``app.project.sequences[index].markers``

**Description**

An array of :ref:`Marker <marker>` objects in the sequence.

**Type**

:ref:`markerCollection`, read-only;

----

.. _sequence.name:

Sequence.name
*************

``app.project.sequences[index].name``

**Description**

The name of the sequence.

**Type**

String; read/write.

----

.. _sequence.projectItem:

Sequence.projectItem
********************

``app.project.sequences[index].projectItem``

**Description**

The :ref:`projectItem` associated with the sequence.

**Type**

:ref:`projectitem`; read-only.

.. note:: Not all sequences will have a ``projectItem``. There may be sequences in a project that Premiere generates that are invisible to the user, these do not have ``projectItems``


----

.. _sequence.sequenceID:

Sequence.sequenceID
*******************

``app.project.sequences[index].sequenceID``

**Description**

The unique identifier assigned to this sequence, at the time of its creation, in the form of ``xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx``

**Type**

String; read-only.

----

.. _sequence.timebase:

Sequence.timebase
*****************

``app.project.sequences[index].timebase``

**Description**

The number of **ticks** per frame in the sequence. Converted to seconds, this is commonly referred to as the frame duration of the sequence.

**Type**

String; read-only.

----

.. _sequence.videoDisplayFormat:

Sequence.videoDisplayFormat
***************************

``app.project.sequences[index].videoDisplayFormat``

**Description**

The video display format of the sequence.

Set this attribute with the :ref:`sequence.setsettings` method.

**Type**

An enumerated value; read/write. One of:
         
=======  ========================
``100``   24 Timecode
``101``   25 Timecode
``102``   29.97 Drop Timecode
``103``   29.97 Non-Drop Timecode
``104``   30 Timecode
``105``   50 Timecode
``106``   59.94 Drop Timecode
``107``   59.94 Non-Drop Timecode
``108``   60 Timecode
``109``   Frames
``110``   23.976 Timecode
``111``   16mm Feet + Frames
``112``   35mm Feet + Frames
``113``   48 Timecode
=======  ========================

----

.. _sequence.videoTracks:

Sequence.videoTracks
********************

``app.project.sequences[index].videoTracks``

**Description**

An array of video :ref:`Track <Track>` objects in the sequence.

**Type**

:ref:`trackCollection`; read-only.

----

.. _sequence.zeroPoint:

Sequence.zeroPoint
******************

``app.project.sequences[index].zeroPoint``

**Description**

The starting time, in **ticks**, of the sequence.

Set this attribute with the :ref:`sequence.setzeropoint` method. 

**Type**

String; read-only.

----

=======
Methods
=======

.. _sequence.attachCustomProperty:

Sequence.attachCustomProperty()
*******************************

``app.project.sequences[index].attachCustomProperty(propertyID, propertyValue)``

**Description**

Attaches a custom property, and its value, to the sequence. This property is visible if/when the sequence is exported to FCP XML.

**Parameters**

=================  ==========  =========================
Argument           Type        Description
=================  ==========  =========================
``propertyID``     ``String``  ID of custom property.  
``propertyValue``  ``String``  Value of custom property.
=================  ==========  =========================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.autoReframeSequence:

Sequence.autoReframeSequence()
******************************

``app.project.sequences[index].autoReframeSequence(numerator, denominator, motionPreset, newName, useNestedSequences)``

**Description**

Generates a new, auto-reframed sequence. 

**Parameters**

======================  ===========  =============================================
Argument                Type         Description
======================  ===========  =============================================
``numerator``           ``Integer``  Numerator of desired frame aspect ratio.  
``denominator``         ``Integer``  Denominator of desired frame aspect ratio.  
``motionPreset``        ``String``   One of: ``slower``, ``default`` or ``faster``
``newName``             ``String``   A name for a newly created sequence. 
``useNestedSequences``  ``Boolean``  Whether to honor nested sequence. 
======================  ===========  =============================================

**Returns**

Returns the new :ref:`sequence`.

**Example**

.. code:: javascript

    var sequence = app.project.activeSequence;
    if (sequence) {
        var numerator = 1;
        var denominator = 1;
        var motionPreset = 'default'; // 'default', 'faster', 'slower'
        var newName = sequence.name + ', auto-reframed.';
        var useNestedSequences  = false;

        var newSequence = sequence.autoReframeSequence(numerator, denominator, motionPreset, newName, useNestedSequences);

        if (newSequence) {
            alert('Created reframed sequence: ' + newName + '.');
        } else {
            alert('Failed to create re-framed sequence: ' + newName + '.');
        }
    } else {
        alert('No active sequence');
    }

----

.. _sequence.clone:

Sequence.clone()
****************

``app.project.sequences[index].clone()``

**Description**

Creates a clone, or a duplicate, of the sequence.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.close:

Sequence.close()
****************

``app.project.sequences[index].close()``

**Description**

Closes the sequence.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.createCaptionTrack:

Sequence.createCaptionTrack()
*****************************

``app.project.sequences[index].createCaptionTrack(projectItem, 
startAtTime, captionFormat)``

**Description**

Creates a caption track in the sequence using caption data from a :ref:`projectitem`.

**Parameters**

=================  ==================  ======================================================================================================
Argument           Type                Description
=================  ==================  ======================================================================================================
``projectItem``    :ref:`projectitem`  A captions source clip (e.g. .srt)
``startAtTime``    ``Float``           Offset in seconds from start of sequence
``captionFormat``  ``Constant``        Caption format of the new track (see below). Optional, default is ``Sequence.CAPTION_FORMAT_SUBTITLE``
=================  ==================  ======================================================================================================

====================================  ============
``captionFormat``                     Description
====================================  ============
``Sequence.CAPTION_FORMAT_SUBTITLE``  Subtitle
``Sequence.CAPTION_FORMAT_608``       CEA-608
``Sequence.CAPTION_FORMAT_708``       CEA-708
``Sequence.CAPTION_FORMAT_TELETEXT``  Teletext
``Sequence.CAPTION_FORMAT_OPEN_EBU``  EBU Subtitle
``Sequence.CAPTION_FORMAT_OP42``      OP-42
``Sequence.CAPTION_FORMAT_OP47``      OP-47
====================================  ============

**Returns**

Returns a boolean; ``true`` if successful.

**Example**

.. code:: javascript

	app.project.activeSequence.createCaptionTrack(projectItem, 0, Sequence.CAPTION_FORMAT_708);

----

.. _sequence.createSubsequence:

Sequence.createSubsequence()
****************************

``app.project.sequences[index].createSubsequence(ignoreTrackTargeting)``

**Description**

Creates a new sequence, from the in point to the out point, which is a sub-sequence of the original sequence.

**Parameters**

========================  ===========  ====================================================================================================================
Argument                  Type         Description
========================  ===========  ====================================================================================================================
``ignoreTrackTargeting``  ``Boolean``  Whether the new sequence should ignore the track targeting, in the original sequence. Optional, default is ``false``
========================  ===========  ====================================================================================================================

**Returns**

Returns the newly-created :ref:`sequence`.

.. note:: This is not the same as nesting. The newly-created sequence is not inserted back into the original sequence. To nest, see the example function below. 

**Example**

.. code:: javascript

    function nestSelection() {
        var activeSequence = app.project.activeSequence;
        var selection = activeSequence.getSelection();

        if (!selection.length) {
            return;
        }
        
        var trackId = selection[0].parentTrackIndex;
        var originalInPoint = activeSequence.getInPointAsTime();
        var originalOutPoint = activeSequence.getOutPointAsTime();
        var start = selection[0].start;
        var end = selection[selection.length - 1].end;
        activeSequence.setInPoint(start.seconds);
        activeSequence.setOutPoint(end.seconds);

        var nestedSequence = activeSequence.createSubsequence(true);

        activeSequence.videoTracks[trackId].overwriteClip(nestedSequence.projectItem, start.seconds);
        activeSequence.setInPoint(originalInPoint.seconds);
        activeSequence.setOutPoint(originalOutPoint.seconds);

        return nestedSequence;
    }

----

.. _sequence.exportAsFinalCutProXML:

Sequence.exportAsFinalCutProXML()
*********************************

``app.project.sequences[index].exportAsFinalCutProXML(outputPath)``

**Description**

Creates a new FCP XML representation of the sequence and its constituent media.

**Parameters**

==============  ===========  =========================================
Argument        Type         Description
==============  ===========  =========================================
``outputPath``  ``String``   The output path for the new FCP XML file.
==============  ===========  =========================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.exportAsMediaDirect:

Sequence.exportAsMediaDirect()
******************************

``app.project.sequences[index].exportAsMediaDirect(outputPath, presetPath, workAreaType)``

**Description**

Renders the sequence to the specified output path, using the specified output preset (.epr file), and honoring the specified work area type.

**Parameters**

================  ===========  =========================================================================
Argument          Type         Description
================  ===========  =========================================================================
``outputPath``    ``String``   An output path, to which to render the media.
``presetPath``    ``String``   Path to the preset file (.epr file) which contains the encoding settings.
``workAreaType``  ``Integer``  The work area type to be rendered (see below).
================  ===========  =========================================================================

================  =====================================================
``workAreaType``  Description
================  =====================================================
``0``             Renders the entire sequence.
``1``             Renders between the in and out point of the sequence.
``2``             Renders the work area of the sequence.
================  =====================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.exportAsProject:

Sequence.exportAsProject()
**************************

``app.project.sequences[index].exportAsProject(outputPath)``

**Description**

Creates a new :ref:`project` containing only the given sequence and its constituent media.

**Parameters**

==============  ==========  ====================================
Argument        Type        Description
==============  ==========  ====================================
``outputPath``  ``String``  The output path for the new project.
==============  ==========  ====================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.getExportFileExtension:

Sequence.getExportFileExtension()
*********************************

``app.project.sequences[index].getExportFileExtension(outputPresetPath)``

**Description**

Retrieves the file extension associated with the specified output preset (.epr file).

**Parameters**

====================  ==========  =============================
Argument              Type        Description
====================  ==========  =============================
``outputPresetPath``  ``String``  The output preset to be used.
====================  ==========  =============================

**Returns**

Returns a string.

----

.. _sequence.getInPoint:

Sequence.getInPoint()
*********************

``app.project.sequences[index].getInPoint()``

**Description**

Retrieves the current sequence in point, in seconds.

**Parameters**

None.

**Returns**

Returns a string.

----

.. _sequence.getInPointAsTime:

Sequence.getInPointAsTime()
***************************

``app.project.sequences[index].getInPointAsTime()``

**Description**

Retrieves the current sequence in point.

**Parameters**

None.

**Returns**

Returns a :ref:`time`.

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

Returns a string.

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

Returns a :ref:`time`.

----

.. _sequence.getPlayerPosition:

Sequence.getPlayerPosition()
*********************************************

``app.project.sequences[index].getPlayerPosition()``

**Description**

Retrieves the position of the CTI (Current Time Indicator), in **ticks**.

**Parameters**

None.

**Returns**

Returns a :ref:`time`.

----

.. _sequence.getSelection():

Sequence.getSelection()
***********************

``app.project.sequences[index].getSelection()``

**Description**

An array of :ref:`Track item <trackItem>` objects, of the selected clips in the sequence, in temporal order.

**Parameters**

None.

**Returns**

Returns a :ref:`trackitemcollection`.

----

.. _sequence.getSettings:

Sequence.getSettings()
**********************

``app.project.sequences[index].getSettings()``

**Description**

Retrieves the settings of the current sequence.

**Parameters**

None.

**Returns**

Returns an object; a sequence settings structure.

+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| Property                  | Type         | Possible Values                     | Description                                                                  |
+===========================+==============+=====================================+==============================================================================+
| ``audioChannelCount``     | ``Integer``  |                                     | Number of audio channels in the sequence.                                    |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
|| ``audioChannelType``     || ``Integer`` || ``0`` Mono                         || Audio channel type.                                                         |
||                          ||             || ``1`` Stereo                       ||                                                                             |
||                          ||             || ``2`` 5.1                          ||                                                                             |
||                          ||             || ``3`` Multichannel                 ||                                                                             |
||                          ||             || ``4`` 4 Channel                    ||                                                                             |
||                          ||             || ``5`` 8 Channel                    ||                                                                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
|| ``audioDisplayFormat``   || ``Integer`` || ``200`` Audio Samples              || Audio timecode display format.                                              |
||                          ||             || ``201`` Milliseconds               ||                                                                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``audioSampleRate``       | :ref:`time`  |                                     | Audio sample rate.                                                           |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``autoToneMapEnabled``    | ``Boolean``  |                                     | Whether Auto Tone Map Media is checked.                                      |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``compositeLinearColor``  | ``Boolean``  |                                     | Whether sequence is composited in linear color.                              |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``editingMode``           | ``String``   |                                     | The GUID of the editing mode.                                                |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``maximumBitDepth``       | ``Boolean``  |                                     | Whether sequence is composited at maximum depth.                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``maximumRenderQuality``  | ``Boolean``  |                                     | Whether sequence is rendered at maximum quality.                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``previewCodec``          | ``String``   |                                     | Four character code of preview codec in use.                                 |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``previewFrameWidth``     | ``Integer``  |                                     | Width of preview frame.                                                      |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``previewFrameHeight``    | ``Integer``  |                                     | Height of preview frame.                                                     |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``previewFileFormat``     | ``Integer``  |                                     | Path to the output preset (.epr file) being used for preview file rendering. |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
|| ``videoDisplayFormat``   || ``Integer`` || ``100`` 24 Timecode                || Video time display format.                                                  |
||                          ||             || ``101`` 25 Timecode                ||                                                                             |
||                          ||             || ``102`` 29.97 Drop Timecode        ||                                                                             |
||                          ||             || ``103`` 29.97 Non-Drop Timecode    ||                                                                             |
||                          ||             || ``104`` 30 Timecode                ||                                                                             |
||                          ||             || ``105`` 50 Timecode                ||                                                                             |
||                          ||             || ``106`` 59.94 Drop Timecode        ||                                                                             |
||                          ||             || ``107`` 59.94 Non-Drop Timecode    ||                                                                             |
||                          ||             || ``108`` 60 Timecode                ||                                                                             |
||                          ||             || ``109`` Frames                     ||                                                                             |
||                          ||             || ``110`` 23.976 Timecode            ||                                                                             |
||                          ||             || ``111`` 16mm Feet + Frames         ||                                                                             |
||                          ||             || ``112`` 35mm Feet + Frames         ||                                                                             |
||                          ||             || ``113`` 48 Timecode                ||                                                                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
|| ``videoFieldType``       || ``Integer`` || ``-1`` Default                     || Video field type.                                                           |
||                          ||             || ``0`` No Fields (Progressive Scan) ||                                                                             |
||                          ||             || ``1`` Upper Field First            ||                                                                             |
||                          ||             || ``2`` Lower Field First            ||                                                                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``videoFrameHeight``      | ``Integer``  |                                     | Height of sequence video frame.                                              |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``videoFrameWidth``       | ``Integer``  |                                     | Width of sequence video frame.                                               |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``videoPixelAspectRatio`` | ``String``   |                                     | Pixel aspect ratio.                                                          |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``vrHorzCapturedView``    | ``Integer``  |                                     | The horizontal captured view, in degrees, for VR.                            |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
| ``vrVertCapturedView``    | ``Integer``  |                                     | The vertical captured view, in degrees, for VR.                              |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
|| ``vrLayout``             || ``Integer`` || ``0`` Monoscopic                   || The layout of footage in use, for VR.                                       |
||                          ||             || ``1`` Stereoscopic - Over/Under    ||                                                                             |
||                          ||             || ``2`` Stereoscopic - Side by Side  ||                                                                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+
|| ``vrProjection``         || ``Integer`` || ``0`` None                         || The projection type in use, for VR footage.                                 |
||                          ||             || ``1`` Equirectangular              ||                                                                             |
+---------------------------+--------------+-------------------------------------+------------------------------------------------------------------------------+

----

.. _sequence.getWorkAreaInPoint:

Sequence.getWorkAreaInPoint()
*****************************

``app.project.sequences[index].getWorkAreaInPoint()``

**Description**

Retrieves the current sequence work area in point, in **seconds**.

**Parameters**

None.

**Returns**

Returns a string.

----

.. _sequence.getWorkAreaInPointAsTime:

Sequence.getWorkAreaInPointAsTime()
***********************************

``app.project.sequences[index].getWorkAreaInPointAsTime()``

**Description**

Retrieves the current sequence work area in point.

**Parameters**

None.

**Returns**

Returns a :ref:`time`.

----

.. _sequence.getWorkAreaOutPoint:

Sequence.getWorkAreaOutPoint()
******************************

``app.project.sequences[index].getWorkAreaOutPoint()``

**Description**

Retrieves the current sequence work area out point, in seconds.

**Parameters**

None.

**Returns**

Returns a string.

----

.. _sequence.getWorkAreaOutPointAsTime:

Sequence.getWorkAreaOutPointAsTime()
************************************

``app.project.sequences[index].getWorkAreaOutPointAsTime()``

**Description**

Retrieves the current sequence work area out point.

**Parameters**

None.

**Returns**

Returns a :ref:`time`.

----

.. _sequence.importMGT:

Sequence.importMGT()
********************

``app.project.sequences[index].importMGT(path, time, vidTrackOffset, audTrackOffset)``

**Description**

Imports a MOGRT, or an After Effects Motion Graphics Template, to the specified video or audio track, at the specified time.

**Parameters**

==================  ===========  ==================================================================================
Argument            Type         Description
==================  ===========  ==================================================================================
``path``            ``String``   Full path to a valid MOGRT (.mogrt file), created in After Effects.
``time``            ``String``   The time at which to insert .mogrt, in **ticks**.
``vidTrackOffset``  ``Integer``  How many tracks from the zero-th video track, into which to insert .mogrt content.
``audTrackOffset``  ``Integer``  How many tracks from the zero-th audio track, into which to insert .mogrt content.
==================  ===========  ==================================================================================

**Returns**

Returns a :ref:`trackitem`.

----

.. _sequence.importMGTFromLibrary:

Sequence.importMGTFromLibrary()
*******************************

``app.project.sequences[index].importMGTFromLibrary(libraryName, mgtName, time, vidTrackOffset, audTrackOffset)``

**Description**

Imports a MOGRT, or an After Effects Motion Graphics Template, from the current Premiere Pro user's Creative Cloud Libraries, to the specified video or audio track, at the specified time.

**Parameters**

==================  ===========  =======================
Argument            Type         Description
==================  ===========  =======================
``libraryName``     ``String``   The name of Library (from the current PPro user's Creative Cloud Libraries).
``mgtName``         ``String``   The name of .mogrt within that library.
``time``            ``String``   The time at which to insert .mogrt, in **ticks**.
``vidTrackOffset``  ``Integer``  How many tracks from the zero-th video track, into which to insert .mogrt content.
``audTrackOffset``  ``Integer``  How many tracks from the zero-th audio track, into which to insert .mogrt content.
==================  ===========  =======================

**Returns**

Returns a :ref:`trackitem`.

----

.. _sequence.insertClip:

Sequence.insertClip()
*********************

``app.project.sequences[index].insertClip(projectItem, time, vTrackIndex, aTrackIndex)``

**Description**

Inserts a clip into the sequence, on the specified video and audio tracks, at the specified time.

**Parameters**

===============  ==================  =============================================================
Argument         Type                Description
===============  ==================  =============================================================
``projectItem``  :ref:`projectItem`  A project item from which to get media.
``time``         ``String``          The time at which to add project item, in **seconds**.
``vTrackIndex``  ``Integer``             The (zero-based) track index, into which to insert video.
``aTrackIndex``  ``Integer``             The (zero-based) track index, into which to insert audio.
===============  ==================  =============================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.isDoneAnalyzingForVideoEffects:

Sequence.isDoneAnalyzingForVideoEffects()
*****************************************

``app.project.sequences[index].isDoneAnalyzingForVideoEffects()``

**Description**

Returns whether or not the sequence is done analyzing for video effects.

**Parameters**

None.

**Returns**

Returns a boolean.

----

.. _sequence.isWorkAreaEnabled:

Sequence.isWorkAreaEnabled()
****************************

``app.project.sequences[index].isWorkAreaEnabled()``

**Description**

Returns whether or not the sequence work area bar is enabled.

.. note:: The work area bar is disabled by default. To enable it, check 'Work Area Bar' in the sequence hamburger menu.

**Parameters**

None.

**Returns**

Returns a boolean.

----

.. _sequence.linkSelection:

Sequence.linkSelection()
************************

``app.project.sequences[index].linkSelection()``

**Description**

Links the selected video and audio clips in the sequence.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.overwriteClip:

Sequence.overwriteClip()
************************

``app.project.sequences[index].overwriteClip(projectItem, time, vTrackIndex, aTrackIndex)``

**Description**

Inserts a clip into the sequence, **overwriting existing clips**, on the specified video and audio tracks, at the specified time.

**Parameters**

===============  ==================  =========================================================
Argument         Type                Description
===============  ==================  =========================================================
``projectItem``  :ref:`projectItem`  A project item from which to get media.
``time``         ``String``          The time at which to add project item, in **seconds**.
``vTrackIndex``  ``Integer``         The (zero-based) track index, into which to insert video.
``aTrackIndex``  ``Integer``         The (zero-based) track index, into which to insert audio.
===============  ==================  =========================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.performSceneEditDetectionOnSelection:

Sequence.performSceneEditDetectionOnSelection()
***********************************************

``app.project.sequences[index].performSceneEditDetectionOnSelection(actionDesired, applyCutsToLinkedAudio, sensitivity)``

**Description**

Performs cut detection on the sequence selection. 

**Parameters**

==========================  ===========  ========================================================================
Argument                    Type         Description
==========================  ===========  ========================================================================
``actionDesired``           ``String``   One of: ``CreateMarkers`` or ``ApplyCuts``
``applyCutsToLinkedAudio``  ``Boolean``  Whether to apply detected cuts on linked audio.
``sensitivity``             ``String``   One of: ``LowSensitivity``, ``MediumSensitivity`` or ``HighSensitivity``
==========================  ===========  ========================================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.setInPoint:

Sequence.setInPoint()
*********************

``app.project.sequences[index].setInPoint(time)``

**Description**

Sets a new sequence in point.

**Parameters**

========  ==========================  ==========================
Argument  Type                        Description
========  ==========================  ==========================
``time``  ``Integer`` or :ref:`time`  A new time in **seconds**.
========  ==========================  ==========================

**Returns**

Null.

----

.. _sequence.setOutPoint:

Sequence.setOutPoint()
**********************

``app.project.sequences[index].setOutPoint(time)``

**Description**

Sets a new sequence out point.

**Parameters**

========  ==========================  ==========================
Argument  Type                        Description
========  ==========================  ==========================
``time``  ``Integer`` or :ref:`time`  A new time in **seconds**.
========  ==========================  ==========================

**Returns**

Null.

----

.. _sequence.setPlayerPosition:

Sequence.setPlayerPosition()
****************************

``app.project.sequences[index].setPlayerPosition(time)``

**Description**

Sets the position of the CTI (Current Time Indicator) in the sequence.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          ``String``   A new time in **ticks**.
================  ===========  =======================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.setSettings:

Sequence.setSettings()
**********************

``app.project.sequences[index].setSettings(sequenceSettings)``

**Description**

Sets the settings of the current sequence. *[Editorial: I apologize for any perceived pedantry; sometimes, obvious documentation needs to be obvious. -bbb]*

**Parameters**

====================  ==========  ==============================================================================================
Argument               Type       Description
====================  ==========  ==============================================================================================
``sequenceSettings``  ``Object``  A sequence settings object, obtained via :ref:`Sequence.getSettings() <sequence.getSettings>`.
====================  ==========  ==============================================================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.setWorkAreaInPoint:

Sequence.setWorkAreaInPoint()
*****************************

``app.project.sequences[index].setWorkAreaInPoint(time)``

**Description**

Sets a new sequence work area in point.

**Parameters**

========  ==========================  ==========================
Argument  Type                        Description
========  ==========================  ==========================
``time``  ``Integer`` or :ref:`time`  A new time in **seconds**.
========  ==========================  ==========================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.setWorkAreaInPoint:

Sequence.setWorkAreaOutPoint()
******************************

``app.project.sequences[index].setWorkAreaOutPoint(time)``

**Description**

Sets a new sequence work area out point.

**Parameters**

========  ==========================  ==========================
Argument  Type                        Description
========  ==========================  ==========================
``time``  ``Integer`` or :ref:`time`  A new time in **seconds**.
========  ==========================  ==========================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.unlinkSelection:

Sequence.unlinkSelection()
**************************

``app.project.sequences[index].unlinkSelection()``

**Description**

Unlinks the selected video and audio clips in the sequence.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _sequence.setZeroPoint:

Sequence.setZeroPoint()
***********************

``app.project.sequences[index].setZeroPoint(newZeroPoint)``

**Description**

Set the starting time of the sequence.

**Parameters**

================  ==========  =================================
Argument          Type         Description
================  ==========  =================================
``newZeroPoint``  ``String``   The new zero point in **ticks**.
================  ==========  =================================

**Returns**

Returns a boolean; ``true`` if successful.
