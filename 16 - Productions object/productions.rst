.. highlight:: javascript

.. Productions:

Production
==========

``Production``

**Description**

The Production object lets ExtendScript access and manipulate productions, insert projects, create new projects and bins, and move existing Production projects to Trash.

----

==========
Attributes
==========

.. _production.name:

name
*********************************************

``Production.name``

**Description**

The name of the production.

----

.. _production.path:

path
****

``Production.path``

**Description**

The path to the Production folder. 

----

.. _production.projects:

projects
********

``Production.projects``

**Description**

An array of the projects containined within the Production, which are currently open. Does not include non-open projects.

----

=======
Methods
=======

.. _production.addProject:

addProject()
*********************************************

``app.production.addProject(srcProjectPath, destProjectPath);``

**Description**

Copies a project from some other location, into the Production directory.

**Parameters**

Path to the source project, specified destination path for added project.

**Returns**

Returns **true** if successful.

----

.. _production.close:

close()
*********************************************

``app.production.close();``

**Description**

Closes the Production, and all open projects from within that Production.

**Parameters**

None.

**Returns**

Returns **true** if successful.

----

.. _production.getLocked:

getLocked()
******************

``app.production.getLocked();``

**Description**

Returns the current lock state of the Production.

**Parameters**

None.

**Returns**

Returns **true** if the Production is locked, **false** if it is unlocked.

----

.. _production.moveToTrash:

moveToTrash()
*********************************************

``app.production.moveToTrash(projectOrFolderPath, suppressUI, saveProject);``

**Description**

Moves the specified path ("bin") or .prproj into the Production's Trash folder.

**Parameters**

Path to the source project or path, and booleans specifying whether or not to suppress any resultant Premiere Pro UI, and whether to save the project(s) first.

**Returns**

Returns **true** if successful.

----

.. _production.setLocked:

setLocked()
*********************************************

``app.production.setLocked(newLockState);``

**Description**

Sets the lock state of the Production

**Parameters**

Boolean corresponding to desired new lock state.

**Returns**

Returns **true** if successful.
