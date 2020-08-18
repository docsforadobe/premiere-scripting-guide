.. highlight:: javascript

.. _project:

Project object
===================

``project``

**Description**

Represents a Premiere Pro project. As of Premiere Pro 12.0, multiple projects may be open at the same time.

----

==========
Attributes
==========

.. _project.activeSequence:

Project.activeSequence
*********************************************

``project.activeSequence``

**Description**

The currently active :ref:`sequence`, within the project.

**Type**

a :ref:`sequence`, or ``0`` if no sequence is currently active.

----

.. _project.documentID:

Project.documentID
*********************************************

``project.documentID``

**Description**

A read-only unique identifier for this project.

**Type**

GUID; read-only.

----

.. _project.name:

Project.name
*********************************************

``project.name``

**Description**

The name of the project.

**Type**

String; read-only.

----

.. _project.path:

Project.path
*********************************************

``project.path``

**Description**

The file path of the project.

**Type**

String; read-only.

----

.. _project.rootItem:

Project.rootItem
*********************************************

``project.rootItem``

**Description**

A :ref:`projectItem` representing the "root" of the project.

**Type**

A :ref:`projectItem`; this will always be of type ``ProjectItemType_BIN``.

----

.. _project.sequences:

Project.sequences
*********************************************

``project.sequences``

**Description**

The sequences within the project.

**Type**

An array of :ref:`Sequence <sequence>` objects.

----

=======
Methods
=======

.. _project.addPropertyToProjectMetadataSchema:

Project.addPropertyToProjectMetadataSchema()
*********************************************

``project.addPropertyToProjectMetadataSchema(propertyName, propertyLabel, propertyType)``

**Description**

Adds a new field of the specified type to Premiere Pro's private project metadata schema.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``propertyName``           | **String**, Name of property to be added.         |
+----------------------------+---------------------------------------------------+
| ``propertyLabel``          | **String**, Label of property to be added.        |
+----------------------------+---------------------------------------------------+
| ``propertyType``           | Must be one of the following:                     |
|                            |    - 0 Integer                                    |
|                            |    - 1 Real                                       |
|                            |    - 2 String                                     |
|                            |    - 3 Boolean                                    |
+----------------------------+---------------------------------------------------+

**Returns**

Returns **true** if successful, **undefined** if unsuccessful.

----

.. _project.closeDocument:

Project.closeDocument()
*********************************************

``project.closeDocument(saveFirst, promptIfDirty)``

**Description**

Closes this project.

**Parameters**

Two **ints**; If **saveFirst** is 1, the project will be saved before closing. If **promptIfDirty** is 1, the user will be asked whether they want to save changes first.

**Returns**

Returns **0** if successful.

----

.. _project.consolidateDuplicates:

Project.consolidateDuplicates()
*********************************************

``project.consolidateDuplicates()``

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

``project.createNewSequence(sequenceName, sequenceID)``

**Description**

Creates a new :ref:`sequence` with the specified ID.

**Parameters**

*String* name of sequence.

*GUID* uniquely identifying this sequence.

**Returns**

Returns a :ref:`sequence` if creation was successful, or **0** if unsuccessful.

----

.. _project.createNewSequenceFromClips:

Project.createNewSequenceFromClips()
*****************************************************************************

``project.createNewSequenceFromClips(sequenceName, arrayOfProjectItems, destinationBin);``

**Description**

Creates a new :ref:`sequence` with the given name, in the specified destination bin, and sequentially inserts project items into it.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``sequenceName``           | Optional; Name of created sequence.               |
+----------------------------+---------------------------------------------------+
| ``arrayOfProjectItems``    | Array of projectItems to be inserted in sequence. |
+----------------------------+---------------------------------------------------+
| ``destinationBin``         | Optional; bin to contain sequence.                |
+----------------------------+---------------------------------------------------+

**Returns**

Returns the newly-created :ref:`sequence` if successful; `0` if unsuccessful.

----

.. _project.deleteSequence:

Project.deleteSequence()
*********************************************

``project.deleteSequence(sequenceToDelete)``

**Description**

Deletes the specified :ref:`sequence` from the project.

