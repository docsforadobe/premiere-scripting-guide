.. highlight:: javascript

.. _project:

Project object
===================

``project``

**Description**

Represents a Premiere Pro project. As of Premiere Pro 12.0, multiple projects may be open at the same time.

----

==========
Attributes
==========

.. _project.documentID:

documentID
*********************************************

``project.documentID``

**Description**

A read-only unique identifier for this project.

**Type**

GUID; read-only.

----

.. _projectname.name:

name
*********************************************

``project.name``

**Description**

The name of the project.

**Type**

String; read-only.

----

.. _projectname.path:

path
*********************************************

``project.path``

**Description**

The file path of the project.

**Type**

String; read-only.

----

.. _projectname.rootItem:

rootItem
*********************************************

``project.rootItem``

**Description**

A ``projectItem`` representing the "root" of the project.

**Type**

A projectItem_; this will always be of type ``ProjectItemType_BIN``. 


----

.. _projectname.sequences:

sequences
*********************************************

``project.sequences``

**Description**

The sequences within the project.

**Type**

An array of ``sequence`` objects.


----

.. _projectname.activeSequence:

activeSequence
*********************************************

``project.activeSequence``

**Description**

The currently active sequence, within the project.

**Type**

a ``sequence`` object, or ``0`` if no sequence is currently active.


=======
Methods
=======

.. _project.openSequence:

openSequence()
*********************************************

``project.openSequence(sequenceID)``

**Description**

Makes the sequence with the provided sequence ID, active. This will open the sequence in the Timeline panel.

**Parameters**

A valid ``sequenceID``.

**Returns**

Returns **true** if successful, **false** if not.


----

.. _project.importFiles:

importFiles()
*********************************************

``project.importFiles(arrayOfFilePathsToImport, suppressUI, importAsNumberedStills, targetBin)``

**Description**

Imports media from the specified file paths.

**Parameters**

A valid ``sequenceID``.

**Returns**

Returns **true** if successful, **false** if not.

----

.. _project.importSequences:

importSequences()
*********************************************

``project.importSequences(pathOfContainingProject, arrayOfSequenceIDs)``

**Description**

Imports an array of sequences (with specified sequenceIDs), from the specified project, into the current project.

**Parameters**

*String* containing the full path to the containing project file, and an *Array* of sequenceIDs.

**Returns**

Returns **0** if successful.


----

.. _project.importAEComps:

importAEComps()
*********************************************

``project.importAEComps(pathOfContainingProject, arrayOfCompNames, optionalTargetBin)``

**Description**

Imports specified Compositions (by name) from the containing After Effects .aep project file. You can specify a target bin within the containing project; otherwise, the Compositions will appear in the most recently targeted bin, within this project.

**Parameters**

*String* containing the full path to the containing project file, and an *Array* of sequenceIDs.

**Returns**

Returns **0** if successful.
