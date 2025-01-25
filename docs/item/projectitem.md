# ProjectItem object

`app.project.rootItem.children[index]`

**Description**

Each item in a project is a **projectItem**, including the project root.

---

## Attributes

### ProjectItem.children

`app.project.rootItem.children[index].children`

**Description**

An array of project items, contained within the specified project item.

**Type**

[ProjectItemCollection object](../collection/projectitemcollection.md#projectitemcollection), read-only.

---

### ProjectItem.getAudioChannelMapping

`app.project.rootItem.children[index].getAudioChannelMapping`

**Description**

The audio channel mapping currently applied to this **projectItem**.

**Type**

An audioChannelMapping object.

---

### ProjectItem.getOverrideColorSpaceList

`app.project.rootItem.children[index].getOverrideColorSpaceList`

**Description**

*Add a description*

Returns an object, containing similar data

```javascript
{
    value: [
        sRGB,
        BT.601 (NTSC),
        BT.601 (PAL),
        BT.709,
        BT.709 (Scene),
        BT.2020,
        BT.2020 (Scene),
        BT.2100 PQ,
        BT.2100 PQ (Scene),
        BT.2100 HLG,
        BT.2100 HLG (Scene),
        DCDM XYZ,
    ]
};
```

**Type**

Javascript Object.

---

### ProjectItem.name

`app.project.rootItem.children[index].name`

**Description**

The name of the project item.

**Type**

String; read/write.

**Example**

Rename first project item.

```javascript
var item = app.project.rootItem.children[0];
if (item) {
    item.name = item.name + ', updated by PProPanel.';
} else {
    alert('Could not rename project item');
}
```

---

### ProjectItem.nodeId

`app.project.rootItem.children[index].nodeId`

**Description**

A unique ID assigned to the project item, upon its addition to the project.

**NOTE**: Distinguish between references to the same source media.

**Type**

String; read-only.

---

### ProjectItem.teamProjectsAssetId

`app.project.rootItem.children[index].teamProjectsAssetId`

**Description**

The Team Projects Asset ID of the project item.

**Type**

String; read-only.

---

### ProjectItem.treePath

`app.project.rootItem.children[index].treePath`

**Description**

The current project location of the project item. Example:

> **\\ProjectName.prproj\\Media\\MXF\\filename.mxf**

**Type**

String; read-only.

---

### ProjectItem.type

`app.project.rootItem.children[index].type`

**Description**

Will be **CLIP**, **BIN**, **ROOT**, or **FILE**.

**Type**

Enumerated value; read-only.

---

## Methods

### ProjectItem.attachProxy()

`app.project.rootItem.children[index].attachProxy(mediaPath, isHiRes)`

**Description**

Attaches the media at `newMediaPath` to the project item, as either hi-res or proxy media.

**Parameters**

| Argument    | Type      | Description                                                                              |
|-------------|-----------|------------------------------------------------------------------------------------------|
| `mediaPath` | `String`  | The path to the the newly-assigned media.                                                |
| `isHiRes`   | `Integer` | Whether the new media should be attached as the proxy `0`, or high resolution `1` media. |

**Returns**

Returns **0** if successful.

---

### ProjectItem.canChangeMediaPath()

`app.project.rootItem.children[index].canChangeMediaPath()`

**Description**

Returns **true** if Premiere Pro can change the path, associated with this project item; otherwise, returns **false**.

**Parameters**

None.

**Returns**

Boolean; **true** if media can be replaced, **false** if not.

---

### ProjectItem.canProxy()

`app.project.rootItem.children[index].canProxy()`

**Description**

Indicates whether it’s possible to attach a proxy, to this project item.

**Parameters**

None.

**Returns**

Returns **true** if the project item permits a proxy to be attached; **false** if not.

---

### ProjectItem.changeMediaPath()

`app.project.rootItem.children[index].changeMediaPath(newPath)`

**Description**

Updates the project item to point to a new media path.

**Parameters**

| Argument         | Type      | Description                   |
|------------------|-----------|-------------------------------|
| `newPath`        | `String`  | A new path to the media file. |
| `overrideChecks` | `Boolean` | Override any safety concerns. |

**Returns**

Returns **0** if replacement was successful.

---

### ProjectItem.clearOutPoint()

`app.project.rootItem.children[index].clearOutPoint()`

**Description**

Clears any assigned out point; the project item will then start at `startTime`.

**Parameters**

None

**Returns**

Returns `0` if successful.

---

### ProjectItem.createBin()

`app.project.rootItem.children[index].createBin(name)`

**Description**

Creates an empty bin, within the project item. Only works within bins.

**Parameters**

| Argument   | Type     | Description          |
|------------|----------|----------------------|
| `name`     | `String` | A name of a new bin. |

**Returns**

Returns a project item representing the new bin if successful, or **0** if unsuccessful.

---

### ProjectItem.createSmartBin()

`app.project.rootItem.children[index].createSmartBin(name, queryString)`

**Description**

Creates a search bin; only works for bin project items.

**Parameters**

| Argument      | Type     | Description              |
|---------------|----------|--------------------------|
| `name`        | `String` | A name of a new bin.     |
| `queryString` | `String` | Query string for search. |

**Returns**

Returns a projectItem representing the newly-created bin, if successful.

---

### ProjectItem.createSubClip()

`app.project.rootItem.children[index].createSubClip(name, startTime, endTime, hasHardBoundaries, takeAudio, takeVideo)`

**Description**

Creates a new project item for a sub-clip of the existing project item.

**Parameters**

| Argument            | Type      | Description                                |
|---------------------|-----------|--------------------------------------------|
| `name`              | `String`  | A name of a new subclip.                   |
| `startTime`         | `String`  | Start time of subclip, in **Ticks**.       |
| `endTime`           | `String`  | End time of subclip, in **Ticks**.         |
| `hasHardBoundaries` | `Integer` | If `1`, the user cannot extend in and out. |
| `takeVideo`         | `Integer` | If `1`, use video from source.             |
| `takeAudio`         | `Integer` | If `1`, use audio from source.             |

**Returns**

Returns a project item representing the new subclip, or 0 if creation failed.

---

### ProjectItem.deleteBin()

`app.project.rootItem.children[index].deleteBin()`

**Description**

Deletes a bin, **AND ALL ITS CONTENTS**, from the project.

**Parameters**

None.

**Returns**

Returns **0** if deletion was successful.

---

### ProjectItem.findItemsMatchingMediaPath()

`app.project.rootItem.children[index].findItemsMatchingMediaPath(pathToMatch, ignoreSubClips)`

**Description**

Returns an array of project items, all of which reference the same media path.

**Parameters**

| Argument         | Type      | Description                           |
|------------------|-----------|---------------------------------------|
| `pathToMatch`    | `String`  | A path to match.                      |
| `ignoreSubClips` | `Integer` | If `1`, no subclips will be returned. |

**Returns**

Returns an array of project items, or **0** if no project items matching the `matchPath` were found.

---

### ProjectItem.getColorLabel()

`app.project.rootItem.children[index].getColorLabel()`

**Description**

Retrieves the project item’s color label.

**Parameters**

None.

**Returns**

`Number`, one of

| labelColor   | - 0 = Violet<br/>- 1 = Iris<br/>- 2 = Caribbean<br/>- 3 = Lavender<br/>- 4 = Cerulean<br/>- 5 = Forest<br/>- 6 = Rose<br/>- 7 = Mango<br/>- 8 = Purple<br/>- 9 = Blue<br/>- 10 = Teal<br/>- 11 = Magenta<br/>- 12 = Tan<br/>- 13 = Green<br/>- 14 = Brown<br/>- 15= Yellow   |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

---

### ProjectItem.getColorSpace()

`app.project.rootItem.children[index].getColorSpace()`

**Description**

Retrieves the project item’s colorspace properties.

**Parameters**
None.

**Returns**

Returns an item’s colorspace properties.

| item.   | - name.<br/>- transfer characteristic<br/>- primaries.<br/>- matrix equation.   |
|---------|---------------------------------------------------------------------------------|

**Code Sample**

this will write the above info to the Events panel.

```javascript
```

{
var colorSpace = app.project.rootItem.children[0].getColorSpace()
app.setSDKEventMessage(“Color Space “ + “ = “ + colorSpace.name, ‘info’);
app.setSDKEventMessage(“Transfer Characteristic “ + “ = “ + colorSpace.transferCharacteristic, ‘info’);
app.setSDKEventMessage(“Color Primaries “ + “ = “ + colorSpace.primaries, ‘info’);
app.setSDKEventMessage(“Matrix Equation “ + “ = “ + colorSpace.matrixEquation, ‘info’);
}

#### .. \_projectItem.getOriginalColorSpace:

### ProjectItem.getOriginalColorSpace()

`app.project.rootItem.children[index].getOriginalColorSpace()`

**Description**

Retrieves the project item’s colorspace properties .

**Parameters**
None.

**Returns**

Returns an item’s colorspace properties if the properties have been overwritten.

| item.   | - original name.<br/>- original transfer characteristic<br/>- original primaries.<br/>- original matrix equation.   |
|---------|---------------------------------------------------------------------------------------------------------------------|

**Code Sample**

See ProjectItem.getColorSpace()

#### .. \_projectItem.getEmbeddedLUTID:

### ProjectItem.getEmbeddedLUTID()

`app.project.rootItem.children[index].getEmbeddedLUTID()`

**Description**

Retrieves the project item’s LUTID .

**Parameters**
None.

**Returns**

Returns an item’s LUTID

**Code Sample**

Writes LUTID to Events panel.

```javascript
```

{
var lutID = app.project.rootItem.children[0].getEmbeddedLUTID()
app.setSDKEventMessage(“LutID “ + “ = “ + lutID, ‘info’);
}

#### .. \_projectItem.getInputLUTID:

### ProjectItem.getInputLUTID()

`app.project.rootItem.children[index].getInputLUTID()`

**Description**

Retrieves the project item’s Input LUTID .

**Parameters**
None.

**Returns**

Returns an item’s Input LUTID

**Code Sample**

Writes Input LUTID to Events panel.

```javascript
```

{
var lutID = app.project.rootItem.children[0].getInputLUTID()

app.setSDKEventMessage(“Input LutID “ + “ = “ + inputLutID, ‘info’);
}

---

### ProjectItem.getFootageInterpretation()

`app.project.rootItem.children[index].getFootageInterpretation()`

**Description**

Returns a structure describing the current interpretation of the projectItem.

**Parameters**

None.

**Returns**

A footage interpretation structure, or `0` if unsuccessful.

| `alphaUsage`              | Alpha, will be one of the following:<br/>: - 0 ALPHACHANNEL_NONE<br/>  - 1 ALPHACHANNEL_STRAIGHT<br/>  - 2 ALPHACHANNEL_PREMULTIPLIED<br/>  - 3 ALPHACHANNEL_IGNORE   |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `fieldType`               | Field type, one of the following:<br/>: - -1 FIELDTYPE_DEFAULT<br/>  - 0 FIELDTYPE_PROGRESSIVE<br/>  - 1 FIELDTYPE_UPPERFIRST<br/>  - 2 FIELDTYPE_LOWERFIRST          |
| `ignoreAlpha`             | `true` or `false`.                                                                                                                                                    |
| `invertAlpha`             | `true` or `false`.                                                                                                                                                    |
| `frameRate`               | Frame rate as floating point value.                                                                                                                                   |
| `pixelAspectRatio`        | Pixel aspect ratio as floating point value.                                                                                                                           |
| `removePulldown`          | `true` or `false`.                                                                                                                                                    |
| `vrConformProjectionType` | The projection type in use, for VR footage. One of these:<br/>: - 0 VR_CONFORM_PROJECTION_NONE<br/>  - 1 VR_CONFORM_PROJECTION_EQUIRECTANGULAR                        |
| `vrLayoutType`            | The layout of footage in use, for VR. One of these:<br/>: - 0 VR_LAYOUT_MONOSCOPIC<br/>  - 1 VR_LAYOUT_STEREO_OVER_UNDER<br/>  - 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE      |
| `vrHorizontalView`        | The horizontal view in use, for VR footage.                                                                                                                           |
| `vrVerticalView`          | The vertical view in use, for VR footage.                                                                                                                             |

---

### ProjectItem.getInPoint()

`app.project.rootItem.children[index].getInPoint()`

**Description**

Obtains the current project item in point.

**Parameters**

None.

**Returns**

A [Time object](../other/time.md#time), containing the in point.

---

### ProjectItem.getMarkers()

`app.project.rootItem.children[index].getMarkers()`

**Description**

Retrieves the [MarkerCollection object](../collection/markercollection.md#markercollection) associated with this project item.

**Parameters**

None.

**Returns**

[MarkerCollection object](../collection/markercollection.md#markercollection), read-only;

---

### ProjectItem.getMediaPath()

`app.project.rootItem.children[index].getMediaPath()`

**Description**

Returns the path associated with the project item’s media, as a String. **NOTE**: This only works for atomic media; this call cannot provide meaningful paths for media which has no actual path (which will be the case for any media generated by synthetic importers, like Premiere Pro’s own Universal Counting Leader). Also, for image sequences, only the path to the first image in the sequence will be returned.

**Parameters**

None.

**Returns**

A String containing the path to the media associate with the project item.

---

### ProjectItem.getOutPoint()

`app.project.rootItem.children[index].getOutPoint(mediaType)`

**Description**

Retrieves the current out point for specified media type.

**Parameters**

| Argument    | Type      | Description                                                                                                             |
|-------------|-----------|-------------------------------------------------------------------------------------------------------------------------|
| `mediaType` | `Integer` | Pass `1` for video only, or `2` for audio only. If no `mediaType` is passed, function gets the out point for all media. |

**Returns**

Returns a [Time object](../other/time.md#time).

---

### ProjectItem.getProjectMetadata()

`app.project.rootItem.children[index].getProjectMetadata()`

**Description**

Retrieves metadata associated with the project item. Distinct from media XMP.

**Parameters**

None.

**Returns**

A String containing all Premiere Pro private project metadata, serialized.

---

### ProjectItem.getProjectColumnsMetadata()

`app.project.rootItem.children[index].getProjectColumnsMetadata()`

**Description**

Returns a JSON string to the user with all the metadata from the current project view layout

**Parameters**

None.

**Returns**
A JSON string that can be parsed with JSON.parse() method in the Javascript layer. This generates a list of objects, each object representing a column. Each object will contain 4 key/value pairs: ColumnName, ColumnValue, ColumnID, ColumnPath.
ColumnName and ColumnValue serve as informational key/value.
ColumnID and ColumnPath can be used to modify that column via the method setProjectMetadata() or setXMPMetadata().

For example:

| Object        | Value                                                     | Description              |
|---------------|-----------------------------------------------------------|--------------------------|
| `ColumnName`  | `Name`                                                    | Name of the column       |
| `ColumnValue` | `A014C003_180620_R205.mov`                                | Example of colummn value |
| `ColumnID`    | `Column.Intrinsic.Name`                                   | ID of the colummn        |
| `ColumnPath`  | `http://ns.adobe.com/premierePrivateProjectMetaData/1.0/` | Path of the column       |

---

### ProjectItem.getProxyPath()

`app.project.rootItem.children[index].getProxyPath()`

**Description**

Retrieves the path to the proxy media associated with this project item.

**Parameters**

None.

**Returns**

Returns the path (as **String**) to the proxy media associated with the proxy item, or **0** if none is found.

---

### ProjectItem.getXMPMetadata()

`app.project.rootItem.children[index].getXMPMetadata()`

**Description**

Retrieves the XMP metadata associated with the project item, as a String.

**Parameters**

None.

**Returns**

A String containing all XMP metadata, serialized.

---

### ProjectItem.hasProxy()

`app.project.rootItem.children[index].hasProxy()`

**Description**

Indicates whether a proxy has already been attached, to the project item.

**Parameters**

None.

**Returns**

Returns **true** if the project item has a proxy attached; **false** if not.

---

### ProjectItem.isMergedClip()

`app.project.rootItem.children[index].isMergedClip()`

**Description**

Indicates whether the project item refers to a merged clip.

**Parameters**

None.

**Returns**

Returns `true` if the project item is a merged clip, `false` if it isn’t.

---

### ProjectItem.isMulticamClip()

`app.project.rootItem.children[index].isMulticamClip()`

**Description**

Indicates whether the project item refers to a multicam clip.

**Parameters**

None.

**Returns**

Returns `true` if the project item is a multicam clip, `false` if it isn’t.

---

### ProjectItem.isOffline()

`app.project.rootItem.children[index].isOffline()`

**Description**

Returns a Boolean indicating whether the project item is offline.

**Parameters**

None.

**Returns**

Boolean, `true` if offline.

---

### ProjectItem.isSequence()

`app.project.rootItem.children[index].isSequence()`

**Description**

Indicates whether the project item refers to a [Sequence object](../sequence/sequence.md#sequence).

**Parameters**

None.

**Returns**

Returns `true` if the project item is a [Sequence object](../sequence/sequence.md#sequence), or a multicam clip, or a merged clip. Returns `false` if it isn’t any of those.

---

### ProjectItem.moveBin()

`app.project.rootItem.children[index].moveBin(newParentBinProjectItem)`

**Description**

Moves the projectItem into a new parent bin.

**Parameters**

None.

**Returns**

Returns **0** if move was successful.

---

### ProjectItem.refreshMedia()

`app.project.rootItem.children[index].refreshMedia()`

**Description**

Forces Premiere Pro to update its representation of the media associated with the project item. If the media was previously off-line, this can cause it to become online (if previously missing media has become available).

**Parameters**

None.

**Returns**

An array of markers associated with the project item, or **0** if there are no markers.

---

### ProjectItem.renameBin()

`app.project.rootItem.children[index].renameBin(newName)`

**Description**

Changes name of bin. Only works on project items which are bins.

**Parameters**

| Argument   | Type     | Description     |
|------------|----------|-----------------|
| `newName`  | `String` | A new bin name. |

**Returns**

Returns **0** if renaming bin was successful.

---

### ProjectItem.select()

`app.project.rootItem.children[index].select()`

**Description**

Sets the project item (which must be a bin), as the target for subsequent imports into the project.

**Parameters**

None.

**Returns**

Returns **0** if the project item has successfully been made the target, for subsequent imports.

---

### ProjectItem.setColorLabel()

`app.project.rootItem.children[index].setColorLabel(labelColor)`

**Description**

Sets the project item’s color label.

**Parameters**

| Argument     | Type      | Description                                                                   |
|--------------|-----------|-------------------------------------------------------------------------------|
| `labelColor` | `Integer` | A label color; see [ProjectItem.getColorLabel()](#projectitem-getcolorlabel). |

**Returns**

0 if successful.

---

### ProjectItem.setFootageInterpretation()

`app.project.rootItem.children[index].setFootageInterpretation(interpretation)`

**Description**

Returns a structure describing the current interpretation of the projectItem.

**Parameters**

| Argument         | Type   | Description                         |
|------------------|--------|-------------------------------------|
| `interpretation` |        | A footage interpretation structure. |

**Returns**

`true` if successful.

---

### ProjectItem.setInPoint()

`app.project.rootItem.children[index].setInPoint(time, mediaType)`

**Description**

Sets the in point to `timeInTicks`, for specified media types.

**Parameters**

| Argument    | Type      | Description                                                                                                      |
|-------------|-----------|------------------------------------------------------------------------------------------------------------------|
| `time`      | `String`  | A time in **Ticks**.                                                                                             |
| `mediaType` | `Integer` | Determining which media type to affect; pass `1` for video only, `2` for audio only, or `4` for all media types. |

**Returns**

Returns `0` if successful.

---

### ProjectItem.setOffline()

`app.project.rootItem.children[index].setOffline()`

**Description**

Makes the project item offline.

**Parameters**

None.

**Returns**

`true` if successful.

---

### ProjectItem.setOutPoint()

`app.project.rootItem.children[index].setOutPoint(time, mediaType)`

**Description**

Sets the out point to `timeInTicks`, for specified media types.

**Parameters**

| Argument    | Type      | Description                                                                                                      |
|-------------|-----------|------------------------------------------------------------------------------------------------------------------|
| `time`      | `String`  | A time in **Ticks**.                                                                                             |
| `mediaType` | `Integer` | Determining which media type to affect; pass `1` for video only, `2` for audio only, or `4` for all media types. |

**Returns**

Returns `0` if successful.

---

### ProjectItem.setOverrideFrameRate()

`app.project.rootItem.children[index].setOverrideFrameRate(newFrameRate)`

**Description**

Sets the frame rate of the project item.

**Parameters**

| Argument       | Type    | Description         |
|----------------|---------|---------------------|
| `newFrameRate` | `Float` | The new frame rate. |

**Returns**

Returns **0** if the frame rate has successfully been changed.

---

### ProjectItem.setOverridePixelAspectRatio()

`app.project.rootItem.children[index].setOverridePixelAspectRatio(numerator, denominator)`

**Description**

Sets the pixel aspect ratio for the project item.

**Parameters**

| Argument      | Type      | Description        |
|---------------|-----------|--------------------|
| `numerator`   | `Integer` | A new numerator.   |
| `denominator` | `Integer` | A new denominator. |

**Returns**

Returns **0** if the aspect ratio has successfully been changed.

---

### ProjectItem.setProjectMetadata()

`app.project.rootItem.children[index].setProjectMetadata(newMetadata, updatedFields)`

**Description**

Sets the private project metadata associated with the project item.

**Parameters**

| Argument        | Type     | Description                                                |
|-----------------|----------|------------------------------------------------------------|
| `newMetadata`   | `String` | A new, serialized private project metadata.                |
| `updatedFields` | `Array`  | An array containing the names of the fields to be updated. |

**Returns**

Returns 0 if update was successful.

---

### ProjectItem.setScaleToFrameSize()

`app.project.rootItem.children[index].setScaleToFrameSize()`

**Description**

Turns on scaling to frame size, for when media from this project item is inserted into a sequence.

**Parameters**

None.

**Returns**

Undefined return value.

---

### ProjectItem.setStartTime()

`app.project.rootItem.children[index].setStartTime(time)`

**Description**

Assigns a new start time to the project item

**Parameters**

| Argument   | Type     | Description                                    |
|------------|----------|------------------------------------------------|
| `time`     | `String` | A new starting time, represented in **Ticks**. |

**Returns**

Returns `0` if successful.

---

### ProjectItem.setXMPMetadata()

`app.project.rootItem.children[index].setXMPMetadata(newXMP)`

**Description**

Sets the XMP metadata associated with the project item.

**Parameters**

| Argument   | Type     | Description                     |
|------------|----------|---------------------------------|
| `newXMP`   | `String` | A new, serialized XMP metadata. |

**Returns**

Returns 0 if update was successful.

---

### ProjectItem.startTime()

`app.project.rootItem.children[index].startTime()`

**Description**

Returns a [Time object](../other/time.md#time), representing start time.

**Parameters**

None.

**Returns**

[Time object](../other/time.md#time).

---

### ProjectItem.videoComponents()

`app.project.rootItem.children[index].videoComponents()`

**Description**

Video components for the ‘Master Clip’ of this project item.

**Type**

[ComponentCollection object](../collection/componentcollection.md#componentcollection), read-only.
