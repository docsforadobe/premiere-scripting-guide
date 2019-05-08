.. highlight:: javascript

.. _Application:

Application object
==================

``app``

**Description**

Provides access to objects and application settings within the Premiere Pro application. The single global object is always available by its name, **app**.

Attributes of the Application object provide access to specific objects within Premiere Pro. Methods of the Application object can create, open and close projects, access other APIs available from the PPro DOM (Anywhere, Team Projects, Encoder), and quit Premiere Pro. 

----

==========
Attributes
==========

.. _app.version:

version
*********************************************

``app.version``

**Description**

The version of Premiere Pro, providing the API.

**Type**

Floating point; read-only.

----

.. _app.buildNumber:

buildNumber
*********************************************

``app.buildNumber``

**Description**

The number of the build of Premiere Pro being run.

**Type**

Integer; read-only.

----

.. _app.getPProPrefPath:

getPProPrefPath
*********************************************

``app.getPProPrefPath``

**Description**

The path containing the currently active "Adobe Premiere Pro Prefs" file.

**Type**

String; read-only.

----

.. _app.getPProSysPrefPath:

getPProSysPrefPath
*********************************************

``app.getPProSysPrefPath``

**Description**

The path containing Premiere Pro's active configuration files, not specific to a given user.

**Type**

String; read-only.

----


.. _app.project:

project
*********************************************

``app.project``

**Description**

The currently active project. Before Premiere Pro 12.0, this pointed at the *only* project; after 12.0, this points to the currently active project.

**Type**

String; read-only.

----

.. _app.projects:

projects
*********************************************

``app.projects``

**Description**

An array referencing all open projects.

**Type**

Array (of Project objects); read-only.

----

.. _app.anywhere:

anywhere
*********************************************

``app.anywhere``

**Description**

An Anywhere object, providing access to connected Anywhere servers, through the Premiere Pro DOM. 

**Type**
Anywhere object; read-only.
----

.. _app.Encoder:

Encoder
*********************************************

``app.Encoder``

**Description**

An Encoder object, providing access to Adobe Media Encoder (as used by Premiere Pro), through the Premiere Pro DOM. 

**Type**

Encoder object; read-only.


----

.. _app.projectManager:

projectManager
*********************************************

``app.projectManager``

**Description**

A projectManager object, providing access to project management functions within Premiere Pro.

**Type**

projectManager object; some members read-only, some read-write.


----

.. _app.userGuid:

userGuid
*********************************************

``app.userGuid``

**Description**

A unique identifier for the currently logged-in Creative Cloud user.

**Type**

userGuid object; read-only.


----

.. _app.properties:

properties
*********************************************

``app.properties``

**Description**

The properties object provides methods to access and modify preference values.

**Type**

properties object; read-only.

----

.. _app.sourceMonitor:

sourceMonitor
*********************************************

``app.sourceMonitor``

**Description**

Provides access to Source monitor.

**Type**

sourceMonitor object; read-only.


=======
Methods
=======

.. _app.isDocumentOpen:

isDocumentOpen()
*********************************************

``app.isDocumentOpen()``

**Description**

Determines whether there are any projects currently open.

**Parameters**

None.

**Returns**

Returns **true** if at least 1 project is open; otherwise **false**.

----

.. _app.isDocument:

isDocument(path)
*********************************************

``app.isDocument(path)``

**Description**

Determines whether the file at path can be opened as a Premiere Pro project.

**Parameters**

None.

**Returns**

Returns **true** if file is openeable.

----

.. _app.openDocument:

openDocument(path)
*********************************************

``app.openDocument(path)``

**Description**

Opens the file at the specified path, as a Premiere Pro project.

**Parameters**

path

**Returns**

Returns **true** if file was successfully opened.

----


.. _app.openFCPXML:

openFCPXML(path, projPath)
*********************************************

``app.openFCPXML(path, projPath)``

**Description**

Opens an FCP XML file at path, as a Premiere Pro project (specified in projPath).

**Parameters**

path, projPath.

**Returns**

Returns **true** if file was successfully opened as a Premiere Pro project.

----


.. _app.quit:

quit()
*********************************************

``app.quit()``

**Description**

Quits Premiere Pro; user will be prompted to save any changes to project.

**Parameters**

None.

**Returns**

Nothing.

----

.. _app.trace:

trace()
*********************************************

``app.trace()``

**Description**

Writes a string to Premiere Pro's debug console.

**Parameters**

None.

**Returns**

Nothing.

----

.. _app.setSDKEventMessage:

setSDKEventMessage()
*********************************************

``app.setSDKEventMessage(message, decorator)``

**Description**

Writes a string to Premiere Pro's Events panel. 

**Parameters**

message is a string; decorator can be either 'info', 'warning' or 'error'.

**Returns**

Returns 'true' if successful.

----


.. _app.setScratchDiskPath:

setScratchDiskPath()
*********************************************

``app.setScratchDiskPath(path, whichScratchValueToSet)``

**Description**

Specifies the path to be used for one of Premiere Pro's scratch disk paths. 

**Parameters**

+----------------------------+---------------------------------------------------+
| ``path``                   | The new path to be used.                          |
+----------------------------+---------------------------------------------------+
| ``whichScratchValueToSet`` | Must be one of the following:                     |
|                            | ``FirstAudioCaptureFolder``                       |
|                            | ``FirstVideoCaptureFolder``                       |
|                            | ``FirstAudioPreviewFolder``                       |
|                            | ``FirstAutoSaveFolder``                           |
|                            | ``FirstCCLibrariesFolder``                        |
+----------------------------+---------------------------------------------------+

**Returns**

Returns 'true' if successful.

----

.. _app.enableQE:

enableQE()
*********************************************

|  ``app.enableQE()``

**Description**

Enables Premiere Pro's QE DOM. 

**Parameters**

None.

**Returns**

Returns true if QE DOM was enabled.

----

.. _app.setExtensionPersistent:

setExtensionPersistent(ExtensionID, persist)
************************************************

``app.setExtensionPersistent(ExtensionID, persist)``

**Description**

Controls whether the extension with the given ExtensionID remains persistent in memory, throughout the Premiere Pro session.

**Parameters**

================  =========================================================
``extensionID``   Which extension to modify.
================  =========================================================
``persist``       Pass 1 to keep extension in memory, 0 to allow unloading.
================  =========================================================

**Returns**
Nothing.
----

.. _app.getEnableProxies:

getEnableProxies()
*********************************************

``app.getEnableProxies()``

**Description**

Determines whether proxy usage is currently enabled.

**Parameters**

None.

**Returns**

Returns 1 if proxies are enabled, 0 of they are not.

----


.. _app.setEnableProxies:

setEnableProxies(enabled)
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

