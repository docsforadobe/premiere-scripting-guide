.. highlight:: javascript

.. _Application:

Application object
==================

``app``

**Description**

Provides access to objects and application settings within Premiere Pro.
The single global object is always available by its name, **app**.

----

==========
Attributes
==========

.. _app.anywhere:

app.anywhere
*********************************************

``app.anywhere``

**Description**

An :ref:`anywhere`, providing access to available Anywhere servers. Only available when running in Anywhere configuration (discontinued).

**Type**

:ref:`anywhere`.

----

.. _app.build:

app.build
*********************************************

``app.build``

**Description**

The number of the build of Premiere Pro being run.

**Type**

String; read-only.

**Example**

Get a build version of current application *(Adobe Premiere Pro version 14.3.1 (Build 45))*

.. code:: javascript

	parseInt(app.build); // 45

----

.. _app.encoder:

app.encoder
*********************************************

``app.encoder``

**Description**

Provides access to Adobe Media Encoder (on the same system).

**Type**

:ref:`encoder`.

----

.. _app.getAppPrefPath:

app.getAppPrefPath
*********************************************

``app.getAppPrefPath``

**Description**

The path containing the currently active "Adobe Premiere Pro Prefs" file.

**Type**

String; read-only.

**Example**

Get a path to a currently active preference file

.. code:: javascript

	app.getAppPrefPath; // /Users/USERNAME/Documents/Adobe/Premiere Pro/14.0/Profile-USERNAME/

----

.. _app.getAppSystemPrefPath:

app.getAppSystemPrefPath
*********************************************

``app.getAppSystemPrefPath``

**Description**

Premiere Pro's active configuration files, not specific to a given user.

**Type**

String; read-only.

**Example**

Get a path to a currently active configuration folder

.. code:: javascript

	app.getAppSystemPrefPath; // /Library/Application Support/Adobe/Adobe Premiere Pro 2020/

----

.. _app.getPProPrefPath:

app.getPProPrefPath
*********************************************

``app.getPProPrefPath``

**Description**

The path containing the currently active "Adobe Premiere Pro Prefs" file.

**Type**

String; read-only.

**Example**

Get a path to a currently active preference file

.. code:: javascript

	app.getPProPrefPath; // /Users/USERNAME/Documents/Adobe/Premiere Pro/14.0/Profile-USERNAME/

----

.. _app.getPProSystemPrefPath:

app.getPProSystemPrefPath
*********************************************

``app.getPProSystemPrefPath``

**Description**

Premiere Pro's active configuration files, not specific to a given user.

**Type**

String; read-only.

**Example**

Get a path to a currently active configuration folder

.. code:: javascript

	app.getPProSystemPrefPath; // /Library/Application Support/Adobe/Adobe Premiere Pro 2020/

----

.. _app.learnPanelContentDirPath:

app.learnPanelContentDirPath
*********************************************

``app.learnPanelContentDirPath``

**Description**

Get the Learn panel's contents directory path.

**Type**

String; read-only.

**Example**

Get a path to a Learn panel's directory

.. code:: javascript

	app.learnPanelContentDirPath; // /Users/Shared/Adobe/Premiere Pro 2020/Learn Panel/

----

.. _app.learnPanelExampleProjectDirPath:

app.learnPanelExampleProjectDirPath
*********************************************

``app.learnPanelExampleProjectDirPath``

**Description**

Get the Learn panel's example projects directory path.

**Type**

String; read-only.

**Example**

Get a path to a Learn panel's example projects' directory

.. code:: javascript

	app.learnPanelExampleProjectDirPath; // /Users/Shared/Adobe/Premiere Pro/14.0/Tutorial/Going Home project/

----

.. _app.metadata:

app.metadata
*********************************************

``app.metadata``

**Description**

Get applications Metadata object.

**Type**

:ref:`metadata`, read-only.

----

.. _app.path:

app.path
*********************************************

``app.path``

**Description**

Get a path to applications executable file.

**Type**

String; read-only.

**Example**

