.. highlight:: javascript

.. _trackCollection:

TrackCollection object
################################################

|   ``app.project.sequences[index].audioTracks``
|   ``app.project.sequences[index].videoTracks``

The TrackCollection object represents a collection of :ref:`Track objects <track>` in a sequence. 

    TrackCollection is a subclass of :ref:`collection`. All methods and attributes of Collection, in addition to those listed below, are available when working with TrackCollection.

----

==========
Attributes
==========

.. _trackCollection.numTracks:

TrackCollection.numTracks
*********************************************

|   ``app.project.sequences[index].audioTracks.numTracks``
|   ``app.project.sequences[index].videoTracks.numTracks``

**Description**

The total number of tracks in the sequence.

**Type**

Integer, read-only.
