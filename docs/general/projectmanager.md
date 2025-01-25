<a id="projectmanager"></a>

# ProjectManager object

`app.projectManager.options`

**Description**

The ProjectManager object exposes Premiere Pro’s Project Manager, for project consolidation, transfer and transcoding.

---

## Attributes

<a id="projectmanager-affectedsequences"></a>

### ProjectManager.affectedSequences

`app.projectManager.options.affectedSequences`

**Description**

An Array of [Sequence](../sequence/sequence.md#sequence) objects, to be exported.

**Type**

Array; read/write.

---

<a id="projectmanager-cliptranscoderoption"></a>

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

<a id="projectmanager-cliptransferoption"></a>

### ProjectManager.clipTransferOption

`app.projectManager.options.clipTransferOption`

**Description**

The specified setting for clip transfer. Value will be one of the following:

| `CLIP_TRANSFER_COPY`      | Copy entire source media.           |
|---------------------------|-------------------------------------|
| `CLIP_TRANSFER_TRANSCODE` | Transcode to default output format. |

---

<a id="projectmanager-convertaecompstoclips"></a>

### ProjectManager.convertAECompsToClips

`app.projectManager.options.convertAECompsToClips`

**Description**

If true, render dynamically-linked After Effects compositions to new media (using specified output preset).

**Type**

Boolean; read/write.

---

<a id="projectmanager-convertimagesequencestoclips"></a>

### ProjectManager.convertImageSequencesToClips

`app.projectManager.options.convertImageSequencesToClips`

**Description**

If true, transcode image sequences to new media (using specified output preset).

**Type**

Boolean; read/write.

---

<a id="projectmanager-convertsyntheticstoclips"></a>

### ProjectManager.convertSyntheticsToClips

`app.projectManager.options.convertSyntheticsToClips`

**Description**

If true, transcode clips from synthetic importers to new media (using specified output preset).

**Type**

Boolean; read/write.

---

<a id="projectmanager-copytopreventalphaloss"></a>

### ProjectManager.copyToPreventAlphaLoss

`app.projectManager.options.copyToPreventAlphaLoss`

**Description**

If true, includes any available alpha information into transcoded media.

**Type**

Boolean; read/write.

---

<a id="projectmanager-destinationpath"></a>

### ProjectManager.destinationPath

`app.projectManager.options.destinationPath`

**Description**

The path to which to export the project and media.

**Type**

String; read/write.

---

<a id="projectmanager-encoderpresetfilepath"></a>

### ProjectManager.encoderPresetFilePath

`app.projectManager.options.encoderPresetFilePath`

**Description**

The path to the output preset (.epr file) to be used.

**Type**

String; read-write.

---

<a id="projectmanager-excludeunused"></a>

### ProjectManager.excludeUnused

`app.projectManager.options.excludeUnused`

**Description**

If non-zero, exclude unused project items from the exported project.

**Type**

Boolean; read/write.

---

<a id="projectmanager-handleframecount"></a>

### ProjectManager.handleFrameCount

`app.projectManager.options.handleFrameCount`

**Description**

How many frames of ‘handle’ footage (before and after the in and out points) of media, to include.

**Type**

Integer; read/write.

---

<a id="projectmanager-includeallsequences"></a>

### ProjectManager.includeAllSequences

`app.projectManager.options.includeAllSequences`

**Description**

If true, export all [Sequences](../sequence/sequence.md#sequence) in the exported project.

**Type**

Boolean; read/write.

---

<a id="projectmanager-includeconformedaudio"></a>

### ProjectManager.includeConformedAudio

`app.projectManager.options.includeConformedAudio`

**Description**

If true, include conformed audio files with exported project.

**Type**

Boolean; read/write.

---

<a id="projectmanager-includepreviews"></a>

### ProjectManager.includePreviews

`app.projectManager.options.includePreviews`

**Description**

If true, include rendered preview files with exported project.

**Type**

Boolean; read/write.

---

<a id="projectmanager-renamemedia"></a>

### ProjectManager.renameMedia

`app.projectManager.options.renameMedia`

**Description**

If true, perform renaming as part of the export process.

**Type**

Boolean; read/write.