Get a path to applications executable file.

.. code:: javascript

	app.path; // /Applications/Adobe Premiere Pro 2020/Adobe Premiere Pro 2020.app/

----

.. _app.project:

app.project
*********************************************

``app.project``

**Description**

The currently active project.

**Type**

:ref:`project`.

----

.. _app.projectManager:

app.projectManager
*********************************************

``app.projectManager``

**Description**

Provides access to project management functions within Premiere Pro.

**Type**

:ref:`projectManager`.

----

.. _app.projects:

app.projects
*********************************************

``app.projects``

**Description**

An array referencing all open projects; `numProjects` contains size.

**Type**

:ref:`projectCollection`, read-only.

----

.. _app.properties:

app.properties
*********************************************

``app.properties``

**Description**

The properties object provides methods to access and modify preference values.

**Type**

:ref:`properties`, read-only;

----

.. _app.sourceMonitor:

app.sourceMonitor
*********************************************

``app.sourceMonitor``

**Description**

Provides access to :ref:`sourceMonitor`.

**Type**

:ref:`sourceMonitor`.

----

.. _app.userGuid:

app.userGuid
*********************************************

``app.userGuid``

**Description**

A unique identifier for the currently logged-in Creative Cloud user.

**Type**

String; read-only.

----

.. _app.version:

app.version
*********************************************

``app.version``

**Description**

The version of Premiere Pro, providing the API.

**Type**

String; read-only.

**Example**

Get a version of a current application *(Adobe Premiere Pro version 14.3.1 (Build 45))*

.. code:: javascript

	app.version; // 14.3.1

----

=======
Methods
=======

.. _app.enableQE:

app.enableQE()
*********************************************

``app.enableQE()``

**Description**

Enables Premiere Pro's QE DOM.

**Parameters**

None.

**Returns**

Returns true if QE DOM was enabled.

----

.. _app.getEnableProxies:

app.getEnableProxies()
*********************************************

``app.getEnableProxies()``

**Description**

Determines whether proxy usage is currently enabled.

**Parameters**

None.

**Returns**

Returns 1 if proxies are enabled, 0 of they are not.

----

.. _app.getWorkspaces:

app.getWorkspaces()
*********************************************

``app.getWorkspaces()``

**Description**

Obtain an array of the workspaces available.

**Parameters**

None.

**Returns**

Returns an Array of workspaces if successful, `null` if unsuccessful.

----

.. _app.isDocument:

app.isDocument()
*********************************************

``app.isDocument(path)``

**Description**

Determines whether the file at path can be opened as a Premiere Pro :ref:`project <project>`.

**Parameters**

A path as a ``String`` to a file to test.

**Returns**

Returns **true** if file can be opened as a Premiere Pro :ref:`project <project>`.

**Example**

Test for valid project files

.. code:: javascript

	app.isDocument('~/Desktop/myProject.prproj'); // true
	app.isDocument('~/Desktop/textFile.txt');     // false
	app.isDocument('~/Desktop/footageFile.mov');  // false
	app.isDocument('~/Desktop/imageFile.mov');    // false

----

.. _app.isDocumentOpen:

app.isDocumentOpen()
*********************************************

``app.isDocumentOpen()``

**Description**

Determines whether there are any :ref:`projects <project>` currently open.

**Parameters**

None.

**Returns**

Returns **true** if at least 1 project is open; otherwise **false**.

----

.. _app.newProject:

app.newProject()
*********************************************

``app.newProject(projPath)``

**Description**

Creates a new .prproj :ref:`project`, at the specified path.

**Parameters**

================  =================================================================================================
``projPath``       **String** containing full path to new project; a .prproj extension will be added, if necessary.
================  =================================================================================================

**Returns**

Returns **true** if successful.

----

.. _app.openDocument:

app.openDocument()
***********************

``app.openDocument(path)``

**Description**

Opens the file at the specified path, as a Premiere Pro :ref:`project`.

**Parameters**

