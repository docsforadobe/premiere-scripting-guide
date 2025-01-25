# Collection object

Like an array, a collection associates a set of objects or values as a logical group and provides access to them by index. However, most collection objects are read-only. You do not assign objects to them yourself — their contents update automatically as objects are created or deleted.

## Objects

- [ComponentCollection object](componentcollection.md#componentcollection) - *todo*.
- [MarkerCollection object](markercollection.md#markercollection) - a collection of the [Marker objects](../general/marker.md#marker) in a [ProjectItem object](../item/projectitem.md#projectitem) and [Sequence object](../sequence/sequence.md#sequence).
- [ProjectCollection object](projectcollection.md#projectcollection) - a collection of [Project objects](../general/project.md#project).
- [ProjectItemCollection object](projectitemcollection.md#projectitemcollection) - a collection of [ProjectItem objects](../item/projectitem.md#projectitem).
- [SequenceCollection object](sequencecollection.md#sequencecollection) - a collection of  [Sequence objects](../sequence/sequence.md#sequence).
- [TrackCollection object](trackcollection.md#trackcollection) - a collection of [Track objects](../sequence/track.md#track).
- [TrackItemCollection object](trackitemcollection.md#trackitemcollection) - a collection of [TrackItem objects](../item/trackitem.md#trackitem).

---

## Attributes

| `length`   | The number of objects in the collection.   |
|------------|--------------------------------------------|

---

## Methods

| `[]`   | Retrieves an object in the collection by its index number. The<br/>first object is at index 0.   |
|--------|--------------------------------------------------------------------------------------------------|
