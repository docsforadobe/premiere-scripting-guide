# TrackItem object

`app.project.sequences[index].audioTracks[index].clips[index]`

`app.project.sequences[index].videoTracks[index].clips[index]`


#### Description

The TrackItem object represents an item on a video or audio track, within a [Sequence object](../sequence/sequence.md).

---

## Attributes

### TrackItem.components

`app.project.sequences[index].audioTracks[index].clips[index].components`

`app.project.sequences[index].videoTracks[index].clips[index].components`


#### Description

The components associated with this trackItem. This can include intrinsic transformations, as well as video and audio effects.

#### Type

[ComponentCollection object](../collection/componentcollection.md), read-only;

---

### TrackItem.duration

`app.project.sequences[index].audioTracks[index].clips[index].duration`

`app.project.sequences[index].videoTracks[index].clips[index].duration`


#### Description

The duration of the trackItem.

#### Type

[Time object](../other/time.md), read-only.

---

### TrackItem.end

`app.project.sequences[index].audioTracks[index].clips[index].end`

`app.project.sequences[index].videoTracks[index].clips[index].end`


#### Description

The visible end time of the trackItem in the sequence, relative to the beginning of its corresponding sequence (NOT the sequence zero point).

!!! note
    This may differ from the trackItem's out point, which is relative to the source.

#### Type

[Time object](../other/time.md), read/write.

---

### TrackItem.inPoint

`app.project.sequences[index].audioTracks[index].clips[index].inPoint`

`app.project.sequences[index].videoTracks[index].clips[index].inPoint`


#### Description

The in point set on the source for this trackItem instance, relative to the beginning of the source.

#### Type

[Time object](../other/time.md), read/write.

---

### TrackItem.matchName

`app.project.sequences[index].audioTracks[index].clips[index].matchName`

`app.project.sequences[index].videoTracks[index].clips[index].matchName`


#### Description

*Add a description*

#### Type

String; read-only.

---

### TrackItem.mediaType

`app.project.sequences[index].audioTracks[index].clips[index].mediaType`

`app.project.sequences[index].videoTracks[index].clips[index].mediaType`


#### Description

The mediaType of media provided by this trackItem.

#### Type

String, one of:

- `"Audio"`
- `"Video"`

---

### TrackItem.name

`app.project.sequences[index].audioTracks[index].clips[index].name`

`app.project.sequences[index].videoTracks[index].clips[index].name`


#### Description

The name of the track item.

#### Type

String; read/write.

---

### TrackItem.nodeId

`app.project.sequences[index].audioTracks[index].clips[index].nodeId`

`app.project.sequences[index].videoTracks[index].clips[index].nodeId`


#### Description

*Add a description*

#### Type

String.

---

### TrackItem.outPoint

`app.project.sequences[index].audioTracks[index].clips[index].outPoint`

`app.project.sequences[index].videoTracks[index].clips[index].outPoint`


#### Description

The out point set on the source for this TrackItem instance, relative to the beginning of the source.

#### Type

[Time object](../other/time.md), read/write.

---

### TrackItem.projectItem

`app.project.sequences[index].audioTracks[index].clips[index].projectItem`

`app.project.sequences[index].videoTracks[index].clips[index].projectItem`


#### Description

The [ProjectItem object](projectitem.md) from which the media is being drawn.

#### Type

A [ProjectItem object](projectitem.md).

---

### TrackItem.start

`app.project.sequences[index].audioTracks[index].clips[index].start`

`app.project.sequences[index].videoTracks[index].clips[index].start`


#### Description

The visible start time of the trackItem in the sequence, relative to the beginning of its corresponding sequence (NOT the sequence zero point). Note: This may differ from the trackItem's in point, which is relative to the source.

#### Type

[Time object](../other/time.md), read/write.

---

### TrackItem.type

`app.project.sequences[index].audioTracks[index].clips[index].type`

`app.project.sequences[index].videoTracks[index].clips[index].type`


#### Description

The type of media provided by this trackItem.

#### Type

Number, `1` means video, `2` means audio.

---

## Methods

### TrackItem.getMGTComponent()

`app.project.sequences[index].videotracks[index].getMGTComponent`

`app.project.sequences[index].audiotracks[index].getMGTComponent`


#### Description

Adds an After Effects Motion Graphics Template - a Mogrt - to the selected track at the specified time.

#### Parameters

|    Parameter     |  Type   |                                       Description                                       |
| ---------------- | ------- | --------------------------------------------------------------------------------------- |
| `mogrtPath`      | String  | Full path to a valid .mogrt, created in After Effects                                   |
| `targetTime`     | String  | The time at which to insert the .mogrt, in ticks                                        |
| `vidTrackOffset` | Integer | The offset from 0 (the first available track), on which to insert video from the .mogrt |
| `audTrackOffset` | Integer | The offset from 0 (the first available track), on which to insert audio from the .mogrt |

