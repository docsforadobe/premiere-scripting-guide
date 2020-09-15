.. highlight:: javascript

.. _project:

Project object
===================

``app.project``

**Description**

Represents a Premiere Pro project. As of Premiere Pro 12.0, multiple projects may be open at the same time.

----

==========
Attributes
==========

.. _project.activeSequence:

Project.activeSequence
*********************************************

``app.project.activeSequence``

**Description**

The currently active :ref:`sequence`, within the project.

**Type**

a :ref:`sequence`, or ``0`` if no sequence is currently active.

----

.. _project.cloudProjectlocalID:

Project.cloudProjectlocalID
*********************************************

``app.project.cloudProjectlocalID``

**Description**

The ID of cloud project.

**Type**

String; read/only.

----

.. _project.documentID:

Project.documentID
*********************************************

``app.project.documentID``

**Description**

A unique identifier for this project, in format of ``xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx``.

**Type**

String; read-only.

----

.. _project.isCloudProject:

Project.isCloudProject
*********************************************

``app.project.isCloudProject``

**Description**

Check whether the project is cloud project.

**Type**

Boolean; read-only.

----

.. _project.name:

Project.name
*********************************************

``app.project.name``

**Description**

The name of the project.

**Type**

String; read-only.

----

.. _project.path:

Project.path
*********************************************

``app.project.path``

**Description**

The file path of the project.

**Type**

String; read-only.

**Example**

Get a path of a curently active project

.. code:: javascript

    app.project.path; // /Users/USERNAME/Desktop/Project.prproj

----

.. _project.rootItem:

Project.rootItem
*********************************************

``app.project.rootItem``

**Description**

A :ref:`projectItem` representing the "root" of the project.

**Type**

A :ref:`projectItem`; this will always be of type ``ProjectItemType_BIN``.

----

.. _project.sequences:

Project.sequences
*********************************************

``app.project.sequences``

**Description**

The sequences within the project.

**Type**

:ref:`sequenceCollection`, read-only.

----

=======
Methods
=======

.. _project.addPropertyToProjectMetadataSchema:

Project.addPropertyToProjectMetadataSchema()
*********************************************

``app.project.addPropertyToProjectMetadataSchema(propertyName, propertyLabel, propertyType)``

**Description**

Adds a new field of the specified type to Premiere Pro's private project metadata schema.

**Parameters**

=================  ===========  =======================
Argument           Type         Description
=================  ===========  =======================
``propertyName``   ``String``   A name of property to be added. 
``propertyLabel``  ``String``   A label of property to be added.
``propertyType``                Must be one of the following:

                                - 0 ``Integer``
                                - 1 ``Real``
                                - 2 ``String``
                                - 3 ``Boolean``
=================  ===========  =======================

**Returns**

Returns **true** if successful, **undefined** if unsuccessful.

----

.. _project.closeDocument:

Project.closeDocument()
*********************************************

``app.project.closeDocument(saveFirst, promptIfDirty)``

**Description**

Closes this project.

**Parameters**

=================  ===========  =======================
Argument           Type         Description
=================  ===========  =======================
``saveFirst``      ``Integer``  If ``1``, the project will be saved before closing.
``promptIfDirty``  ``Integer``  If ``1``, the user will be asked whether they want to save changes first.
=================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _project.consolidateDuplicates:

Project.consolidateDuplicates()
*********************************************

``app.project.consolidateDuplicates()``

**Description**

Invokes Premiere Pro's "Consolidate Duplicate Footage" functionality, as available from the UI.

**Parameters**

None.

**Returns**

Returns  **0** if successful.

----

.. _project.createNewSequence:

Project.createNewSequence()
*********************************************

``app.project.createNewSequence(sequenceName, sequenceID)``

**Description**

Creates a new :ref:`sequence` with the specified ID.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``sequenceName``  ``String``   A name of a sequence.
``sequenceID``    ``String``   An uniquely identifying ID for a new sequence.
================  ===========  =======================

**Returns**

Returns a :ref:`sequence` if creation was successful, or **0** if unsuccessful.

----

.. _project.createNewSequenceFromClips:

Project.createNewSequenceFromClips()
*****************************************************************************

``app.project.createNewSequenceFromClips(sequenceName, arrayOfProjectItems, destinationBin);``

**Description**

Creates a new :ref:`sequence` with the given name, in the specified destination bin, and sequentially inserts project items into it.

**Parameters**

=======================  =====================================================  =======================
Argument                 Type                                                   Description
=======================  =====================================================  =======================
``sequenceName``         ``String``                                             Optional. A name for a new sequence.
``arrayOfProjectItems``  ``Array`` of :ref:`ProjectItem <projectItem>` objects  An array of project items to be inserted into sequence.
``destinationBin``       :ref:`projectItem`                                     Optional. A bin to contain sequence. 
=======================  =====================================================  =======================

