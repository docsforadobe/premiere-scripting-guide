# Marker object

`app.project.activeSequence.markers.getFirstMarker()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker()`
<br/>

**Description**

Both [Project items](../item/projectitem.md) and [sequences](../sequence/sequence.md) have associated **marker** objects, which represent their associated markers.

---

## Attributes

### Marker.comments

`app.project.activeSequence.markers.getFirstMarker().comments`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().comments`
<br/>

**Description**

The comments within the marker.

**Type**

String; read/write.

---

### Marker.end

`app.project.activeSequence.markers.getFirstMarker().end`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().end`
<br/>

**Description**

A [Time object](../other/time.md) containing the value of the ending of the marker.

**Type**

[Time object](../other/time.md); read/write.

---

### Marker.guid

`app.project.activeSequence.markers.getFirstMarker().guid`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().guid`
<br/>

**Description**

The unique identifier of the marker, created at time of instantiation.

**Type**

String; read-only.

---

### Marker.name

`app.project.activeSequence.markers.getFirstMarker().name`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().name`
<br/>

**Description**

The name of the marker.

**Type**

String; read/write.

---

### Marker.start

`app.project.activeSequence.markers.getFirstMarker().start`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().start`
<br/>

**Description**

A [Time object](../other/time.md) containing the value of the beginning of the marker.

**Type**

[Time object](../other/time.md); read/write.

---

### Marker.type

`app.project.activeSequence.markers.getFirstMarker().type`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().type`
<br/>

**Description**

The type of marker; either "Comment", "Chapter", "Segmentation", or "WebLink". Note: Premiere Pro can import some marker types, which cannot be created from within Premiere Pro.

**Type**

String; read-only.

---

## Methods

### Marker.getColorByIndex()

`app.project.activeSequence.markers.getFirstMarker().getColorByIndex(index)`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().getColorByIndex(index)`
<br/>

!!! note
    This functionality was added in Adobe Premire Pro 13.x.

**Description**

Gets the marker color index.

**Parameters**

| Argument   | Type      | Description                     |
|------------|-----------|---------------------------------|
| `index`    | `Integer` | Index of the marker to be read. |

**Returns**

Returns the color index as an `Integer`.

---

### Marker.getWebLinkFrameTarget()

`app.project.activeSequence.markers.getFirstMarker().getWebLinkFrameTarget()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkFrameTarget()`
<br/>

**Description**

Retrieves the frame target, from the marker's FrameTarget field.

**Parameters**

None.

**Returns**

Returns a `String` containing the frame target, or **0** if unsuccessful.

---

### Marker.getWebLinkURL()

`app.project.activeSequence.markers.getFirstMarker().getWebLinkURL()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().getWebLinkURL()`
<br/>

**Description**

Retrieves the URL, from the marker's URL field.

**Parameters**

None.

**Returns**

Returns a `String` containing the URL, or **0** if unsuccessful.

---

### Marker.setColorByIndex()

`app.project.activeSequence.markers.getFirstMarker().setColorByIndex(colorIndex, markerIndex)`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().setColorByIndex(colorIndex, markerIndex)`
<br/>

!!! note
    This functionality was added in Adobe Premire Pro 13.x.

**Description**

Sets the marker color by index. Color indexies listed below.

* 0 = Green
* 1 = Red
* 2 = Purple
* 3 = Orange
* 4 = Yellow
* 5 = White
* 6 = Blue
* 7 = Cyan

**Parameters**

| Argument      | Type      | Description                                |
|---------------|-----------|--------------------------------------------|
| `colorIndex`  | `Integer` | Index of the color to apply to the marker. |
| `markerIndex` | `Integer` | Index of the marker to be set.             |

**Returns**

Returns `undefined`.

---

### Marker.setTypeAsChapter()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsChapter()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsChapter()`
<br/>

**Description**

Sets the type of the marker to "Chapter".

**Parameters**

None.

**Returns**

Returns **0** if successful.

---

### Marker.setTypeAsComment()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsComment()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsComment()`
<br/>

**Description**

Sets the type of the marker to "Comment".

**Parameters**

None.

**Returns**

Returns **0** if successful.

---

### Marker.setTypeAsSegmentation()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsSegmentation()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsSegmentation()`
<br/>

**Description**

Sets the type of the marker to "Segmentation".

**Parameters**

None.

**Returns**

Returns **0** if successful.

---

### Marker.setTypeAsWebLink()

`app.project.activeSequence.markers.getFirstMarker().setTypeAsWebLink()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker().setTypeAsWebLink()`
<br/>

**Description**

Sets the type of the marker to "WebLink".

**Parameters**

None.

**Returns**

Returns **0** if successful.
