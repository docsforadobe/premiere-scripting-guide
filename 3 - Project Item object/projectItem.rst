.. highlight:: javascript

.. _projectItem:

Project Item object
===================

``projectItem``

**Description**

Each item in a given Premiere Pro project is a **projectItem**. The root item of each project is also, itself, a **projectItem**.

----

==========
Attributes
==========

.. _projectItem.children:

children
*********************************************

``projectItem.children``

**Description**

A read-only array of project items, which are themselves contained within the specified project item.

**Type**

Array; read-only.

----

.. name:

name
*********************************************

``projectItem.name``

**Description**

The name of the project item.

**Type**

String; read/write.

----

.. _projectItem.treePath:

treePath
*********************************************

``projectItem.treePath``

**Description**

The path within the project, to the current location of the project item. For example, an .mxf file located in a bin named "MXF", within a bin named "Media", would have a tree path of 

    **\\ProjectName.prproj\\Media\\MXF\\filename.mxf**

**Type**

String; read-only.

----

.. _projectItem.type:

type
*********************************************

``projectItem.type``

**Description**

The type of the project Item. Value will be one of the following: **CLIP**, **BIN**, **ROOT**, or **FILE**.

**Type**

Enumeration; read-only.

----


.. _projectItem.nodeID:

nodeID
*********************************************

``projectItem.nodeID``

**Description**

A unique ID assigned to the project item, upon its addition to the project.

**NOTE**: This allows for differentiation between two different project items, associated with the same source media.

**Type**

String; read-only.

----

.. _projectItem.videoComponents:

videoComponents
*********************************************

``projectItem.videoComponents``

**Description**

An array of video components associated with the 'Master Clip' of this project item.

**Type**

Array of video components. While the parameters associated with these components are read/write, this array of components is, itself, read-only.


----

.. _projectItem.teamProjectsAssetId:

teamProjectsAssetId
*********************************************

``projectItem.teamProjectsAssetId``

**Description**

The Team Projects Asset ID of the project item. 

**Type**
String; read-only.

----

=======
Methods
=======

.. _projectItem.createSmartBin:

createSmartBin()
*********************************************

``projectItem.createSmartBin(String nameOfNewBin, String queryString)``

**Description**

Creates a smart bin (also known as a search bin), within the project item. Only works within project items which are bins. 

**Parameters**

Name of new bin. Query string for search.

**Returns**

Returns **0** if creation if smart bin was successful.

----

.. _projectItem.createBin:

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

.. _projectItem.renameBin:

renameBin()
*********************************************

``projectItem.renameBin(String newName)``

**Description**

Changes name of bin. Only works on project items which are bins. 

**Parameters**

New bin name. 

**Returns**

Returns **0** if renaming bin was successful.

----

.. _projectItem.deleteBin:

deleteBin()
*********************************************

``projectItem.deleteBin()``

**Description**

Deletes a bin, **AND ALL ITS CONTENTS**, from the project. Only works on project items which are bins. 

**Parameters**

None.

**Returns**

Returns **0** if deletion was successful.

----

.. _projectItem.getXMPMetadata:

getXMPMetadata()
*********************************************

``projectItem.getXMPMetadata()``

**Description**

Retrieves the XMP metadata associated with the project item, as a String.

**Parameters**

None.

**Returns**

A String containing all XMP metadata, serialized. 

----

.. _projectItem.setXMPMetadata:

setXMPMetadata()
*********************************************

``projectItem.setXMPMetadata(String newXMP)``

**Description**

Sets the XMP metadata associated with the project item.

**Parameters**

A String representing the new, serialized XMP metadata.

**Returns**

Returns 0 if update was successful.

----

.. _projectItem.getProjectMetadata:

getProjectMetadata()
*********************************************

``projectItem.getProjectMetadata()``

**Description**

Retrieves Premiere Pro's private project metadata associated with the project item, as a String. **NOTE** While this data is also valid XMP, it is distinct from the XMP metadata associated with the media. 

**Parameters**

None.

**Returns**

A String containing all Premiere Pro private project metadata, serialized. 

----

.. _projectItem.setProjectMetadata:

setProjectMetadata()
*********************************************

``projectItem.setProjectMetadata(String newPrivateProjectMetadata)``

**Description**

Sets the private project metadata associated with the project item.

**Parameters**

A String representing the new, serialized private project metadata.

**Returns**

Returns 0 if update was successful.

----

.. _projectItem.getMarkers:

getMarkers()
*********************************************

``projectItem.getMarkers()``

**Description**

Retrieves the markers associated with this project item.

**Parameters**

None.

**Returns**

An array of markers associated with the project item, or **0** if there are no markers. 

----

.. _projectItem.refreshMedia:

refreshMedia()
*********************************************

``projectItem.refreshMedia()``

**Description**

Forces Premiere Pro to update its representation of the media associated with the project item. If the media was previously off-line, this can cause it to become online (if previously missing media has become available).

**Parameters**

None.

**Returns**

An array of markers associated with the project item, or **0** if there are no markers. 

----

.. _projectItem.getMediaPath:

getMediaPath()
*********************************************

``projectItem.getMediaPath()``

**Description**

