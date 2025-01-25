# ProjectManager object

`app.projectManager.options`

**Description**

The ProjectManager object exposes Premiere Pro’s Project Manager, for project consolidation, transfer and transcoding.

---

## Attributes

### ProjectManager.affectedSequences

`app.projectManager.options.affectedSequences`

**Description**

An Array of [Sequence](../sequence/sequence.md#sequence) objects, to be exported.

**Type**

Array; read/write.

---

### ProjectManager.clipTranscoderOption

`app.projectManager.options.clipTranscoderOption`

**Description**

The specified setting for clip transcode. Value will be one of the following:

| `CLIP_TRANSCODE_MATCH_PRESET`                                   | Transcode using the specified preset.   |
|-----------------------------------------------------------------|-----------------------------------------|
| `CLIP_TRANSCODE_MATCH_CLIPS`                                    | Match the clips                         |
| `CLIP_TRANSCODE_MATCH_SEQUENCE` | Must be one of the following: |                                         |

**Type**

String; read/write.

---

### ProjectManager.clipTransferOption

`app.projectManager.options.clipTransferOption`

**Description**

The specified setting for clip transfer. Value will be one of the following:

| `CLIP_TRANSFER_COPY`      | Copy entire source media.           |
|---------------------------|-------------------------------------|
| `CLIP_TRANSFER_TRANSCODE` | Transcode to default output format. |

---

### ProjectManager.convertAECompsToClips

`app.projectManager.options.convertAECompsToClips`

**Description**

If true, render dynamically-linked After Effects compositions to new media (using specified output preset).

**Type**

Boolean; read/write.

---

### ProjectManager.convertImageSequencesToClips

`app.projectManager.options.convertImageSequencesToClips`

**Description**

If true, transcode image sequences to new media (using specified output preset).

**Type**

Boolean; read/write.

---

### ProjectManager.convertSyntheticsToClips

`app.projectManager.options.convertSyntheticsToClips`

**Description**

If true, transcode clips from synthetic importers to new media (using specified output preset).

**Type**

Boolean; read/write.

---

### ProjectManager.copyToPreventAlphaLoss

`app.projectManager.options.copyToPreventAlphaLoss`

**Description**

If true, includes any available alpha information into transcoded media.

**Type**

Boolean; read/write.

---

### ProjectManager.destinationPath

`app.projectManager.options.destinationPath`

**Description**

The path to which to export the project and media.

**Type**

String; read/write.

---

### ProjectManager.encoderPresetFilePath

`app.projectManager.options.encoderPresetFilePath`

**Description**

The path to the output preset (.epr file) to be used.

**Type**

String; read-write.

---

### ProjectManager.excludeUnused

`app.projectManager.options.excludeUnused`

**Description**

If non-zero, exclude unused project items from the exported project.

**Type**

Boolean; read/write.

---

### ProjectManager.handleFrameCount

`app.projectManager.options.handleFrameCount`

**Description**

How many frames of ‘handle’ footage (before and after the in and out points) of media, to include.

**Type**

Integer; read/write.

---

### ProjectManager.includeAllSequences

`app.projectManager.options.includeAllSequences`

**Description**

If true, export all [Sequences](../sequence/sequence.md#sequence) in the exported project.

**Type**

Boolean; read/write.

---

### ProjectManager.includeConformedAudio

`app.projectManager.options.includeConformedAudio`

**Description**

If true, include conformed audio files with exported project.

**Type**

Boolean; read/write.

---

### ProjectManager.includePreviews

`app.projectManager.options.includePreviews`

**Description**

If true, include rendered preview files with exported project.

**Type**

Boolean; read/write.

---

### ProjectManager.renameMedia

`app.projectManager.options.renameMedia`

**Description**

If true, perform renaming as part of the export process.

**Type**

Boolean; read/write.
