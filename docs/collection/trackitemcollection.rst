.. highlight:: javascript

.. _trackItemCollection:

TrackItemCollection object
################################################

|   ``app.project.sequences[index].audioTracks[index].clips``
|   ``app.project.sequences[index].videoTracks[index].clips``

The TrackItemCollection object represents a collection of :ref:`TrackItem objects <trackItem>` on a track.

    TrackItemCollection is a subclass of :ref:`collection`. All methods and attributes of Collection, in addition to those listed below, are available when working with TrackItemCollection.

----

==========
Attributes
==========

.. _trackItemCollection.numItems:

TrackItemCollection.numItems
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips.numItems``
|   ``app.project.sequences[index].videoTracks[index].clips.numItems``

#### Description

The total number of clips on a track.

#### Type

Integer, read-only.