**Returns**

Returns the newly-created :ref:`sequence` if successful; `0` if unsuccessful.

----

.. _project.deleteSequence:

Project.deleteSequence()
*********************************************

``app.project.deleteSequence(sequence)``

**Description**

Deletes the specified :ref:`sequence` from the project.

**Parameters**

================  ===============  =======================
Argument          Type             Description
================  ===============  =======================
``sequence``      :ref:`sequence`  A sequence to delete.
================  ===============  =======================

**Returns**

Returns 0 if successful.

----

.. _project.exportAAF:

Project.exportAAF()
*********************************************

``app.project.exportAAF(sequenceToExport, outputPath, mixdownVideo, explodeToMono, sampleRate, bitsPerSample, embedAudio, audioFileFormat, trimSources, handleFrames, presetPath, renderAudioEffects, includeClipCopies, preserveParentFolder)``

**Description**

Exports an AAF file of the specified :ref:`sequence`, using the specified settings.

**Parameters**

========================  =================  =======================
Argument                  Type               Description
========================  =================  =======================
``sequence``              :ref:`sequence`    A sequence to export.
``filePath``              ``String``         An output path for .aaf file. 
``mixdownVideo``          ``Integer``        If ``1``, render video before export. 
``explodeToMono``         ``Integer``        If ``1``, breaks out stereo tracks to mono.
``sampleRate``                               The sample rate of output audio. 
``bitsPerSample``                            The bits per sample of audio output. 
``embedAudio``            ``Integer``        If ``1``, audio is embedded, if ``0``, external.
``audioFileFormat``       ``Integer``        ``0`` is AIFF, ``1`` is WAV.  
``trimSources``           ``Integer``        If ``1``, trim audio files before export. 
``handleFrames``          ``Integer``        The number of handle frames (from 0 to 1000).
``presetPath``            ``String``         A path to export preset (.epr) file. 
``renderAudioEffects``    ``Integer``        If ``1``, render audio effects before export.
``includeClipCopies``     ``Integer``        If ``1``, include each copy of a clip. 
``preserveParentFolder``  ``Integer``        If ``1``, preserves the parent folder, in output. 
========================  =================  =======================

**Returns**

Returns **0** if successful.

----

.. _project.exportFinalCutProXML:

Project.exportFinalCutProXML()
*********************************************

``app.project.exportFinalCutProXML(outputPath, suppressUI)``

**Description**

Exports an FCP XML representation of the entire project, to the specified output path.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``outputPath``    ``String``   An output path for .xml file.
``suppressUI``    ``Integer``  If ``1``, no warnings or alerts will be shown, during the export.
================  ===========  =======================

**Returns**

Returns 0 if successful.

----

.. _project.exportOMF:

Project.exportOMF()
*********************************************

``app.project.exportOMF(sequence, outputPath, omfTitle, sampleRate, bitsPerSample, audioEncapsulated, audioFileFormat, trimAudioFiles, handleFrames, includePan)``

**Description**

Exports an OMF file of the specified :ref:`sequence`, using the specified settings.

**Parameters**

======================  =================  =======================
Argument                Type               Description
======================  =================  =======================
``sequence``            :ref:`sequence`    The sequence to be output. 
``filePath``            ``String``         An output path for .omf file.
``omfTitle``            ``String``         The title of the OMF.
``sampleRate``                             The sample rate of output audio. 
``bitsPerSample``                          The bits per sample of audio output. 
``audioEncapsulated``   ``Integer``        If ``1``, audio is embedded, if ``0``, external. 
``audioFileFormat``     ``Integer``        ``0`` is AIFF, ``1`` is WAV.
``trimAudioFiles``      ``Integer``        ``1`` means yes, trim audio files. 
``handleFrames``        ``Integer``        Number of handle frames (from 0 to 1000). 
``includePan``          ``Integer``        ``1`` means include pan info; ``0`` means don't. 
======================  =================  =======================

**Returns**

Returns **0** if successful.

----

.. _project.exportTimeline:

Project.exportTimeline()
*********************************************

``app.project.exportTimeline(exportControllerName)``

**Description**

Exports the currently active :ref:`sequence`, using an Export Controller plug-in with the specified name.

**Parameters**

=========================  ===========  =======================
Argument                   Type         Description
=========================  ===========  =======================
``exportControllerName``   ``String``   The name of the Export Controller plug-in to be used. To use the Premiere Pro SDK example Export Controller, the value would be "SDK Export Controller".
=========================  ===========  =======================

**Returns**

Returns **0** if successful, or an error code if not.

----

.. _project.getGraphicsWhiteLuminance:

