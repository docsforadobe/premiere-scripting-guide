.. highlight:: javascript

.. _ProjectManager:

ProjectManager object
==========================

``ProjectManager``

**Description**

The ProjectManager object exposes Premiere Pro's Project Manager, for project consolidation, transfer and transcoding.

----

==========
Attributes
==========

.. _ProjectManager.affectedSequences:

affectedSequences
*********************************************

``ProjectManager.affectedSequences``

**Description**

An `Array` of `Sequence` objects, to be exported.

**Type**

Array; read-write.

----

.. _ProjectManager.clipTranscoderOption:

clipTranscoderOption
*********************************************

``ProjectManager.clipTranscoderOption``

**Description**

The specified setting for clip transcode. Value will be one of the following:

+-----------------------------------+---------------------------------------------------+
| ``CLIP_TRANSCODE_MATCH_PRESET``   | Transcode using the specified preset.             |
+-----------------------------------+---------------------------------------------------+
| ``CLIP_TRANSCODE_MATCH_CLIPS``    | Match the clips                                   |
+-----------------------------------+---------------------------------------------------+
| ``CLIP_TRANSCODE_MATCH_SEQUENCE`` | Must be one of the following:                     |
+----------------------------+----------------------------------------------------------+

**Type**

String; read/write.

----

.. _ProjectManager.clipTransferOption:

clipTransferOption
*********************************************

``ProjectManager.clipTransferOption``

**Description**

The specified setting for clip transfer. Value will be one of the following:

+-----------------------------------+---------------------------------------------------+
| ``CLIP_TRANSFER_COPY``            | Copy entire source media.                         |
+-----------------------------------+---------------------------------------------------+
| ``CLIP_TRANSFER_TRANSCODE``       | Transcode to default output format.               |
+-----------------------------------+---------------------------------------------------+

----

.. _ProjectManager.convertAECompsToClips:

convertAECompsToClips
*********************************************

``ProjectManager.convertAECompsToClips``

**Description**

If `true`, render dynamically-linked After Effects compositions to new media (using specified output preset).

**Type**

Boolean; read/write.

----

.. _ProjectManager.convertImageSequencesToClips:

convertImageSequencesToClips
*********************************************

``ProjectManager.convertImageSequencesToClips``

**Description**

If `true`, transcode image sequences to new media (using specified output preset).

**Type**

Boolean; read/write.

----

.. _ProjectManager.convertSyntheticsToClips:

convertSyntheticsToClips
*********************************************

``ProjectManager.convertSyntheticsToClips``

**Description**

If `true`, transcode clips from synthetic importers to new media (using specified output preset).

**Type**

Boolean; read/write.

----

.. _ProjectManager.copyToPreventAlphaLoss:

copyToPreventAlphaLoss
*********************************************

``ProjectManager.copyToPreventAlphaLoss``

**Description**

If `true`, includes any available alpha information into transcoded media.

**Type**

Boolean; read/write.

----

.. _ProjectManager.destinationPath:

destinationPath
*********************************************

``ProjectManager.destinationPath``

**Description**

The path to which to export the project and media.

**Type**

String; read/write.

----

.. _ProjectManager.encoderPresetFilePath:

encoderPresetFilePath
*********************************************

``ProjectManager.encoderPresetFilePath``

**Description**

The path to the output preset (.epr file) to be used.

**Type**

String; read-write.

----

.. _ProjectManager.excludeUnused:

excludeUnused
*********************************************

``ProjectManager.excludeUnused``

**Description**

If non-zero, exclude unused project items from the exported project.

**Type**

Boolean; read/write.

----

.. _ProjectManager.handleFrameCount:

handleFrameCount
*********************************************

``ProjectManager.handleFrameCount``

**Description**

How many frames of 'handle' footage (before and after the in and out points) of media, to include.

**Type**

Integer; read/write.

----

.. _ProjectManager.includeAllSequences:

includeAllSequences
*********************************************

``ProjectManager.includeAllSequences``

**Description**

If `true`, export all sequences in the exported project.

**Type**

Boolean; read/write.

----

.. _ProjectManager.includeConformedAudio:

includeConformedAudio
*********************************************

``ProjectManager.includeConformedAudio``

**Description**

If `true`, include conformed audio files with exported project.

**Type**

Boolean; read/write.

----

.. _ProjectManager.includePreviews:

includePreviews
*********************************************

``ProjectManager.includePreviews``

**Description**

If `true`, include rendered preview files with exported project.

**Type**

Boolean; read/write.

----

.. _ProjectManager.renameMedia:

renameMedia
*********************************************

``ProjectManager.renameMedia``

**Description**

If `true`, perform renaming as part of the export process.

**Type**

Boolean; read/write.

----

=======
Methods
=======

.. _ProjectManager.closeClip:

closeClip
*********************************************

``source.closeClip()``

**Description**

Closes the front-most clip in the Source monitor.

**Parameters**

None.

**Returns**

Returns **0** if successful.
