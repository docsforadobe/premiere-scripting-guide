.. highlight:: javascript

.. _sequence:

Sequence object
===================

``Sequence``

**Description**

The **Sequence** object represents sequences of media (a.k.a. "timelines"), in Premiere Pro.

----

==========
Attributes
==========

.. _sequence.name:

name
*********************************************

``sequence.name``

**Description**

The name of the sequence.

**Type**

String; read/write.



=======
Methods
=======

.. _sequence.createBin:

createBin()
*********************************************

``projectItem.createBin(String nameOfNewBin)``

**Description**

Creates an empty bin, within the project item. Only works within project items which are bins. 

**Parameters**

Name of new bin. 

**Returns**

Returns **0** if creation of bin was successful.

----
