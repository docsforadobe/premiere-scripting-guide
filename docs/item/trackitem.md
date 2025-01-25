<a id="trackitem"></a>

# TrackItem object

`app.project.sequences[index].audioTracks[index].clips[index]`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index]`
<br/>

**Description**

The **trackItem** object represents an item on a video or audio track, within a [Sequence object](../sequence/sequence.md#sequence).

---

## Attributes

### TrackItem.components

`app.project.sequences[index].audioTracks[index].clips[index].components`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components`
<br/>

**Description**

The components associated with this trackItem. This can include intrinsic transformations, as well as video and audio effects.

**Type**

[ComponentCollection object](../collection/componentcollection.md#componentcollection), read-only;

---

### TrackItem.duration

`app.project.sequences[index].audioTracks[index].clips[index].duration`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].duration`
<br/>

**Description**

The duration of the trackItem.

**Type**

[Time object](../other/time.md#time), read-only.

---

### TrackItem.end

`app.project.sequences[index].audioTracks[index].clips[index].end`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].end`
<br/>

**Description**

The visible end time of the trackItem in the sequence, relative to the beginning of its corresponding sequence (NOT the sequence zero point). Note: This may differ from the trackItem’s out point, which is relative to the source.

**Type**

[Time object](../other/time.md#time), read/write.

---

### TrackItem.inPoint

`app.project.sequences[index].audioTracks[index].clips[index].inPoint`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].inPoint`
<br/>

**Description**

The in point set on the source for this trackItem instance, relative to the beginning of the source.

**Type**

[Time object](../other/time.md#time), read/write.

---

### TrackItem.matchName

`app.project.sequences[index].audioTracks[index].clips[index].matchName`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].matchName`
<br/>

**Description**

*Add a description*

**Type**

String; read-only.

---

### TrackItem.mediaType

`app.project.sequences[index].audioTracks[index].clips[index].mediaType`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].mediaType`
<br/>

**Description**

The mediaType of media provided by this trackItem.

**Type**

String, either **Audio** or **Video**.

---

### TrackItem.name

`app.project.sequences[index].audioTracks[index].clips[index].name`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].name`
<br/>

**Description**

The name of the track item.

**Type**

String; read/write.

---

### TrackItem.nodeId

`app.project.sequences[index].audioTracks[index].clips[index].nodeId`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].nodeId`
<br/>

**Description**

*Add a description*

**Type**

String.

---

### TrackItem.outPoint

`app.project.sequences[index].audioTracks[index].clips[index].outPoint`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].outPoint`
<br/>

**Description**

The out point set on the source for this trackItem instance, relative to the beginning of the source.

**Type**

[Time object](../other/time.md#time), read/write.

---

### TrackItem.projectItem

`app.project.sequences[index].audioTracks[index].clips[index].projectItem`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].projectItem`
<br/>

**Description**

The [ProjectItem object](projectitem.md#projectitem) from which the media is being drawn.

**Type**

A [ProjectItem object](projectitem.md#projectitem).

---

### TrackItem.start

`app.project.sequences[index].audioTracks[index].clips[index].start`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].start`
<br/>

**Description**

The visible start time of the trackItem in the sequence, relative to the beginning of its corresponding sequence (NOT the sequence zero point). Note: This may differ from the trackItem’s in point, which is relative to the source.

**Type**