**Parameters**

The :ref:`sequence` to delete.

**Returns**

Returns 0 if successful.

----

.. _project.exportAAF:

Project.exportAAF()
*********************************************

``project.exportAAF(sequenceToExport, outputPath, mixdownVideo, explodeToMono, sampleRate, bitsPerSample, embedAudio, audioFileFormat, trimSources, handleFrames, presetPath, renderAudioEffects, includeClipCopies, preserveParentFolder)``

**Description**

Exports an AAF file of the specified :ref:`sequence`, using the specified settings.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``sequence``               | Specifies the sequence to be output.              |
+----------------------------+---------------------------------------------------+
| ``filePath``               | Complete output path for .aaf file.               |
+----------------------------+---------------------------------------------------+
| ``mixdownVideo``           | If **1**, render video before export.             |
+----------------------------+---------------------------------------------------+
| ``explodeToMono``          | If **1**, breaks out stereo tracks to mono.       |
+----------------------------+---------------------------------------------------+
| ``sampleRate``             | Specifies the sample rate of output audio.        |
+----------------------------+---------------------------------------------------+
| ``bitsPerSample``          | Specifies the bits per sample of audio output.    |
+----------------------------+---------------------------------------------------+
| ``embedAudio``             | If **1**, audio is embedded, if **0**, external.  |
+----------------------------+---------------------------------------------------+
| ``audioFileFormat``        | **0** is AIFF, **1** is WAV.                      |
+----------------------------+---------------------------------------------------+
| ``trimSources``            | If **1**, trim audio files before export.         |
+----------------------------+---------------------------------------------------+
| ``handleFrames``           | Number of handle frames (from 0 to 1000).         |
+----------------------------+---------------------------------------------------+
| ``presetPath``             | Complete path to Export preset (.epr file).       |
+----------------------------+---------------------------------------------------+
| ``renderAudioEffects``     | If **1**, render audio effects before export.     |
+----------------------------+---------------------------------------------------+
| ``includeClipCopies``      | If **1**, include each copy of a clip.            |
+----------------------------+---------------------------------------------------+
| ``preserveParentFolder``   | If **1**, preserves the parent folder, in output. |
+----------------------------+---------------------------------------------------+

**Returns**

Returns **0** if successful.

----

.. _project.exportFinalCutProXML:

Project.exportFinalCutProXML()
*********************************************

``project.exportFinalCutProXML(outputPath, suppressUI)``

**Description**

Exports an FCP XML representation of the entire project, to the specified output path.

**Parameters**

Full output path of .xml file, as a *String*.

The suppressUI param is an *Int*; if **1**, no warnings or alerts will be shown, during the export.

**Returns**

Returns 0 if successful.

----

.. _project.exportOMF:

Project.exportOMF()
*********************************************

``project.exportOMF(sequence, outputPath, omfTitle, sampleRate, bitsPerSample, audioEncapsulated, audioFileFormat, trimAudioFiles, handleFrames, includePan)``

**Description**

Exports an OMF file of the specified :ref:`sequence`, using the specified settings.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``sequence``               | Specifies the sequence to be output.              |
+----------------------------+---------------------------------------------------+
| ``filePath``               | Complete output path for .omf file.               |
+----------------------------+---------------------------------------------------+
| ``omfTitle``               | **String** with which to title the OMF.           |
+----------------------------+---------------------------------------------------+
| ``sampleRate``             | Specifies the sample rate of output audio.        |
+----------------------------+---------------------------------------------------+
| ``bitsPerSample``          | Specifies the bits per sample of audio output.    |
+----------------------------+---------------------------------------------------+
| ``audioEncapsulated``      | If **1**, audio is embedded, if **0**, external.  |
+----------------------------+---------------------------------------------------+
| ``audioFileFormat``        | **0** is AIFF, **1** is WAV.                      |
+----------------------------+---------------------------------------------------+
| ``trimAudioFiles``         | **1** means yes, trim audio files.                |
+----------------------------+---------------------------------------------------+
| ``handleFrames``           | Number of handle frames (from 0 to 1000).         |
+----------------------------+---------------------------------------------------+
| ``includePan``             | **1** means include pan info; **0** means don't.  |
+----------------------------+---------------------------------------------------+

