.. highlight:: javascript

.. _markerCollection:

MarkerCollection object
################################################

|   ``app.project.sequences[index].markers``
|   ``app.project.rootItem.children[index].getMarkers()``

The MarkerCollection object represents a collection of :ref:`Marker objects <marker>` in a :ref:`projectItem` and :ref:`sequence`.

    MarkerCollection is a subclass of :ref:`collection`. All methods and attributes of Collection, in addition to those listed below, are available when working with MarkerCollection.

----

==========
Attributes
==========

.. _markerCollection.numMarkers:

MarkerCollection.numMarkers
*********************************************

|   ``app.project.sequences[index].markers.numMarkers``
|   ``app.project.rootItem.children[index].getMarkers().numMarkers``

#### Description

The count of marker objects in the project item or sequence.

#### Type

Integer, read-only.

----

=======
Methods
=======

.. _markerCollection.createMarker:

MarkerCollection.createMarker()
*********************************************

|   ``app.project.sequences[index].markers.createMarker(time)``
|   ``app.project.rootItem.children[index].getMarkers().createMarker(time)``

#### Description

Create a new :ref:`marker` on a project item or a sequence.

#### Parameters

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          `Float`    A time, in seconds, where marker should be created.
================  ===========  =======================

#### Returns

:ref:`marker` if successful.

----

.. _markerCollection.deleteMarker:

MarkerCollection.deleteMarker()
*********************************************

|   ``app.project.sequences[index].markers.deleteMarker(marker)``
|   ``app.project.rootItem.children[index].getMarkers().deleteMarker(marker)``

#### Description

Remove a given marker object from a collection.

#### Parameters

================  =============  =======================
Argument          Type           Description
================  =============  =======================
``marker``        :ref:`marker`  A marker object to remove from collection.
================  =============  =======================

#### Returns

`Boolean`.

**Examples**

Remove all markers from the active sequence

.. code:: javascript

    var markers = app.project.activeSequence.markers;
    var marker = markers.getFirstMarker();
    var count = markers.numMarkers;

    while (marker) {
        markers.deleteMarker(marker);
        marker = markers.getFirstMarker();
    }

    alert('Removed ' + count.toString() + ' markers');

----

.. _markerCollection.getFirstMarker:

MarkerCollection.getFirstMarker()
*********************************************

|   ``app.project.sequences[index].markers.getFirstMarker()``
|   ``app.project.rootItem.children[index].getMarkers().getFirstMarker()``

#### Description

Retrieve the first marker object, sorted by time in seconds, on a given project item or sequence.

#### Parameters

None.

#### Returns

:ref:`marker` or ``undefined``.

----

.. _markerCollection.getLastMarker:

MarkerCollection.getLastMarker()
*********************************************

|   ``app.project.sequences[index].markers.getLastMarker()``
|   ``app.project.rootItem.children[index].getMarkers().getLastMarker()``

#### Description

Retrieve the very last marker object, sorted by time in seconds, on a given project item or sequence.

#### Parameters

None.

#### Returns

:ref:`marker` or ``undefined``.

----

.. _markerCollection.getNextMarker:

MarkerCollection.getNextMarker()
*********************************************

|   ``app.project.sequences[index].markers.getNextMarker(currentMarker)``
|   ``app.project.rootItem.children[index].getMarkers().getNextMarker(currentMarker)``

#### Description

Get the next available marker, sorted by seconds, starting from a given one.

#### Parameters

==================  =============  =======================
Argument            Type           Description
==================  =============  =======================
``currentMarker``   :ref:`marker`  A starting marker object, from which to get a next one.
==================  =============  =======================

#### Returns

:ref:`marker` or ``undefined``.

----

.. _markerCollection.getPrevMarker:

MarkerCollection.getPrevMarker()
*********************************************

|   ``app.project.sequences[index].markers.getPrevMarker(currentMarker)``
|   ``app.project.rootItem.children[index].getMarkers().getPrevMarker(currentMarker)``

#### Description

Get the previous available marker, sorted by seconds, starting from a given one.

#### Parameters

==================  =============  =======================
Argument            Type           Description
==================  =============  =======================
``currentMarker``   :ref:`marker`  A starting marker object, from which to get a previous one.
==================  =============  =======================

#### Returns

:ref:`marker` or ``undefined``.