+---------------------------------------+------------------------------------------------------------------------+
| ``pathToDocument``                    | Full path to the document to be opened.                                |
+---------------------------------------+------------------------------------------------------------------------+
| ``optionalSuppressConversionDialog``  | Suppress project conversion dialog?                                    |
+---------------------------------------+------------------------------------------------------------------------+
| ``optionalBypassLocateFileDialog``    | Bypass the locate file dialog?                                         |
+---------------------------------------+------------------------------------------------------------------------+
| ``optionalBypassWarningDialog``       | Bypass warning dialog?                                                 |
+---------------------------------------+------------------------------------------------------------------------+
| ``optionalDoNotAddToMRUList``         | Skip adding this file, to the most recently used list?                 |
+---------------------------------------+------------------------------------------------------------------------+

**Returns**

Returns **true** if file was successfully opened.

----

.. _app.openFCPXML:

app.openFCPXML()
*********************************************

``app.openFCPXML(path, projPath)``

**Description**

Opens an FCP XML file as a Premiere Pro :ref:`project` (specified in projPath).

**Parameters**

path, projPath.

**Returns**

Returns **true** if file was successfully opened as a Premiere Pro :ref:`project`.

----

.. _app.quit:

app.quit()
*********************************************

``app.quit()``

**Description**

Quits Premiere Pro; user will be prompted to save any changes to :ref:`project`.

**Parameters**

None.

**Returns**

Nothing.

----

.. _app.setEnableProxies:

app.setEnableProxies()
*********************************************

``app.setEnableProxies(enabled)``

**Description**

Determines whether proxy usage is currently enabled.

**Parameters**

================  =========================================================
``enabled``       1 turns proxies on, 0 turns them off.
================  =========================================================

**Returns**

Returns 1 if proxy enablement was changed.

----

.. _app.setExtensionPersistent:

app.setExtensionPersistent()
************************************************

``app.setExtensionPersistent(ExtensionID, persist)``

**Description**

Whether extension with the given ExtensionID persists, within this session.

**Parameters**

+--------------------------------------------------------------------------------+
| ``extensionID``   | Which extension to modify.                                 |
+--------------------------------------------------------------------------------+
| ``persist``       | Pass 1 to keep extension in memory, 0 to allow unloading.  |
+--------------------------------------------------------------------------------+

**Returns**

Returns **true** if successful. 

----

.. _app.setScratchDiskPath:

app.setScratchDiskPath()
*********************************************

``app.setScratchDiskPath(path, whichScratchValueToSet)``

**Description**

Specifies the path to be used for one of Premiere Pro's scratch disk paths.

**Parameters**

+----------------------------+-----------------------------------------------+
| ``path``                   | The new path to be used.                      |
+----------------------------+-----------------------------------------------+
| ``whichScratchValueToSet`` | Must be one of the following:                 |
|                            | ``FirstAudioCaptureFolder``                   |
|                            | ``FirstVideoCaptureFolder``                   |
|                            | ``FirstAudioPreviewFolder``                   |
|                            | ``FirstAutoSaveFolder``                       |
|                            | ``FirstCCLibrariesFolder``                    |
+----------------------------+-----------------------------------------------+

**Returns**

Returns 'true' if successful.

----

.. _app.setSDKEventMessage:

app.setSDKEventMessage()
*********************************************

``app.setSDKEventMessage(message, decorator)``

**Description**

Writes a string to Premiere Pro's Events panel.

**Parameters**

message is a string; decorator can be either 'info', 'warning' or 'error'.

**Returns**

Returns 'true' if successful.

----

.. _app.setWorkspace:

app.setWorkspace()
*********************************************

``app.setWorkspace(indexOfWorkspace)``

**Description**

Obtain an array of the workspaces available.

**Parameters**

Integer specifying which workspace (from the array returned by getWorkspaces()) to enable.

**Returns**

Returns true if successful.

----

.. _app.trace:

app.trace()
*********************************************

``app.trace()``

**Description**

Writes a string to Premiere Pro's debug console.

**Parameters**

None.

**Returns**

Returns **true** if trace was added.
