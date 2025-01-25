# Track object

`app.project.sequences[index].audioTracks[index]`
<br/>
`app.project.sequences[index].videoTracks[index]`
<br/>

#### Description

The **Track** object represents a video or audio track, within a [Sequence object](sequence.md).

---

## Attributes

### Track.clips

`app.project.sequences[index].audioTracks[index].clips`
<br/>
`app.project.sequences[index].videoTracks[index].clips`
<br/>

#### Description

An array of [Track item](../item/trackitem.md) objects, contained within the track, in temporal order.

#### Type

[TrackItemCollection object](../collection/trackitemcollection.md), read-only;

---

### Track.id

`app.project.sequences[index].audioTracks[index].id`
<br/>
`app.project.sequences[index].videoTracks[index].id`
<br/>

#### Description

This is the ordinal assigned to the track, upon creation.

#### Type

Integer, read-only.

---

### Track.mediaType

`app.project.sequences[index].audioTracks[index].mediaType`
<br/>
`app.project.sequences[index].videoTracks[index].mediaType`
<br/>

#### Description

The type of media, contained in this track.

#### Type

String, read-only; valid values are `Audio` and `Video`.

---

### Track.name

`app.project.sequences[index].audioTracks[index].name`
<br/>
`app.project.sequences[index].videoTracks[index].name`
<br/>

#### Description

The name of the track.

#### Type

String; read-only.

---

### Track.transitions

`app.project.sequences[index].audioTracks[index].transitions`
<br/>
`app.project.sequences[index].videoTracks[index].transitions`
<br/>

#### Description

An array of transitions objects, contained within the track, in temporal order.

#### Type

[TrackItemCollection object](../collection/trackitemcollection.md), read-only;

---

## Methods

### Track.insertClip()

`app.project.sequences[index].audioTracks[index].insertClip(projectItem, time, vTrackIndex, aTrackIndex)`
<br/>
`app.project.sequences[index].videoTracks[index].insertClip(projectItem, time, vTrackIndex, aTrackIndex)`
<br/>

#### Description

Adds a 'clip' (media segment from a [ProjectItem object](../item/projectitem.md)) to the track, at the specified time. Media will be inserted, at that time.

#### Parameters

| Argument      | Type                                                     | Description                                               |
|---------------|----------------------------------------------------------|-----------------------------------------------------------|
| `projectItem` | [ProjectItem object](../item/projectitem.md) | A project item from which to get media.                   |
| `time`        | String                                                 | The time at which to add project item, in **Ticks**.      |
| `vTrackIndex` | `int`                                                    | The (zero-based) track index, into which to insert video. |
| `aTrackIndex` | `int`                                                    | The (zero-based) track index, into which to insert audio. |

#### Returns

None.

---

### Track.isMuted()

`app.project.sequences[index].audioTracks[index].isMuted()`
<br/>
`app.project.sequences[index].videoTracks[index].isMuted()`
<br/>

#### Description

Retrieves the current mute state, of the track.

#### Parameters

None.

#### Returns

Returns **true** if track is currently muted; **false** if not.

---

### Track.overwriteClip()

`app.project.sequences[index].audioTracks[index].overwriteClip(projectItem, time)`
<br/>
`app.project.sequences[index].videoTracks[index].overwriteClip(projectItem, time)`
<br/>

#### Description

Adds a 'clip' (media segment from a [ProjectItem object](../item/projectitem.md)) to the track, at the specified time. This will overwrite any existing media, at that time.

#### Parameters

| Argument      | Type                                                     | Description                                          |
|---------------|----------------------------------------------------------|------------------------------------------------------|
| `projectItem` | [ProjectItem object](../item/projectitem.md) | A project item from which to get media.              |
| `time`        | String                                                 | The time at which to add project item, in **Ticks**. |

#### Returns

Returns `true`.

---

### Track.setMute()

`app.project.sequences[index].audioTracks[index].setMute(isMuted)`
<br/>
`app.project.sequences[index].videoTracks[index].setMute(isMuted)`
<br/>

#### Description

Sets the mute state, of the track.

#### Parameters

| Argument   | Type      | Description                                                |
|------------|-----------|------------------------------------------------------------|
| `isMuted`  | Integer | If `1`, mute the track. If `0`, the track will be unmuted. |

#### Returns

Returns 0 if successful.