[Time object](../other/time.md#time), read/write.

---

### TrackItem.type

`app.project.sequences[index].audioTracks[index].clips[index].type`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].type`
<br/>

**Description**

The type of media provided by this trackItem.

**Type**

Number, **1** means video, **2** means audio.

---

## Methods

### TrackItem.getMGTComponent()

`app.project.sequences[index].videotracks[index].getMGTComponent`
<br/>
`app.project.sequences[index].audiotracks[index].getMGTComponent`
<br/>

**Description**
Adds an After Effects Motion Graphics Template - a Mogrt - to the selected track at the specified time.

**Parameters**

| Argument         | Type      | Description                                                                             |
|------------------|-----------|-----------------------------------------------------------------------------------------|
| `mogrtPath`      | `String`  | Full path to a valid .mogrt, created in After Effects                                   |
| `targetTime`     | `String`  | The time at which to insert the .mogrt, in ticks                                        |
| `vidTrackOffset` | `Integer` | The offset from 0 (the first available track), on which to insert video from the .mogrt |
| `audTrackOffset` | `Integer` | The offset from 0 (the first available track), on which to insert audio from the .mogrt |

**Returns**

A Component object representing the parameters of the .mogrt, which the creator has exposed.

---

### TrackItem.getSpeed()

`app.project.sequences[index].audioTracks[index].clips[index].getSpeed()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].getSpeed()`
<br/>

**Description**

Returns the speed multiplier applied to the `trackItem`.

**Parameters**

None.

**Returns**

Returns the speed multiplier applied to the `trackItem`, as a `float`. No speed adjustment = `1`.

---

### TrackItem.isAdjustmentLayer()

`app.project.sequences[index].audioTracks[index].clips[index].isAdjustmentLayer()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].isAdjustmentLayer()`
<br/>

**Description**

Returns wheter the `trackItem` is an adjustment layer.

**Parameters**

None.

**Returns**

Returns `true` if the trackitem is an adjustment layer; `false` if not.

---

<a id="trackitem-isspeedreversed"></a>

### TrackItem.isSpeedReversed()mm

`app.project.sequences[index].audioTracks[index].clips[index].isSpeedReversed()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].isSpeedReversed()`
<br/>

**Description**

Returns whether the trackItem is reversed.

**Parameters**

None.

**Returns**

Returns **1** if `trackItem` is reversed; **0** if not.

---

### TrackItem.isSelected()

`app.project.sequences[index].audioTracks[index].clips[index].isSelected()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].isSelected()`
<br/>

**Description**

Retrieves the current selection state of the trackItem.

**Parameters**

None.

**Returns**

Returns `true` if trackItem is selected; `false` if not.

---

### TrackItem.setSelected()

`app.project.sequences[index].audioTracks[index].clips[index].setSelected(state, updateUI)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].setSelected(state, updateUI)`
<br/>

**Description**

Sets the selection state of the trackItem.

**Parameters**

| Argument   | Type      | Description                                                                   |
|------------|-----------|-------------------------------------------------------------------------------|
| `state`    | `Integer` | If `1`, the track item will be selected; if `0`, it will be deselected.       |
| `updateUI` | `Integer` | If `1`, the Premiere Pro UI will be updated after this function call is made. |

**Returns**

Returns **0** if successful.

---

### TrackItem.getMatchName()

`app.project.sequences[index].audioTracks[index].clips[index].getMatchName()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].getMatchName()`
<br/>

**Description**

Retrieves the match name for the trackItem.

**Parameters**

None.

**Returns**

Returns the match name as a **String** if successful.

---

### TrackItem.remove()

`app.project.sequences[index].audioTracks[index].clips[index].remove(inRipple, inAlignToVideo)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].remove(inRipple, inAlignToVideo)`
<br/>

**Description**

Sets the selection state of the trackItem.

**Parameters**

| Argument         | Type      | Description                                                                                                       |
|------------------|-----------|-------------------------------------------------------------------------------------------------------------------|
| `inRipple`       | `Boolean` | If `1`, later track items will be moved earlier, to fill the gap; if `0`, later track items will remain in place. |
| `inAlignToVideo` | `Boolean` | If `1`, Premiere Pro will align moved track items to the start of the nearest video frame.                        |

**Returns**

Returns **0** if successful.

---

<a id="trackitem-disabled"></a>

### TrackItem.disabled

`app.project.sequences[index].audioTracks[index].clips[index].disabled`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].disabled`
<br/>

**Description**

Sets the disabled state of the trackItem. Read/Write.

**Parameters**

| Argument          | Type      | Description                                                                        |
|-------------------|-----------|------------------------------------------------------------------------------------|
| `newDisableState` | `Boolean` | If `true`, this trackItem will be disabled; if `false`, trackItem will be enabled. |

**Returns**

Returns **0** if successful.

---

<a id="trackitem-move"></a>

### TrackItem.move()

`app.project.sequences[index].audioTracks[index].clips[index].move(newInPoint)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].move(newInPoint)`
<br/>

**Description**

Moves the inPoint of the track item to a new time, by shifting it by a number of seconds.

**Parameters**

| Argument     | Type     | Description                                                                                   |
|--------------|----------|-----------------------------------------------------------------------------------------------|
| `newInPoint` | `Number` | A time object that represent the amount of time, in seconds, to shift the track item’s start. |

**Returns**

Returns **0** if successful.