Project.getGraphicsWhiteLuminance()
*****************************************************************************

``app.project.getGraphicsWhiteLuminance();``

**Description**

Retrieves the current graphics white luminance value, for this project.

**Parameters**

None.

**Returns**

Returns the currently selected graphics white value.

----

.. _project.getInsertionBin:

Project.getInsertionBin()
*********************************************

``app.project.getInsertionBin()``

**Description**

Returns a :ref:`projectItem` referencing the bin into which import will occur.

**Parameters**

None.

**Returns**

Returns a :ref:`projectItem` if successful, **0** if not.

----

.. _project.getProjectPanelMetadata:

Project.getProjectPanelMetadata()
*********************************************

``app.project.getProjectPanelMetadata()``

**Description**

Returns the current layout of the Project panel.

**Parameters**

None.

**Returns**

Returns a **String** representing the current Project panel layout, or **0** if unsuccessful.

----

.. _project.getSharedLocation:

Project.getSharedLocation()
*********************************************

``app.project.getSharedLocation()``

**Description**

Returns the path to the location to which shared files are to be copied.

**Parameters**

None.

**Returns**

Returns a **String** containing the path.

----

.. _project.getSupportedGraphicsWhiteLuminances:

Project.getSupportedGraphicsWhiteLuminances()
*****************************************************************************

``app.project.getSupportedGraphicsWhiteLuminances();``

**Description**

Retrieves the supported graphics white luminance values, for this project.

**Parameters**

None.

**Returns**

Returns an array of graphics white settings supported by the project; Currently it returns (100, 203, 300)

----

.. _project.importAEComps:

Project.importAEComps()
*********************************************

``app.project.importAEComps(path, compNames, targetBin)``

**Description**

Imports specified Compositions (by name) from the containing After Effects .aep project file. You can specify a target bin within the containing project; otherwise, the Compositions will appear in the most recently targeted bin, within this project.

**Parameters**

======================  ===================  =======================
Argument                Type                 Description
======================  ===================  =======================
``path``                ``String``           A path to the After Effects .aep project file.
``compNames``           ``Array``            Names of compositions within the specified project, to be imported.
``targetBin``           :ref:`projectItem`   Optional. The destination bin for this import.
======================  ===================  =======================

**Returns**

Returns **0** if successful.

----

.. _project.importAllAEComps:

Project.importAllAEComps()
*********************************************

``app.project.importAllAEComps(path, targetBin)``

**Description**

Imports specified Compositions (by name) from the containing After Effects .aep project file. You can specify a target bin within the containing project; otherwise, the Compositions will appear in the most recently targeted bin, within this project.

**Parameters**

================  ==================  =======================
Argument          Type                Description
================  ==================  =======================
``path``          ``String``          A path to After Effects .aep project file.
``targetBin``     :ref:`projectItem`  Optional. The destination bin for this import.
================  ==================  =======================

**Returns**

Returns **0** if successful.

----

.. _project.importFiles:

Project.importFiles()
*********************************************

``app.project.importFiles(filePaths, suppressUI, targetBin, importAsNumberedStills)``

**Description**

Imports media from the specified file paths.

**Parameters**

============================  ==================  =======================
Argument                      Type                Description
============================  ==================  =======================
``filePaths``                 ``Array``           An array of the file paths to be imported.
``suppressUI``                ``Boolean``         Whether warning dialogs should be suppressed.
``targetBin``                 :ref:`projectItem`  The bin into which the files should be imported.
``importAsNumberedStills``    ``Boolean``         Whether the file paths should be interpreted as a sequence of numbered stills.
============================  ==================  =======================

**Returns**

Returns **true** if successful, **false** if not.

----

.. _project.importSequences:

Project.importSequences()
*********************************************

``app.project.importSequences(path, sequenceIDs)``

**Description**

Imports an array of :ref:`sequence <sequence>` objects (with specified sequenceIDs), from the specified project, into the current project.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``path``          ``String``   A path to a project file.
``sequenceIDs``   ``Array``    An array of sequence IDs to import.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _project.isSharedLocationCopyEnabled:

Project.isSharedLocationCopyEnabled()
*********************************************

``app.project.isSharedLocationCopyEnabled()``

**Description**

Determines whether copying to a shared location is enabled, for this project.

**Parameters**

None.

**Returns**

Returns  **true** if copying is enabled; **false** if not.

----

.. _project.newBarsAndTone:

Project.newBarsAndTone()
**************************************************

``app.project.newBarsAndTone(width, height, timeBase, PARNum, PARDen, audioSampleRate, name)``

**Description**

Creates a new :ref:`sequence` with the given name, based on the specified preset (.sqpreset file).

**Parameters**