Returns the path associated with the project item's media, as a String. **NOTE**: This only works for atomic media; this call cannot provide meaningful paths for media which has no actual path (which will be the case for any media generated by synthetic importers, like Premiere Pro's own Universal Counting Leader).

**Parameters**

None.

**Returns**

A String containing the path to the media associate with the project item.

----

.. _projectItem.canChangeMediaPath:

canChangeMediaPath()
*********************************************

``projectItem.canChangeMediaPath()``

**Description**

Returns **true** if Premiere Pro can change the path, associated with this project item; otherwise, returns **false**.

**Parameters**

None.

**Returns**

Boolean; **true** if media can be replaced, **false** if not.

----

.. _projectItem.changeMediaPath:

changeMediaPath()
*********************************************

``projectItem.changeMediaPath(String newPath)``

**Description**

Updates the project item to point to a new media path. 

**Parameters**

A String, representing the new path.

**Returns**

Returns **0** if replacement was successful.

----

.. _projectItem.select:

select()
*********************************************

``projectItem.select()``

**Description**

Sets the project item (which must be a bin), as the target for subsequent imports into the project. 

**Parameters**

None.

**Returns**

Returns **0** if the project item has successfully been made the target, for subsequent imports. 

----

.. _projectItem.setOverridePixelAspectRatio:

setOverridePixelAspectRatio()
*********************************************

``projectItem.setOverridePixelAspectRatio(int numerator, int denominator)``

**Description**

Sets the pixel aspect ratio for the project item.

**Parameters**

Integers representing the new numerator and denominator.

**Returns**

Returns **0** if the aspect ratio has successfully been changed.

----

.. _projectItem.setOverrideFrameRate:

setOverrideFrameRate()
*********************************************

``projectItem.setOverrideFrameRate(float newFrameRate)``

**Description**

Sets the frame rate of the project item.

**Parameters**

**Float** representing the new frame rate.

**Returns**

Returns **0** if the frame rate has successfully been changed.

----

.. _projectItem.setScaleToFrameSize:

setScaleToFrameSize()
*********************************************

``projectItem.setScaleToFrameSize()``

**Description**

Turns on scaling to frame size, for when media from this project item is inserted into a sequence.

**Parameters**

None.

**Returns**

Returns **0** if the project item has been successfully set to scale to frame size.

----

.. _projectItem.createSubClip:

createSubClip()
*********************************************

``projectItem.createSubClip()``

**Description**

Turns on scaling to frame size, for when media from this project item is inserted into a sequence.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``name``                   | Name of new subclip.                              |
+----------------------------+---------------------------------------------------+
| ``startTime``              | Start time of subclip, in **Ticks**.              |
+----------------------------+---------------------------------------------------+
| ``endTime``                | End time of subclip, in **Ticks**.                |
+----------------------------+---------------------------------------------------+
| ``hasHardBoundaries``      | 0 or 1; if 1, the user cannot extend in and out.  |
+----------------------------+---------------------------------------------------+
| ``takeVideo``              | 0 or 1; if 1, use video from source.              |
+----------------------------+---------------------------------------------------+
| ``takeAudio``              | 0 or 1; if 1, use video from source.              |
+----------------------------+---------------------------------------------------+


**Returns**

Returns a project item representing the new subclip, or 0 if creation failed.

----

.. _projectItem.findItemsMatchingMediaPath:

findItemsMatchingMediaPath()
*********************************************

``projectItem.findItemsMatchingMediaPath(String matchPath, int ignoreSubClips)``

**Description**

Returns an array of project items, all of which reference the same media path.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``matchPath``              | Path to match, as **String**.                     |
+----------------------------+---------------------------------------------------+
| ``ignoreSubClips``         | 0 or 1; if 1, no subclips will be returned.       |
+----------------------------+---------------------------------------------------+

**Returns**

Returns an array of project items, or **0** if no project items matching the ``matchPath`` were found.

----

.. _projectItem.canProxy:

canProxy()
*********************************************

``projectItem.canProxy()``

**Description**

Indicates whether it's possible to attach a proxy, to this project item.

**Parameters**

None.

**Returns**

Returns **true** if the project item permits a proxy to be attached; **false** if not.

----

.. _projectItem.hasProxy:

hasProxy()
*********************************************

``projectItem.hasProxy()``

**Description**

Indicates whether a proxy has already been attached, to the project item.

**Parameters**

None.

**Returns**

Returns **true** if the project item has a proxy attached; **false** if not.

----

.. _projectItem.getProxyPath:

getProxyPath()
*********************************************

``projectItem.getProxyPath()``

**Description**

Retrieves the path to the proxy media associated with this project item.

**Parameters**

None.

**Returns**

Returns the path (as **String**) to the proxy media associated with the proxy item, or **0** if none is found.

----

.. _projectItem.attachProxy:

attachProxy()
*********************************************

``projectItem.attachProxy(String newMediaPath, int isHiRes)``

**Description**

Attaches the media at ``newMediaPath`` to the project item, as either hi-res or proxy media.

**Parameters**

The path the the newly-assigned media (as String), and an **int** indicating whether the new media should be attached as the proxy (**0**) or high resolution (**1**) media.

**Returns**

Returns **0** if successful.
