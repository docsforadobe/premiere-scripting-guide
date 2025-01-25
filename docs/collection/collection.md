# Collection object

Like an array, a collection associates a set of objects or values as a logical group and provides access to them by index. However, most collection objects are read-only. You do not assign objects to them yourself — their contents update automatically as objects are created or deleted.

## Objects

- [ComponentCollection object](componentcollection.md) - *todo*.
- [MarkerCollection object](markercollection.md) - a collection of the [Marker objects](../general/marker.md) in a [ProjectItem object](../item/projectitem.md) and [Sequence object](../sequence/sequence.md).
- [ProjectCollection object](projectcollection.md) - a collection of [Project objects](../general/project.md).
- [ProjectItemCollection object](projectitemcollection.md) - a collection of [ProjectItem objects](../item/projectitem.md).
- [SequenceCollection object](sequencecollection.md) - a collection of  [Sequence objects](../sequence/sequence.md).
- [TrackCollection object](trackcollection.md) - a collection of [Track objects](../sequence/track.md).
- [TrackItemCollection object](trackitemcollection.md) - a collection of [TrackItem objects](../item/trackitem.md).

---

## Attributes

| `length`   | The number of objects in the collection.   |
|------------|--------------------------------------------|

---

## Methods

| `[]`   | Retrieves an object in the collection by its index number. The<br/>first object is at index 0.   |
|--------|--------------------------------------------------------------------------------------------------|
