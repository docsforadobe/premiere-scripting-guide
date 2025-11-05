# Marker object

`app.project.activeSequence.markers.getFirstMarker()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker()`


#### Description

Both [Project items](../item/projectitem.md) and [sequences](../sequence/sequence.md) have associated Marker objects, which represent their associated markers.

---

## Attributes

### Marker.comments

`app.project.activeSequence.markers.getFirstMarker().comments`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().comments`


#### Description

The comments within the marker.

#### Type

String; read/write.

---

### Marker.end

`app.project.activeSequence.markers.getFirstMarker().end`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().end`


#### Description

A [Time object](../other/time.md) containing the value of the ending of the marker.

NOTE: To set the time value for the end of a marker, pass a Seconds value, not a complete replacement ```Time```.

#### Type

[Time object](../other/time.md); read/write.

---

### Marker.guid

`app.project.activeSequence.markers.getFirstMarker().guid`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().guid`


#### Description

The unique identifier of the marker, created at time of instantiation.

#### Type

String; read-only.

---

### Marker.name

`app.project.activeSequence.markers.getFirstMarker().name`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().name`


#### Description

The name of the marker.

#### Type

String; read/write.

---

### Marker.start

`app.project.activeSequence.markers.getFirstMarker().start`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().start`


#### Description

A [Time object](../other/time.md) containing the value of the beginning of the marker.

#### Type

[Time object](../other/time.md); read/write.

---

### Marker.type

`app.project.activeSequence.markers.getFirstMarker().type`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().type`


#### Description

The type of marker, one of:

- `"Comment"`
- `"Chapter"`
- `"Segmentation"`
- `"WebLink"`

!!! note
    Premiere Pro can import some marker types which cannot be created from within Premiere Pro.

#### Type

String; read-only.

---

## Methods

### Marker.getColorByIndex()

`app.project.activeSequence.markers.getFirstMarker().getColorByIndex(index)`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().getColorByIndex(index)`


!!! note
    This functionality was added in Adobe Premire Pro 13.x.

#### Description

Gets the marker color index.

#### Parameters

| Parameter |  Type   |           Description           |
| --------- | ------- | ------------------------------- |
| `index`   | Integer | Index of the marker to be read. |

#### Returns

Returns the color index as an Integer.

---

### Marker.getWebLinkFrameTarget()

`app.project.activeSequence.markers.getFirstMarker().getWebLinkFrameTarget()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkFrameTarget()`


#### Description

Retrieves the frame target, from the marker's FrameTarget field.

#### Parameters

None.

#### Returns

Returns a String containing the frame target, or `0` if unsuccessful.

---

### Marker.getWebLinkURL()

`app.project.activeSequence.markers.getFirstMarker().getWebLinkURL()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkURL()`


#### Description

Retrieves the URL, from the marker's URL field.

#### Parameters

None.

#### Returns

Returns a String containing the URL, or `0` if unsuccessful.

---

### Marker.setColorByIndex()

`app.project.activeSequence.markers.getFirstMarker().setColorByIndex(colorIndex, markerIndex)`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().setColorByIndex(colorIndex, markerIndex)`


!!! note
    This functionality was added in Adobe Premire Pro 13.x.

#### Description

Sets the marker color by index. Color indices listed below.

- `0` = Green
- `1` = Red
- `2` = Purple
- `3` = Orange
- `4` = Yellow
- `5` = White
- `6` = Blue
- `7` = Cyan

#### Parameters

|   Parameter   |  Type   |                Description                 |
| ------------- | ------- | ------------------------------------------ |
| `colorIndex`  | Integer | Index of the color to apply to the marker. |
| `markerIndex` | Integer | Index of the marker to be set.             |

#### Returns

Returns `undefined`.

---

### Marker.setTypeAsChapter()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsChapter()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsChapter()`


#### Description

Sets the type of the marker to "Chapter".

#### Parameters

None.

#### Returns

Returns `0` if successful.

---

### Marker.setTypeAsComment()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsComment()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsComment()`


#### Description

Sets the type of the marker to "Comment".

#### Parameters

None.

#### Returns

Returns `0` if successful.

---

### Marker.setTypeAsSegmentation()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsSegmentation()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsSegmentation()`


#### Description

Sets the type of the marker to "Segmentation".

#### Parameters

None.

#### Returns

Returns `0` if successful.

---

### Marker.setTypeAsWebLink()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsWebLink()`

`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsWebLink()`


#### Description

Sets the type of the marker to "WebLink".

#### Parameters

None.

#### Returns

Returns `0` if successful.