#### Returns

A Component object representing the parameters of the .mogrt, which the creator has exposed.

---

### TrackItem.getSpeed()

`app.project.sequences[index].audioTracks[index].clips[index].getSpeed()`

`app.project.sequences[index].videoTracks[index].clips[index].getSpeed()`


#### Description

Returns the speed multiplier applied to the TrackItem.

#### Parameters

None.

#### Returns

Returns the speed multiplier applied to the TrackItem, as a Float. No speed adjustment = `1`.

---

### TrackItem.isAdjustmentLayer()

`app.project.sequences[index].audioTracks[index].clips[index].isAdjustmentLayer()`

`app.project.sequences[index].videoTracks[index].clips[index].isAdjustmentLayer()`


#### Description

Returns wheter the TrackItem is an adjustment layer.

#### Parameters

None.

#### Returns

Returns `true` if the trackitem is an adjustment layer; `false` if not.

---

### TrackItem.isSpeedReversed()mm

`app.project.sequences[index].audioTracks[index].clips[index].isSpeedReversed()`

`app.project.sequences[index].videoTracks[index].clips[index].isSpeedReversed()`


#### Description

Returns whether the trackItem is reversed.

#### Parameters

None.

#### Returns

Returns `1` if TrackItem is reversed; `0` if not.

---

### TrackItem.isSelected()

`app.project.sequences[index].audioTracks[index].clips[index].isSelected()`

`app.project.sequences[index].videoTracks[index].clips[index].isSelected()`


#### Description

Retrieves the current selection state of the trackItem.

#### Parameters

None.

#### Returns

Returns `true` if trackItem is selected; `false` if not.

---

### TrackItem.setSelected()

`app.project.sequences[index].audioTracks[index].clips[index].setSelected(state, updateUI)`

`app.project.sequences[index].videoTracks[index].clips[index].setSelected(state, updateUI)`


#### Description

Sets the selection state of the trackItem.

#### Parameters

| Parameter  |  Type   |                                  Description                                  |
| ---------- | ------- | ----------------------------------------------------------------------------- |
| `state`    | Integer | If `1`, the track item will be selected; if `0`, it will be deselected.       |
| `updateUI` | Integer | If `1`, the Premiere Pro UI will be updated after this function call is made. |

#### Returns

Returns `0` if successful.

---

### TrackItem.getMatchName()

`app.project.sequences[index].audioTracks[index].clips[index].getMatchName()`

`app.project.sequences[index].videoTracks[index].clips[index].getMatchName()`


#### Description

Retrieves the match name for the trackItem.

#### Parameters

None.

#### Returns

Returns the match name as a String if successful.

---

### TrackItem.remove()

`app.project.sequences[index].audioTracks[index].clips[index].remove(inRipple, inAlignToVideo)`

`app.project.sequences[index].videoTracks[index].clips[index].remove(inRipple, inAlignToVideo)`


#### Description

Sets the selection state of the trackItem.

#### Parameters

|    Parameter     |  Type   |                                                    Description                                                    |
| ---------------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| `inRipple`       | Boolean | If `1`, later track items will be moved earlier, to fill the gap; if `0`, later track items will remain in place. |
| `inAlignToVideo` | Boolean | If `1`, Premiere Pro will align moved track items to the start of the nearest video frame.                        |

#### Returns

Returns `0` if successful.

---

### TrackItem.disabled

`app.project.sequences[index].audioTracks[index].clips[index].disabled`

`app.project.sequences[index].videoTracks[index].clips[index].disabled`


#### Description

Sets the disabled state of the TrackItem. Read/Write.

#### Parameters

|     Parameter     |  Type   |                                    Description                                     |
| ----------------- | ------- | ---------------------------------------------------------------------------------- |
| `newDisableState` | Boolean | If `true`, this TrackItem will be disabled; if `false`, TrackItem will be enabled. |

#### Returns

Returns `0` if successful.

---

### TrackItem.move()

`app.project.sequences[index].audioTracks[index].clips[index].move(newInPoint)`

`app.project.sequences[index].videoTracks[index].clips[index].move(newInPoint)`


#### Description

Moves the inPoint of the track item to a new time, by shifting it by a number of seconds.

#### Parameters

|  Parameter   |              Type               |                                          Description                                          |
| ------------ | ------------------------------- | --------------------------------------------------------------------------------------------- |
| `newInPoint` | [Time object](../other/time.md) | A Time object that represent the amount of time, in seconds, to shift the track item's start. |

#### Returns

Returns `0` if successful.
