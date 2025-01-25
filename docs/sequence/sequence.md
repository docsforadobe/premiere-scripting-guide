# Sequence object

`app.project.sequences[index]`

#### Description

The **Sequence** object represents sequences of media, or 'timelines', in Premiere Pro.

---

## Attributes

### Sequence.audioDisplayFormat

`app.project.sequences[index].audioDisplayFormat`

#### Description

The audio display format of the sequence.

Set this attribute with the [Sequence.setSettings()](#sequencesetsettings) method.

#### Type

An enumerated value; read/write. One of:

- `200` - Audio Samples
- `201` - Milliseconds

---

### Sequence.audioTracks

`app.project.sequences[index].audioTracks`

#### Description

An array of audio [Track](track.md) objects in the sequence.

#### Type

[TrackCollection object](../collection/trackcollection.md); read-only.

---

### Sequence.end

`app.project.sequences[index].end`

#### Description

The time, in ticks, of the end of the sequence.

#### Type

String; read-only.

---

### Sequence.frameSizeHorizontal

`app.project.sequences[index].frameSizeHorizontal`

#### Description

The horizontal frame size, or width, of the sequence.

Set this attribute with the [Sequence.setSettings()](#sequencesetsettings) method.

#### Type

Integer; read-only.

---

### Sequence.frameSizeVertical

`app.project.sequences[index].frameSizeVertical`

#### Description

The vertical frame size, or height, of the sequence.

Set this attribute with the [Sequence.setSettings()](#sequencesetsettings) method.

#### Type

Integer; read-only.

---

### Sequence.id

`app.project.sequences[index].id`

#### Description

This is the ordinal assigned to the sequence upon creation.

If this is the thirty-third sequence created within the project during a given Premiere Pro session, this value will be `33`.

!!! note
    In testing, this attribute seems unstable and produces unreliable results. Recommend using [Sequence.sequenceID](#sequencesequenceid) instead.

#### Type

Integer, read-only.

---

### Sequence.markers

`app.project.sequences[index].markers`

#### Description

An array of [Marker](../general/marker.md) objects in the sequence.

#### Type

[MarkerCollection object](../collection/markercollection.md), read-only;

---

### Sequence.name

`app.project.sequences[index].name`

#### Description

The name of the sequence.

#### Type

String; read/write.

---

### Sequence.projectItem

`app.project.sequences[index].projectItem`

#### Description

The [ProjectItem object](../item/projectitem.md) associated with the sequence.

!!! note
    Not all sequences will have a `projectItem`. There may be sequences in a project that Premiere generates that are invisible to the user, these do not have `projectItems`

#### Type

[ProjectItem object](../item/projectitem.md); read-only.

---

### Sequence.sequenceID

`app.project.sequences[index].sequenceID`

#### Description

The unique identifier assigned to this sequence, at the time of its creation, in the form of `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

#### Type

String; read-only.

---

### Sequence.timebase

`app.project.sequences[index].timebase`

#### Description

The number of ticks per frame in the sequence. Converted to seconds, this is commonly referred to as the frame duration of the sequence.

#### Type

String; read-only.

---

### Sequence.videoDisplayFormat

`app.project.sequences[index].videoDisplayFormat`

#### Description

The video display format of the sequence.

Set this attribute with the [Sequence.setSettings()](#sequencesetsettings) method.

#### Type

An enumerated value; read/write. One of:

- `100` - 24 Timecode
- `101` - 25 Timecode
- `102` - 29.97 Drop Timecode
- `103` - 29.97 Non-Drop Timecode
- `104` - 30 Timecode
- `105` - 50 Timecode
- `106` - 59.94 Drop Timecode
- `107` - 59.94 Non-Drop Timecode
- `108` - 60 Timecode
- `109` - Frames
- `110` - 23.976 Timecode
- `111` - 16mm Feet + Frames
- `112` - 35mm Feet + Frames
- `113` - 48 Timecode

---

### Sequence.videoTracks

`app.project.sequences[index].videoTracks`

#### Description

An array of video [Track](track.md) objects in the sequence.

#### Type

[TrackCollection object](../collection/trackcollection.md); read-only.

---

### Sequence.zeroPoint

`app.project.sequences[index].zeroPoint`

#### Description

The starting time, in ticks, of the sequence.

Set this attribute with the [Sequence.setZeroPoint()](#sequencesetzeropoint) method.

#### Type

String; read-only.

---

## Methods

### Sequence.attachCustomProperty()

`app.project.sequences[index].attachCustomProperty(propertyID, propertyValue)`

#### Description

Attaches a custom property, and its value, to the sequence. This property is visible if/when the sequence is exported to FCP XML.

#### Parameters

|    Argument     |  Type  |        Description        |
| --------------- | ------ | ------------------------- |
| `propertyID`    | String | ID of custom property.    |
| `propertyValue` | String | Value of custom property. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.autoReframeSequence()

`app.project.sequences[index].autoReframeSequence(numerator, denominator, motionPreset, newName, useNestedSequences)`

#### Description

Generates a new, auto-reframed sequence.

#### Parameters

|       Argument       |  Type   |                             Description                              |
| -------------------- | ------- | -------------------------------------------------------------------- |
| `numerator`          | Integer | Numerator of desired frame aspect ratio.                             |
| `denominator`        | Integer | Denominator of desired frame aspect ratio.                           |
| `motionPreset`       | String  | One of:<ul><li>`slower`</li><li>`default`</li><li>`faster`</li></ul> |
| `newName`            | String  | A name for a newly created sequence.                                 |
| `useNestedSequences` | Boolean | Whether to honor nested sequence.                                    |

#### Returns

The new [Sequence object](#sequence-object).

#### Example

```javascript
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
```

---

### Sequence.clone()

`app.project.sequences[index].clone()`

#### Description

Creates a clone, or a duplicate, of the sequence.

#### Parameters

None.

#### Returns

Boolean; `true` if successful.

---

### Sequence.close()

`app.project.sequences[index].close()`

#### Description

Closes the sequence.

#### Parameters

None.

#### Returns

Boolean; `true` if successful.

---

### Sequence.createCaptionTrack()

`app.project.sequences[index].createCaptionTrack(projectItem, startAtTime, [captionFormat])`

#### Description

Creates a caption track in the sequence using caption data from a [ProjectItem object](../item/projectitem.md).

#### Parameters

|    Argument     |                     Type                     |                                                                                                                                                                                                                                  Description                                                                                                                                                                                                                                   |
| --------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `projectItem`   | [ProjectItem object](../item/projectitem.md) | A captions source clip (e.g. .srt)                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `startAtTime`   | Float                                        | Offset in seconds from start of sequence                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `captionFormat` | `Sequence.CAPTION_FORMAT_` enum              | Caption format of the new track. Optional, default is `Sequence.CAPTION_FORMAT_SUBTITLE`. One of:<ul><li>`Sequence.CAPTION_FORMAT_SUBTITLE` - Subtitle</li><li>`Sequence.CAPTION_FORMAT_608` - CEA-608</li><li>`Sequence.CAPTION_FORMAT_708` - CEA-708</li><li>`Sequence.CAPTION_FORMAT_TELETEXT` - Teletext</li><li>`Sequence.CAPTION_FORMAT_OPEN_EBU` - EBU Subtitle</li><li>`Sequence.CAPTION_FORMAT_OP42` - OP-42</li><li>`Sequence.CAPTION_FORMAT_OP47` - OP-47</li></ul> |

#### Returns

Returns a boolean; `true` if successful.

#### Example

```javascript
app.project.activeSequence.createCaptionTrack(projectItem, 0, Sequence.CAPTION_FORMAT_708);
```

---

### Sequence.createSubsequence()

`app.project.sequences[index].createSubsequence([ignoreTrackTargeting])`

#### Description

Creates a new sequence, from the in point to the out point, which is a sub-sequence of the original sequence.

#### Parameters

|        Argument        |  Type   |                                                    Description                                                     |
| ---------------------- | ------- | ------------------------------------------------------------------------------------------------------------------ |
| `ignoreTrackTargeting` | Boolean | Whether the new sequence should ignore the track targeting, in the original sequence. Optional, default is `false` |

#### Returns

Returns the newly-created [Sequence object](#sequence-object).

!!! note
    This is not the same as nesting. The newly-created sequence is not inserted back into the original sequence. To nest, see the example function below.

#### Example

```javascript
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
```

---

### Sequence.exportAsFinalCutProXML()

`app.project.sequences[index].exportAsFinalCutProXML(outputPath)`

#### Description

Creates a new FCP XML representation of the sequence and its constituent media.

#### Parameters

|   Argument   |  Type  |                Description                |
| ------------ | ------ | ----------------------------------------- |
| `outputPath` | String | The output path for the new FCP XML file. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.exportAsMediaDirect()

`app.project.sequences[index].exportAsMediaDirect(outputPath, presetPath, workAreaType)`

#### Description

Renders the sequence to the specified output path, using the specified output preset (.epr file), and honoring the specified work area type.

#### Parameters

|    Argument    |  Type   |                                                                                                             Description                                                                                                             |
| -------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `outputPath`   | String  | An output path, to which to render the media.                                                                                                                                                                                       |
| `presetPath`   | String  | Path to the preset file (.epr file) which contains the encoding settings.                                                                                                                                                           |
| `workAreaType` | Integer | The work area type to be rendered (see below). One of:<ul><li>`0` - Renders the entire sequence.</li><li>`1` - Renders between the in and out point of the sequence.</li><li>`2` - Renders the work area of the sequence.</li></ul> |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.exportAsProject()

`app.project.sequences[index].exportAsProject(outputPath)`

#### Description

Creates a new [Project object](../general/project.md) containing only the given sequence and its constituent media.

#### Parameters

|   Argument   |  Type  |             Description              |
| ------------ | ------ | ------------------------------------ |
| `outputPath` | String | The output path for the new project. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.getExportFileExtension()

`app.project.sequences[index].getExportFileExtension(outputPresetPath)`

#### Description

Retrieves the file extension associated with the specified output preset (.epr file).

#### Parameters

|      Argument      |  Type  |          Description          |
| ------------------ | ------ | ----------------------------- |
| `outputPresetPath` | String | The output preset to be used. |

#### Returns

Returns a string.

---

### Sequence.getInPoint()

`app.project.sequences[index].getInPoint()`

#### Description

Retrieves the current sequence in point, in seconds.

#### Parameters

None.

#### Returns

Returns a string.

---

### Sequence.getInPointAsTime()

`app.project.sequences[index].getInPointAsTime()`

#### Description

Retrieves the current sequence in point.

#### Parameters

None.

#### Returns

Returns a [Time object](../other/time.md).

---

### Sequence.getOutPoint()

`app.project.sequences[index].getOutPoint()`

#### Description

Retrieves the current sequence out point, in seconds.

#### Parameters

None.

#### Returns

Returns a string.

---

### Sequence.getOutPointAsTime()

`app.project.sequences[index].getOutPointAsTime()`

#### Description

Retrieves the current sequence out point.

#### Parameters

None.

#### Returns

Returns a [Time object](../other/time.md).

---

### Sequence.getPlayerPosition()

`app.project.sequences[index].getPlayerPosition()`

#### Description

Retrieves the position of the CTI (Current Time Indicator), in ticks.

#### Parameters

None.

#### Returns

Returns a [Time object](../other/time.md).

---

### Sequence.getSelection()

`app.project.sequences[index].getSelection()`

#### Description

An array of [Track item](../item/trackitem.md) objects, of the selected clips in the sequence, in temporal order.

#### Parameters

None.

#### Returns

Returns a [TrackItemCollection object](../collection/trackitemcollection.md).

---

### Sequence.getSettings()

`app.project.sequences[index].getSettings()`

#### Description

Retrieves the settings of the current sequence.

#### Parameters

None.

#### Returns

Returns an object; a sequence settings structure.

|        Property         |              Type               |                                                                                                                                                                                                                            Possible Values                                                                                                                                                                                                                             |                                 Description                                  |
| ----------------------- | ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `audioChannelCount`     | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Number of audio channels in the sequence.                                    |
| `audioChannelType`      | Integer                         | <ul><li>`0` - Mono</li><li>`1` - Stereo</li><li>`2` - 5.1</li><li>`3` - Multichannel</li><li>`4` - 4 Channel</li><li>`5` - 8 Channel</li></ul>                                                                                                                                                                                                                                                                                                                         | Audio channel type.                                                          |
| `audioDisplayFormat`    | Integer                         | <ul><li>`200` - Audio Samples</li><li>`201` - Milliseconds</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                   | Audio timecode display format.                                               |
| `audioSampleRate`       | [Time object](../other/time.md) |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Audio sample rate.                                                           |
| `autoToneMapEnabled`    | Boolean                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Whether Auto Tone Map Media is checked.                                      |
| `compositeLinearColor`  | Boolean                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Whether sequence is composited in linear color.                              |
| `editingMode`           | String                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | The GUID of the editing mode.                                                |
| `maximumBitDepth`       | Boolean                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Whether sequence is composited at maximum depth.                             |
| `maximumRenderQuality`  | Boolean                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Whether sequence is rendered at maximum quality.                             |
| `previewCodec`          | String                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Four character code of preview codec in use.                                 |
| `previewFrameWidth`     | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Width of preview frame.                                                      |
| `previewFrameHeight`    | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Height of preview frame.                                                     |
| `previewFileFormat`     | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Path to the output preset (.epr file) being used for preview file rendering. |
| `videoDisplayFormat`    | Integer                         | <ul><li>`100` - 24 Timecode</li><li>`101` - 25 Timecode</li><li>`102` - 29.97 Drop Timecode</li><li>`103` - 29.97 Non-Drop Timecode</li><li>`104` - 30 Timecode</li><li>`105` - 50 Timecode</li><li>`106` - 59.94 Drop Timecode</li><li>`107` - 59.94 Non-Drop Timecode</li><li>`108` - 60 Timecode</li><li>`109` - Frames</li><li>`110` - 23.976 Timecode</li><li>`111` - 16mm Feet + Frames</li><li>`112` - 35mm Feet + Frames</li><li>`113` - 48 Timecode</li></ul> | Video time display format.                                                   |
| `videoFieldType`        | Integer                         | <ul><li>`-1` - Default</li><li>`0` - No Fields (Progressive Scan)</li><li>`1` - Upper Field First</li><li>`2` - Lower Field First</li></ul>                                                                                                                                                                                                                                                                                                                            | Video field type.                                                            |
| `videoFrameHeight`      | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Height of sequence video frame.                                              |
| `videoFrameWidth`       | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Width of sequence video frame.                                               |
| `videoPixelAspectRatio` | String                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Pixel aspect ratio.                                                          |
| `vrHorzCapturedView`    | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | The horizontal captured view, in degrees, for VR.                            |
| `vrVertCapturedView`    | Integer                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | The vertical captured view, in degrees, for VR.                              |
| `vrLayout`              | Integer                         | <ul><li>`0` - Monoscopic</li><li>`1` - Stereoscopic - Over/Under</li><li>`2` - Stereoscopic - Side by Side</li></ul>                                                                                                                                                                                                                                                                                                                                                   | The layout of footage in use, for VR.                                        |
| `vrProjection`          | Integer                         | <ul><li>`0` - None</li><li>`1` - Equirectangular</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                             | The projection type in use, for VR footage.                                  |

---

### Sequence.getWorkAreaInPoint()

`app.project.sequences[index].getWorkAreaInPoint()`

#### Description

Retrieves the current sequence work area in point, in seconds.

#### Parameters

None.

#### Returns

Returns a string.

---

### Sequence.getWorkAreaInPointAsTime()

`app.project.sequences[index].getWorkAreaInPointAsTime()`

#### Description

Retrieves the current sequence work area in point.

#### Parameters

None.

#### Returns

Returns a [Time object](../other/time.md).

---

### Sequence.getWorkAreaOutPoint()

`app.project.sequences[index].getWorkAreaOutPoint()`

#### Description

Retrieves the current sequence work area out point, in seconds.

#### Parameters

None.

#### Returns

Returns a string.

---

### Sequence.getWorkAreaOutPointAsTime()

`app.project.sequences[index].getWorkAreaOutPointAsTime()`

#### Description

Retrieves the current sequence work area out point.

#### Parameters

None.

#### Returns

Returns a [Time object](../other/time.md).

---

### Sequence.importMGT()

`app.project.sequences[index].importMGT(path, time, vidTrackOffset, audTrackOffset)`

#### Description

Imports a MOGRT, or an After Effects Motion Graphics Template, to the specified video or audio track, at the specified time.

#### Parameters

|     Argument     |  Type   |                                    Description                                     |
| ---------------- | ------- | ---------------------------------------------------------------------------------- |
| `path`           | String  | Full path to a valid MOGRT (.mogrt file), created in After Effects.                |
| `time`           | String  | The time at which to insert .mogrt, in ticks.                                      |
| `vidTrackOffset` | Integer | How many tracks from the zero-th video track, into which to insert .mogrt content. |
| `audTrackOffset` | Integer | How many tracks from the zero-th audio track, into which to insert .mogrt content. |

#### Returns

Returns a [TrackItem object](../item/trackitem.md).

---

### Sequence.importMGTFromLibrary()

`app.project.sequences[index].importMGTFromLibrary(libraryName, mgtName, time, vidTrackOffset, audTrackOffset)`

#### Description

Imports a MOGRT, or an After Effects Motion Graphics Template, from the current Premiere Pro user's Creative Cloud Libraries, to the specified video or audio track, at the specified time.

#### Parameters

|     Argument     |  Type   |                                    Description                                     |
| ---------------- | ------- | ---------------------------------------------------------------------------------- |
| `libraryName`    | String  | The name of Library (from the current PPro user's Creative Cloud Libraries).       |
| `mgtName`        | String  | The name of .mogrt within that library.                                            |
| `time`           | String  | The time at which to insert .mogrt, in ticks.                                      |
| `vidTrackOffset` | Integer | How many tracks from the zero-th video track, into which to insert .mogrt content. |
| `audTrackOffset` | Integer | How many tracks from the zero-th audio track, into which to insert .mogrt content. |

#### Returns

Returns a [TrackItem object](../item/trackitem.md).

---

### Sequence.insertClip()

`app.project.sequences[index].insertClip(projectItem, time, vTrackIndex, aTrackIndex)`

#### Description

Inserts a clip into the sequence, on the specified video and audio tracks, at the specified time.

#### Parameters

|   Argument    |                     Type                     |                        Description                        |
| ------------- | -------------------------------------------- | --------------------------------------------------------- |
| `projectItem` | [ProjectItem object](../item/projectitem.md) | A project item from which to get media.                   |
| `time`        | String                                       | The time at which to add project item, in seconds.        |
| `vTrackIndex` | Integer                                      | The (zero-based) track index, into which to insert video. |
| `aTrackIndex` | Integer                                      | The (zero-based) track index, into which to insert audio. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.isDoneAnalyzingForVideoEffects()

`app.project.sequences[index].isDoneAnalyzingForVideoEffects()`

#### Description

Returns whether or not the sequence is done analyzing for video effects.

#### Parameters

None.

#### Returns

Returns a boolean.

---

### Sequence.isWorkAreaEnabled()

`app.project.sequences[index].isWorkAreaEnabled()`

#### Description

Returns whether or not the sequence work area bar is enabled.

!!! note
    The work area bar is disabled by default. To enable it, check 'Work Area Bar' in the sequence hamburger menu.

#### Parameters

None.

#### Returns

Returns a boolean.

---

### Sequence.linkSelection()

`app.project.sequences[index].linkSelection()`

#### Description

Links the selected video and audio clips in the sequence.

#### Parameters

None.

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.overwriteClip()

`app.project.sequences[index].overwriteClip(projectItem, time, vTrackIndex, aTrackIndex)`

#### Description

Inserts a clip into the sequence, **overwriting existing clips**, on the specified video and audio tracks, at the specified time.

#### Parameters

|   Argument    |                     Type                     |                        Description                        |
| ------------- | -------------------------------------------- | --------------------------------------------------------- |
| `projectItem` | [ProjectItem object](../item/projectitem.md) | A project item from which to get media.                   |
| `time`        | String                                       | The time at which to add project item, in seconds.        |
| `vTrackIndex` | Integer                                      | The (zero-based) track index, into which to insert video. |
| `aTrackIndex` | Integer                                      | The (zero-based) track index, into which to insert audio. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.performSceneEditDetectionOnSelection()

`app.project.sequences[index].performSceneEditDetectionOnSelection(actionDesired, applyCutsToLinkedAudio, sensitivity)`

#### Description

Performs cut detection on the sequence selection.

#### Parameters

|         Argument         |  Type   |                                           Description                                           |
| ------------------------ | ------- | ----------------------------------------------------------------------------------------------- |
| `actionDesired`          | String  | One of:<ul><li>`CreateMarkers`</li><li>`ApplyCuts`</li></ul>                                    |
| `applyCutsToLinkedAudio` | Boolean | Whether to apply detected cuts on linked audio.                                                 |
| `sensitivity`            | String  | One of:<ul><li>`LowSensitivity`</li><li>`MediumSensitivity`</li><li>`HighSensitivity`</li></ul> |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.setInPoint()

`app.project.sequences[index].setInPoint(time)`

#### Description

Sets a new sequence in point.

#### Parameters

| Argument |                    Type                    |      Description       |
| -------- | ------------------------------------------ | ---------------------- |
| `time`   | Integer or [Time object](../other/time.md) | A new time in seconds. |

#### Returns

Null.

---

### Sequence.setOutPoint()

`app.project.sequences[index].setOutPoint(time)`

#### Description

Sets a new sequence out point.

#### Parameters

| Argument |                    Type                    |      Description       |
| -------- | ------------------------------------------ | ---------------------- |
| `time`   | Integer or [Time object](../other/time.md) | A new time in seconds. |

#### Returns

Null.

---

### Sequence.setPlayerPosition()

`app.project.sequences[index].setPlayerPosition(time)`

#### Description

Sets the position of the CTI (Current Time Indicator) in the sequence.

#### Parameters

| Argument |  Type  |     Description      |
| -------- | ------ | -------------------- |
| `time`   | String | A new time in ticks. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.setSettings()

`app.project.sequences[index].setSettings(sequenceSettings)`

#### Description

Sets the settings of the current sequence.  *[Editorial: I apologize for any perceived pedantry; sometimes, obvious documentation needs to be obvious. -bbb]*

#### Parameters

|      Argument      |   Type   |                                       Description                                        |
| ------------------ | -------- | ---------------------------------------------------------------------------------------- |
| `sequenceSettings` | `Object` | A sequence settings object, obtained via [Sequence.getSettings()](#sequencegetsettings). |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.setWorkAreaInPoint()

`app.project.sequences[index].setWorkAreaInPoint(time)`

#### Description

Sets a new sequence work area in point.

#### Parameters

| Argument |                    Type                    |      Description       |
| -------- | ------------------------------------------ | ---------------------- |
| `time`   | Integer or [Time object](../other/time.md) | A new time in seconds. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.setWorkAreaOutPoint()

`app.project.sequences[index].setWorkAreaOutPoint(time)`

#### Description

Sets a new sequence work area out point.

#### Parameters

| Argument |                    Type                    |      Description       |
| -------- | ------------------------------------------ | ---------------------- |
| `time`   | Integer or [Time object](../other/time.md) | A new time in seconds. |

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.unlinkSelection()

`app.project.sequences[index].unlinkSelection()`

#### Description

Unlinks the selected video and audio clips in the sequence.

#### Parameters

None.

#### Returns

Returns a boolean; `true` if successful.

---

### Sequence.setZeroPoint()

`app.project.sequences[index].setZeroPoint(newZeroPoint)`

#### Description

Set the starting time of the sequence.

#### Parameters

|    Argument    |  Type  |         Description          |
| -------------- | ------ | ---------------------------- |
| `newZeroPoint` | String | The new zero point in ticks. |

#### Returns

Returns a boolean; `true` if successful.
