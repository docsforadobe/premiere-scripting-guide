# SourceMonitor object

`app.sourceMonitor`

#### Description

The Source object represents Premiere Pro's Source monitor.

---

## Attributes

None.

---

## Methods

### SourceMonitor.closeAllClips()

`app.sourceMonitor.closeAllClips()`

#### Description

Closes all clips in the Source monitor.

#### Parameters

None.

#### Returns

Returns `0` if successful.

---

### SourceMonitor.closeClip()

`app.sourceMonitor.closeClip()`

#### Description

Closes the front-most clip in the Source monitor.

#### Parameters

None.

#### Returns

Returns `0` if successful.

---

### SourceMonitor.getPosition()

`app.sourceMonitor.getPosition()`

#### Description

Retrieves the position of the Source monitor's current time indicator.

#### Parameters

None.

#### Returns

Returns a [Time object](../other/time.md) containing the position of the Source monitor's current time indicator.

---

### SourceMonitor.getProjectItem()

`app.sourceMonitor.getProjectItem()`

#### Description

Retrieves the project item corresponding to the media open in the Source monitor.

#### Parameters

None.

#### Returns

Returns projectItem if successful; null if not.

---

### SourceMonitor.openFilePath()

`app.sourceMonitor.openFilePath(path)`

#### Description

Open a file in the Source monitor.

#### Parameters

| Argument   | Type     | Description                 |
|------------|----------|-----------------------------|
| `path`     | String | A path to the file to open. |

#### Returns

Returns `true` if successful.

---

### SourceMonitor.openProjectItem()

`app.sourceMonitor.openProjectItem(projectItem)`

#### Description

Open a project item in the Source monitor.

#### Parameters

| Argument      | Type                                                     | Description             |
|---------------|----------------------------------------------------------|-------------------------|
| `projectItem` | [ProjectItem object](../item/projectitem.md) | A project item to open. |

#### Returns

Returns `0` if successful.

---

### SourceMonitor.play()

`app.sourceMonitor.play(playbackSpeed)`

#### Description

Begins playing back the Source monitor, at the specified playback speed.

#### Parameters

| Argument        | Type    | Description         |
|-----------------|---------|---------------------|
| `playbackSpeed` | Float | The playback speed. |

#### Returns

Returns `0` if successful.