**Returns**

Returns **0** if successful.

----

.. _project.exportTimeline:

Project.exportTimeline()
*********************************************

``project.exportTimeline(exportControllerName)``

**Description**

Exports the currently active :ref:`sequence`, using an Export Controller plug-in with the specified name.

**Parameters**

A **String** containing the name of the Export Controller plug-in to be used. To use the Premiere Pro SDK example Export Controller, the value would be "SDK Export Controller".

**Returns**

Returns **0** if successful, or an error code if not.

----

.. _project.getGraphicsWhiteLuminance:

Project.getGraphicsWhiteLuminance()
*****************************************************************************

``project.getGraphicsWhiteLuminance();``

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

``project.getInsertionBin()``

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

``project.getProjectPanelMetadata()``

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

``project.getSharedLocation()``

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

``project.getSupportedGraphicsWhiteLuminances();``

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

``project.importAEComps(pathOfContainingProject, arrayOfCompNames, optionalTargetBin)``

**Description**

Imports specified Compositions (by name) from the containing After Effects .aep project file. You can specify a target bin within the containing project; otherwise, the Compositions will appear in the most recently targeted bin, within this project.

**Parameters**

*String* containing the full path to the containing project file, and an *Array* of sequenceIDs.

*Array* of names of Compositions within the specified project, to be imported.

*projectItem* referencing the destination bin for this import.

**Returns**

Returns **0** if successful.

----

.. _project.importAllAEComps:

Project.importAllAEComps()
*********************************************

``project.importAllAEComps(pathOfContainingProject, optionalTargetBin)``

**Description**

Imports specified Compositions (by name) from the containing After Effects .aep project file. You can specify a target bin within the containing project; otherwise, the Compositions will appear in the most recently targeted bin, within this project.

**Parameters**

*String* containing the full path to the containing project file.

*projectItem* referencing the destination bin for this import.

**Returns**

Returns **0** if successful.

----

.. _project.importFiles:

Project.importFiles()
*********************************************

``project.importFiles(arrayOfFilePathsToImport, suppressUI, targetBin, importAsNumberedStills)``

**Description**

Imports media from the specified file paths.

**Parameters**

An ``array`` of full, platform-specific file paths to be imported, a ``boolean`` indicating whether warning dialogs should be suppressed, a :ref:`projectItem` for the bin into which the files should be imported, and a ``boolean`` indicating whether the file paths should be interpreted as a sequence of numbered stills.

**Returns**

Returns **true** if successful, **false** if not.

----

.. _project.importSequences:

Project.importSequences()
*********************************************

``project.importSequences(pathOfContainingProject, arrayOfSequenceIDs)``

**Description**

Imports an array of :ref:`sequence <sequence>` objects (with specified sequenceIDs), from the specified project, into the current project.

**Parameters**

*String* containing the full path to the containing project file, and an *Array* of sequenceIDs.

**Returns**

Returns **0** if successful.

----

.. _project.isSharedLocationCopyEnabled:

Project.isSharedLocationCopyEnabled()
*********************************************

``project.isSharedLocationCopyEnabled()``

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

``project.newBarsAndTone(width, height, timeBase, PARNum, PARDen, audioSampleRate, name);``

**Description**

Creates a new :ref:`sequence` with the given name, based on the specified preset (.sqpreset file).

**Parameters**

+----------------------------+---------------------------------------------------+
| ``width``                  |                                                   |
+----------------------------+---------------------------------------------------+
| ``height``                 |                                                   |
+----------------------------+---------------------------------------------------+
| ``timeBase``               | Timebase of new project item. One of these:       |
+----------------------------+---------------------------------------------------+
| ``PARNum``                 | Pixel aspect ration numerator.                    |
+----------------------------+---------------------------------------------------+
| ``PARDen``	             | Pixel aspect ration denominator.                  |
+----------------------------+---------------------------------------------------+
| ``audioSampleRate``        | audio sample rate.                                |
+----------------------------+---------------------------------------------------+
| ``name``                   | **String**, Name of new project item.             |
+----------------------------+---------------------------------------------------+

