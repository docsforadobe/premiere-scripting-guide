# MarkerCollection object

`app.project.sequences[index].markers`
<br/>
`app.project.rootItem.children[index].getMarkers()`
<br/>

The MarkerCollection object represents a collection of [Marker objects](../general/marker.md) in a [ProjectItem object](../item/projectitem.md) and [Sequence object](../sequence/sequence.md).

> MarkerCollection is a subclass of [Collection object](collection.md). All methods and attributes of Collection, in addition to those listed below, are available when working with MarkerCollection.

---

## Attributes

### MarkerCollection.numMarkers

`app.project.sequences[index].markers.numMarkers`
<br/>
`app.project.rootItem.children[index].getMarkers().numMarkers`
<br/>

#### Description

The count of marker objects in the project item or sequence.

#### Type

Integer, read-only.

---

## Methods

### MarkerCollection.createMarker()

`app.project.sequences[index].markers.createMarker(time)`
<br/>
`app.project.rootItem.children[index].getMarkers().createMarker(time)`
<br/>

#### Description

Create a new [Marker object](../general/marker.md) on a project item or a sequence.

#### Parameters

| Argument   | Type    | Description                                         |
|------------|---------|-----------------------------------------------------|
| `time`     | Float | A time, in seconds, where marker should be created. |

#### Returns

[Marker object](../general/marker.md) if successful.

---

### MarkerCollection.deleteMarker()

`app.project.sequences[index].markers.deleteMarker(marker)`
<br/>
`app.project.rootItem.children[index].getMarkers().deleteMarker(marker)`
<br/>

#### Description

Remove a given marker object from a collection.

#### Parameters

| Argument   | Type                                         | Description                                |
|------------|----------------------------------------------|--------------------------------------------|
| `marker`   | [Marker object](../general/marker.md) | A marker object to remove from collection. |

#### Returns

Boolean.

**Examples**

Remove all markers from the active sequence

```javascript
var markers = app.project.activeSequence.markers;
var marker = markers.getFirstMarker();
var count = markers.numMarkers;

while (marker) {
    markers.deleteMarker(marker);
    marker = markers.getFirstMarker();
}

alert('Removed ' + count.toString() + ' markers');
```

---

### MarkerCollection.getFirstMarker()

`app.project.sequences[index].markers.getFirstMarker()`
<br/>
`app.project.rootItem.children[index].getMarkers().getFirstMarker()`
<br/>

#### Description

Retrieve the first marker object, sorted by time in seconds, on a given project item or sequence.

#### Parameters

None.

#### Returns

[Marker object](../general/marker.md) or `undefined`.

---

### MarkerCollection.getLastMarker()

`app.project.sequences[index].markers.getLastMarker()`
<br/>
`app.project.rootItem.children[index].getMarkers().getLastMarker()`
<br/>

#### Description

Retrieve the very last marker object, sorted by time in seconds, on a given project item or sequence.

#### Parameters

None.

#### Returns

[Marker object](../general/marker.md) or `undefined`.

---

### MarkerCollection.getNextMarker()

`app.project.sequences[index].markers.getNextMarker(currentMarker)`
<br/>
`app.project.rootItem.children[index].getMarkers().getNextMarker(currentMarker)`
<br/>

#### Description

Get the next available marker, sorted by seconds, starting from a given one.

#### Parameters

| Argument        | Type                                         | Description                                             |
|-----------------|----------------------------------------------|---------------------------------------------------------|
| `currentMarker` | [Marker object](../general/marker.md) | A starting marker object, from which to get a next one. |

#### Returns

[Marker object](../general/marker.md) or `undefined`.

---

### MarkerCollection.getPrevMarker()

`app.project.sequences[index].markers.getPrevMarker(currentMarker)`
<br/>
`app.project.rootItem.children[index].getMarkers().getPrevMarker(currentMarker)`
<br/>

#### Description

Get the previous available marker, sorted by seconds, starting from a given one.

#### Parameters

| Argument        | Type                                         | Description                                                 |
|-----------------|----------------------------------------------|-------------------------------------------------------------|
| `currentMarker` | [Marker object](../general/marker.md) | A starting marker object, from which to get a previous one. |

#### Returns

[Marker object](../general/marker.md) or `undefined`.
