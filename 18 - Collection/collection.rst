.. highlight:: javascript

.. _collection:

Collection object
################################################

Like an array, a collection associates a set of objects or values as a logical group and provides access to them by index. However, most collection objects are read-only. You do not assign objects to them yourself — their contents update automatically as objects are created or deleted.

=======
Objects
=======

-  :ref:`componentCollection` - *todo*.
-  :ref:`markerCollection` - a collection of the :ref:`Marker objects <marker>` in a :ref:`projectItem` and :ref:`sequence`. 
-  :ref:`projectCollection` - a collection of :ref:`Project objects <project>`. 
-  :ref:`projectItemCollection` - a collection of :ref:`ProjectItem objects <projectItem>`. 
-  :ref:`sequenceCollection` - a collection of  :ref:`Sequence objects <sequence>`.
-  :ref:`trackCollection` - a collection of :ref:`Track objects <track>`.
-  :ref:`trackItemCollection` - a collection of :ref:`TrackItem objects <trackItem>`.

----

==========
Attributes
==========

==========  ========================================
``length``  The number of objects in the collection.
==========  ========================================

-----

=======
Methods
=======

==========  ==============================================================
``[]``      Retrieves an object in the collection by its index number. The
            first object is at index 0.
==========  ==============================================================