**Returns**

Returns a :ref:`projectItem` for the new bars and tone, or **0** if unsuccessful.

----

.. _project.newSequence:

Project.newSequence()
***********************************************

``project.newSequence(sequenceName, pathToSequencePreset)``

**Description**

Creates a new :ref:`sequence` with the given name, based on the specified preset (.sqpreset file).

**Parameters**

+----------------------------+---------------------------------------------------+
| ``sequenceName``           | **String**, Name of new sequence.                 |
+----------------------------+---------------------------------------------------+
| ``pathToSequencePreset``   | **String**, path to .sqpreset file.               |
+----------------------------+---------------------------------------------------+

**Returns**

Returns a :ref:`sequence`, or **0** if unsuccessful.

----

.. _project.openSequence:

Project.openSequence()
*********************************************

``project.openSequence(sequenceID)``

**Description**

Makes the :ref:`sequence` with the provided sequence ID, active. This will open the sequence in the Timeline panel.

**Parameters**

A valid ``sequenceID``.

**Returns**

Returns **true** if successful, **false** if not.

----

.. _project.pauseGrowing:

Project.pauseGrowing()
*********************************************

``project.pauseGrowing(pausedOrNot)``

**Description**

Pauses (and resumes) growing file capture.

**Parameters**

An **int**; if 1, growing files are enabled.

**Returns**

Returns **0** if successful.

----

.. _project.save:

Project.save()
*********************************************

``project.save()``

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

``project.saveAs(pathToNewProject)``

**Description**

Exports the current project to a new unique file path, opens the project from the new location, and closes the previously-opened (and identical) project.

**Parameters**

A **String** specifying the new path.

**Returns**

Returns **0** if successful, or an error code if not.

----

.. _project.setEnableTranscodeOnIngest:

Project.setEnableTranscodeOnIngest()
*****************************************************************************

``project.setEnableTranscodeOnIngest(FirstAutoSaveFolder);``

**Description**

Controls the enablement of transcode-upon-ingest behavior, for the given project.

**Parameters**

A Boolean indicating the desired state.

**Returns**

Returns **true** if successful.

----

.. _project.setGraphicsWhiteLuminance:

Project.setGraphicsWhiteLuminance()
*****************************************************************************

``project.setGraphicsWhiteLuminance(newValue);``

**Description**

Sets the current graphics white luminance value, for this project. 

**Parameters**

An integer specifying the value to be used; must be a value provided by ``getSupportedGraphicsWhiteLuminances()``.

**Returns**

Returns true if successful.

----

.. _project.setProjectPanelMetadata:

Project.setProjectPanelMetadata()
*********************************************

``project.setProjectPanelMetadata(updatedLayoutAsString)``

**Description**

Returns the current layout of the Project panel.

**Parameters**

**updatedLayoutAsString** represents the desired Project panel layout. Note: The only known method for generating a valid layout string, is setting the Project panel as desired then using project.getProjectPanelMetadata_.

**Returns**

Returns  **0** if unsuccessful.

----

.. _project.setScratchDiskPath:

Project.setScratchDiskPath()
*********************************************

``project.setScratchDiskPath(newPath, whichScratchDiskPath)``

**Description**

Changes the specified scratch disk path to a new path.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``newPath``                | New path value.                                   |
+----------------------------+---------------------------------------------------+
| ``whichScratchDiskPath``   | Must be one of the following:                     |
|                            |  - ``ScratchDiskType.FirstVideoCaptureFolder``    |
|                            |  - ``ScratchDiskType.FirstAudioPreviewFolder``    |
|                            |  - ``ScratchDiskType.FirstAutoSaveFolder``        |
|                            |  - ``ScratchDiskType.FirstCCLibrariesFolder``     |
|                            |  - ``ScratchDiskType.FirstVideoCaptureFolder``    |
|                            |  - ``ScratchDiskType.FirstAudioCaptureFolder``    |
+----------------------------+---------------------------------------------------+

**Returns**

Returns  **0** if unsuccessful.