====================  ===========  =======================
Argument              Type         Description
====================  ===========  =======================
``width``             ``Integer``   
``height``            ``Integer``   
``timeBase``                       A timebase for a new project item.
``PARNum``            ``Integer``  Pixel aspect ration numerator. 
``PARDen``            ``Integer``  Pixel aspect ration denominator. 
``audioSampleRate``                Audio sample rate. 
``name``              ``String``   Name for a new project item. 
====================  ===========  =======================

**Returns**

Returns a :ref:`projectItem` for the new bars and tone, or **0** if unsuccessful.

----

.. _project.newSequence:

Project.newSequence()
***********************************************

``app.project.newSequence(name, pathToSequencePreset)``

**Description**

Creates a new :ref:`sequence` with the given name, based on the specified preset (.sqpreset file).

**Parameters**

=========================  ===========  =======================
Argument                   Type         Description
=========================  ===========  =======================
``name``                   ``String``   Name for a new sequence. 
``pathToSequencePreset``   ``String``   A path to a preset .sqpreset file. 
=========================  ===========  =======================

**Returns**

Returns a :ref:`sequence`, or **0** if unsuccessful.

----

.. _project.openSequence:

Project.openSequence()
*********************************************

``app.project.openSequence(sequence.sequenceID)``

**Description**

Makes the :ref:`sequence` with the provided sequence ID, active. This will open the sequence in the Timeline panel.

**Parameters**

================  ===========================  =======================
Argument          Type                         Description
================  ===========================  =======================
``sequenceID``    :ref:`sequence.sequenceID`   A valid sequence ID that should be opened.
================  ===========================  =======================

**Returns**

Returns **true** if successful, **false** if not.

----

.. _project.pauseGrowing:

Project.pauseGrowing()
*********************************************

``app.project.pauseGrowing(pause)``

**Description**

Pauses (and resumes) growing file capture.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``pause``         ``Integer``  If ``1``, growing files are enabled.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _project.save:

Project.save()
*********************************************

``app.project.save()``

**Description**

Saves the project, at its current path.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _project.saveAs:

Project.saveAs()
*********************************************

``app.project.saveAs(path)``

**Description**

Exports the current project to a new unique file path, opens the project from the new location, and closes the previously-opened (and identical) project.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``path``          ``String``   A path to a new file.
================  ===========  =======================

**Returns**

Returns **0** if successful, or an error code if not.

----

.. _project.setEnableTranscodeOnIngest:

Project.setEnableTranscodeOnIngest()
*****************************************************************************

``app.project.setEnableTranscodeOnIngest(state);``

**Description**

Controls the enablement of transcode-upon-ingest behavior, for the given project.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``state``         ``Boolean``  The desired state.
================  ===========  =======================

**Returns**

Returns **true** if successful.

----

.. _project.setGraphicsWhiteLuminance:

Project.setGraphicsWhiteLuminance()
*****************************************************************************

``app.project.setGraphicsWhiteLuminance(value)``

**Description**

Sets the current graphics white luminance value, for this project. 

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``value``         ``Integer``  The value to be used; must be a value provided by :ref:`project.getSupportedGraphicsWhiteLuminances`.
================  ===========  =======================

**Returns**

Returns true if successful.

----

.. _project.setProjectPanelMetadata:

Project.setProjectPanelMetadata()
*********************************************

``app.project.setProjectPanelMetadata(layout)``

**Description**

Returns the current layout of the Project panel.

**Parameters**

=========================  ===========  =======================
Argument                   Type         Description
=========================  ===========  =======================
``layout``                 ``String``   Represents the desired Project panel layout. Note: The only known method for generating a valid layout string, is setting the Project panel as desired then using :ref:`project.getProjectPanelMetadata`.
=========================  ===========  =======================

**Returns**

Returns  **0** if unsuccessful.

----

.. _project.setScratchDiskPath:

Project.setScratchDiskPath()
*********************************************

``app.project.setScratchDiskPath(newPath, whichScratchDiskPath)``

**Description**

Changes the specified scratch disk path to a new path.

**Parameters**

=========================  ===========  =======================
Argument                   Type         Description
=========================  ===========  =======================
``newPath``                ``String``   A new path.
``whichScratchDiskPath``                Must be one of the following: 

                                        - ``ScratchDiskType.FirstVideoCaptureFolder`` 
                                        - ``ScratchDiskType.FirstAudioPreviewFolder``
                                        - ``ScratchDiskType.FirstAutoSaveFolder`` 
                                        - ``ScratchDiskType.FirstCCLibrariesFolder`` 
                                        - ``ScratchDiskType.FirstAudioCaptureFolder``
=========================  ===========  =======================

**Returns**

Returns  **0** if unsuccessful.
