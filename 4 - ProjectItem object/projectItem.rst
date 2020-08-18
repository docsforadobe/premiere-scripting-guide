.. highlight:: javascript

.. _projectItem:

ProjectItem object
===================

``app.project.rootItem.children[index]``

**Description**

Each item in a project is a **projectItem**, including the project root.

----

==========
Attributes
==========

.. _projectItem.children:

ProjectItem.children
*********************************************

``app.project.rootItem.children[index].children``

**Description**

An array of project items, contained within the specified project item.

**Type**

Array; read-only.

----

.. _projectItem.getAudioChannelMapping:

ProjectItem.getAudioChannelMapping
*********************************************

``app.project.rootItem.children[index].getAudioChannelMapping``

**Description**

The audio channel mapping currently applied to this **projectItem**.

**Type**

An audioChannelMapping object.

----

.. _projectItem.name:

ProjectItem.name
*********************************************

``app.project.rootItem.children[index].name``

**Description**

The name of the project item.

**Type**

String; read/write.

----

.. _projectItem.nodeId:

ProjectItem.nodeId
*********************************************

``app.project.rootItem.children[index].nodeId``

**Description**

A unique ID assigned to the project item, upon its addition to the project.

**NOTE**: Distinguish between references to the same source media.

**Type**

String; read-only.

----

.. _projectItem.teamProjectsAssetId:

ProjectItem.teamProjectsAssetId
*********************************************

``app.project.rootItem.children[index].teamProjectsAssetId``

**Description**

The Team Projects Asset ID of the project item.

**Type**

String; read-only.

----

.. _projectItem.treePath:

ProjectItem.treePath
*********************************************

``app.project.rootItem.children[index].treePath``

**Description**

The current project location of the project item. Example:

    **\\ProjectName.prproj\\Media\\MXF\\filename.mxf**

**Type**

String; read-only.

----

.. _projectItem.type:

ProjectItem.type
*********************************************

``app.project.rootItem.children[index].type``

**Description**

Will be **CLIP**, **BIN**, **ROOT**, or **FILE**.

**Type**

Enumeration; read-only.

----

.. _projectItem.videoComponents:

ProjectItem.videoComponents
*********************************************

``app.project.rootItem.children[index].videoComponents``

**Description**

Video components for the 'Master Clip' of this project item.

**Type**

This array is read-only; the components are not.

----

=======
Methods
=======

.. _projectItem.attachProxy:

ProjectItem.attachProxy()
*********************************************

``app.project.rootItem.children[index].attachProxy(String newMediaPath, int isHiRes)``

**Description**

Attaches the media at ``newMediaPath`` to the project item, as either hi-res or proxy media.

**Parameters**

The path the the newly-assigned media (as String), and an **int** indicating whether the new media should be attached as the proxy (**0**) or high resolution (**1**) media.

**Returns**

Returns **0** if successful.

----

.. _projectItem.canChangeMediaPath:

ProjectItem.canChangeMediaPath()
*********************************************

``app.project.rootItem.children[index].canChangeMediaPath()``

**Description**

Returns **true** if Premiere Pro can change the path, associated with this project item; otherwise, returns **false**.

**Parameters**

None.

**Returns**

Boolean; **true** if media can be replaced, **false** if not.

----

.. _projectItem.canProxy:

ProjectItem.canProxy()
*********************************************

``app.project.rootItem.children[index].canProxy()``

**Description**

Indicates whether it's possible to attach a proxy, to this project item.

**Parameters**

None.

**Returns**

Returns **true** if the project item permits a proxy to be attached; **false** if not.

----

.. _projectItem.changeMediaPath:

ProjectItem.changeMediaPath()
*********************************************

``app.project.rootItem.children[index].changeMediaPath(String newPath)``

**Description**

Updates the project item to point to a new media path.

**Parameters**

A String, representing the new path.

**Returns**

Returns **0** if replacement was successful.

----

.. _projectItem.clearOutPoint:

ProjectItem.clearOutPoint()
*********************************************

``app.project.rootItem.children[index].clearOutPoint()``

**Description**

Clears any assigned out point; the project item will then start at ``startTime``.

**Parameters**

None

**Returns**

Returns ``0`` if successful.

----

.. _projectItem.createBin:

ProjectItem.createBin()
*********************************************

``app.project.rootItem.children[index].createBin(String nameOfNewBin)``

**Description**

Creates an empty bin, within the project item. Only works within bins.

**Parameters**

Name of new bin.

**Returns**

Returns **0** if creation of bin was successful.

----

.. _projectItem.createSmartBin:

ProjectItem.createSmartBin()
*********************************************

``app.project.rootItem.children[index].createSmartBin(String nameOfNewBin, String queryString)``

**Description**

Creates a search bin; only works for bin project items.

**Parameters**

Name of new bin. Query string for search.

**Returns**

Returns **0** if creation if smart bin was successful.

----

.. _projectItem.createSubClip:

ProjectItem.createSubClip()
*********************************************

``app.project.rootItem.children[index].createSubClip(subclipName, startTime, endTime,hasHardBoundaries, takeAudio, takeVideo)``

**Description**

Creates a new project item for a sub-clip of the existing project item.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``subclipName``            | Name of new subclip.                              |
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

.. _projectItem.deleteBin:

ProjectItem.deleteBin()
*********************************************

``app.project.rootItem.children[index].deleteBin()``

**Description**

Deletes a bin, **AND ALL ITS CONTENTS**, from the project.

**Parameters**

None.

**Returns**

Returns **0** if deletion was successful.

----

.. _projectItem.findItemsMatchingMediaPath:

ProjectItem.findItemsMatchingMediaPath()
*********************************************

``app.project.rootItem.children[index].findItemsMatchingMediaPath(pathToMatch, ignoreSubClips)``

**Description**

Returns an array of project items, all of which reference the same media path.

**Parameters**

+----------------------------+---------------------------------------------------+
| ``pathToMatch``            | Path to match, as **String**.                     |
+----------------------------+---------------------------------------------------+
| ``ignoreSubClips``         | 0 or 1; if 1, no subclips will be returned.       |
+----------------------------+---------------------------------------------------+

**Returns**

Returns an array of project items, or **0** if no project items matching the ``matchPath`` were found.

----

.. _projectItem.getColorLabel:

ProjectItem.getColorLabel()
*********************************************

``app.project.rootItem.children[index].getColorLabel()``

**Description**

Retrieves the project item's color label.

**Parameters**

None.

**Returns**

``Number``, one of

+------------+---------------------+
| labelColor | - 0 = Violet        |
|            | - 1 = Iris          |
|            | - 2 = Caribbean     |
|            | - 3 = Lavender      |
|            | - 4 = Cerulean      |
|            | - 5 = Forest        |
|            | - 6 = Rose          |
|            | - 7 = Mango         |
|            | - 8 = Purple        |
|            | - 9 = Blue          |
|            | - 10 = Teal         |
|            | - 11 = Magenta      |
|            | - 12 = Tan          |
|            | - 13 = Green        |
|            | - 14 = Brown        |
|            | - 15= Yellow        |
+------------+---------------------+

----

.. _projectItem.getFootageInterpretation:

ProjectItem.getFootageInterpretation()
*********************************************

``app.project.rootItem.children[index].getFootageInterpretation()``

**Description**

Returns a structure describing the current interpretation of the projectItem.

**Parameters**

None.

**Returns**

A footage interpretation structure, or ``0`` if unsuccessful.

+----------------------------+------------------------------------------------------------+
| ``alphaUsage``             | Alpha, will be one of the following:                       |
|                            |    - 0 ALPHACHANNEL_NONE                                   |
|                            |    - 1 ALPHACHANNEL_STRAIGHT                               |
|                            |    - 2 ALPHACHANNEL_PREMULTIPLIED                          |
|                            |    - 3 ALPHACHANNEL_IGNORE                                 |
+----------------------------+------------------------------------------------------------+
| ``fieldType``              | Field type, one of the following:                          |
|                            |    - -1 FIELDTYPE_DEFAULT                                  |
|                            |    - 0 FIELDTYPE_PROGRESSIVE                               |
|                            |    - 1 ALPHACHANNEL_UPPERFIRST                             |
|                            |    - 2 ALPHACHANNEL_LOWERFIRST                             |
+----------------------------+------------------------------------------------------------+
| ``ignoreAlpha``            | ``true`` or ``false``.                                     |
+----------------------------+------------------------------------------------------------+
| ``invertAlpha``            | ``true`` or ``false``.                                     |
+----------------------------+------------------------------------------------------------+
| ``frameRate``              | Frame rate as floating point value.                        |
+----------------------------+------------------------------------------------------------+
| ``pixelAspectRatio``       | Pixel aspect ratio as floating point value.                |
+----------------------------+------------------------------------------------------------+
| ``removePulldown``         | ``true`` or ``false``.                                     |
+----------------------------+------------------------------------------------------------+
| ``vrConformProjectionType``| The projection type in use, for VR footage. One of these:  |
|                            |    - 0 VR_CONFORM_PROJECTION_NONE                          |
|                            |    - 1 VR_CONFORM_PROJECTION_EQUIRECTANGULAR               |
+----------------------------+------------------------------------------------------------+
| ``vrLayoutType``           | The layout of footage in use, for VR. One of these:        |
|                            |    - 0 VR_LAYOUT_MONOSCOPIC                                |
|                            |    - 1 VR_LAYOUT_STEREO_OVER_UNDER                         |
|                            |    - 2 VR_LAYOUT_STEREO_SIDE_BY_SIDE                       |
+----------------------------+------------------------------------------------------------+
| ``vrHorizontalView``       | The horizontal view in use, for VR footage.                |
+----------------------------+------------------------------------------------------------+
| ``vrVerticalView``         | The vertical view in use, for VR footage.                  |
+----------------------------+------------------------------------------------------------+

----

.. _projectItem.getInPoint:

ProjectItem.getInPoint()
*********************************************

``app.project.rootItem.children[index].getInPoint()``

**Description**

Obtains the current project item in point.

**Parameters**

None.

**Returns**

A :ref:`time`, containing the in point.

----

.. _projectItem.getMarkers:

ProjectItem.getMarkers()
*********************************************

``app.project.rootItem.children[index].getMarkers()``

**Description**

Retrieves the :ref:`Marker <marker>` objects associated with this project item.

**Parameters**

None.

**Returns**

An array of :ref:`Marker <marker>` objects associated with the project item, or **0** if there are no markers.

----

.. _projectItem.getMediaPath:

ProjectItem.getMediaPath()
*********************************************

``app.project.rootItem.children[index].getMediaPath()``

**Description**

Returns the path associated with the project item's media, as a String. **NOTE**: This only works for atomic media; this call cannot provide meaningful paths for media which has no actual path (which will be the case for any media generated by synthetic importers, like Premiere Pro's own Universal Counting Leader). Also, for image sequences, only the path to the first image in the sequence will be returned.

**Parameters**

None.

**Returns**

A String containing the path to the media associate with the project item.

----

.. _projectItem.getOutPoint:

ProjectItem.getOutPoint()
*********************************************

``app.project.rootItem.children[index].getOutPoint(mediaType)``

**Description**

Retrieves the current out point for specified media type.

**Parameters**

mediaType is an ``int``; pass ``1`` for video only, or ``2`` for audio only. If no ``mediaType`` is passed, function gets the out point for all media.

**Returns**

Returns a :ref:`time`.

----

.. _projectItem.getProjectMetadata:

ProjectItem.getProjectMetadata()
*********************************************

``app.project.rootItem.children[index].getProjectMetadata()``

**Description**

Retrieves metadata associated with the project item. Distinct from media XMP.

**Parameters**

None.

**Returns**

A String containing all Premiere Pro private project metadata, serialized.

----

.. _projectItem.getProxyPath:

ProjectItem.getProxyPath()
*********************************************

``app.project.rootItem.children[index].getProxyPath()``

**Description**

Retrieves the path to the proxy media associated with this project item.

**Parameters**

None.

**Returns**

Returns the path (as **String**) to the proxy media associated with the proxy item, or **0** if none is found.

----

.. _projectItem.getXMPMetadata:

ProjectItem.getXMPMetadata()
*********************************************

``app.project.rootItem.children[index].getXMPMetadata()``

**Description**

Retrieves the XMP metadata associated with the project item, as a String.

**Parameters**

None.

**Returns**

A String containing all XMP metadata, serialized.

----

.. _projectItem.hasProxy:

ProjectItem.hasProxy()
*********************************************

``app.project.rootItem.children[index].hasProxy()``

**Description**

Indicates whether a proxy has already been attached, to the project item.

**Parameters**

None.

**Returns**

Returns **true** if the project item has a proxy attached; **false** if not.

----

.. _projectItem.isMergedClip:

ProjectItem.isMergedClip()
*********************************************

``app.project.rootItem.children[index].isMergedClip()``

**Description**

Indicates whether the project item refers to a merged clip.

**Parameters**

None.

**Returns**

Returns ``true`` if the project item is a merged clip, ``false`` if it isn't. 

----

.. _projectItem.isMulticamClip:

ProjectItem.isMulticamClip()
*********************************************

``app.project.rootItem.children[index].isMulticamClip()``

**Description**

Indicates whether the project item refers to a multicam clip.

**Parameters**

None.

**Returns**

Returns ``true`` if the project item is a multicam clip, ``false`` if it isn't. 

----

.. _projectItem.isOffline:

ProjectItem.isOffline()
*********************************************

``app.project.rootItem.children[index].isOffline()``

**Description**

Returns a Boolean indicating whether the project item is offline.

**Parameters**

None.

**Returns**

Boolean, ``true`` if offline.

----

.. _projectItem.isSequence:

ProjectItem.isSequence()
*********************************************

``app.project.rootItem.children[index].isSequence()``

**Description**

Indicates whether the project item refers to a :ref:`sequence`.

**Parameters**

None.

**Returns**

Returns ``true`` if the project item is a :ref:`sequence`, or a multicam clip, or a merged clip. Returns ``false`` if it isn't any of those.

----

.. _projectItem.moveBin:

ProjectItem.moveBin()
*********************************************

``app.project.rootItem.children[index].moveBin(newParentBinProjectItem)``

**Description**

Moves the projectItem into a new parent bin.

**Parameters**

None.

**Returns**

Returns **0** if move was successful.

----

.. _projectItem.refreshMedia:

ProjectItem.refreshMedia()
*********************************************

``app.project.rootItem.children[index].refreshMedia()``

**Description**

Forces Premiere Pro to update its representation of the media associated with the project item. If the media was previously off-line, this can cause it to become online (if previously missing media has become available).

**Parameters**

None.

**Returns**

An array of markers associated with the project item, or **0** if there are no markers.

----

.. _projectItem.renameBin:

ProjectItem.renameBin()
*********************************************

``app.project.rootItem.children[index].renameBin(newName)``

**Description**

Changes name of bin. Only works on project items which are bins.

**Parameters**

New bin name.

**Returns**

Returns **0** if renaming bin was successful.

----

.. _projectItem.select:

ProjectItem.select()
*********************************************

``app.project.rootItem.children[index].select()``

**Description**

Sets the project item (which must be a bin), as the target for subsequent imports into the project.

**Parameters**

None.

**Returns**

Returns **0** if the project item has successfully been made the target, for subsequent imports.

----

.. _projectItem.setColorLabel:

ProjectItem.setColorLabel()
*********************************************

``app.project.rootItem.children[index].setColorLabel(newLabelColor)``

**Description**

Sets the project item's color label.

**Parameters**

New label color; see :ref:`projectItem.getColorLabel`.

**Returns**

0 if successful.

----

.. _projectItem.setFootageInterpretation:

ProjectItem.setFootageInterpretation()
*********************************************

``app.project.rootItem.children[index].setFootageInterpretation(newInterpretation)``

**Description**

Returns a structure describing the current interpretation of the projectItem.

**Parameters**

A footage interpretation structure.

**Returns**

``0`` if successful.

----

.. _projectItem.setInPoint:

ProjectItem.setInPoint()
*********************************************

``app.project.rootItem.children[index].setInPoint(timeInTicks, mediaType)``

**Description**

Sets the in point to ``timeInTicks``, for specified media types. 

**Parameters**

A :ref:`time`, and an ``int`` determining which media type to affect; pass ``1`` for video only, ``2`` for audio only, or ``4`` for all media types.

**Returns**

Returns ``0`` if successful.

----

.. _projectItem.setOffline:

ProjectItem.setOffline()
*********************************************

``app.project.rootItem.children[index].setOffline()``

**Description**

Makes the project item offline.

**Parameters**

None.

**Returns**

``true`` if successful.

----

.. _projectItem.setOutPoint:

ProjectItem.setOutPoint()
*********************************************

``app.project.rootItem.children[index].setOutPoint(timeInTicks, mediaType)``

**Description**

Sets the out point to ``timeInTicks``, for specified media types. 

**Parameters**

A :ref:`time`, and an ``int`` determining which media type to affect; pass ``1`` for video only, ``2`` for audio only, or ``4`` for all media types.

**Returns**

Returns ``0`` if successful.

----

.. _projectItem.setOverrideFrameRate:

ProjectItem.setOverrideFrameRate()
*********************************************

``app.project.rootItem.children[index].setOverrideFrameRate(float newFrameRate)``

**Description**

Sets the frame rate of the project item.

**Parameters**

**Float** representing the new frame rate.

**Returns**

Returns **0** if the frame rate has successfully been changed.

----

.. _projectItem.setOverridePixelAspectRatio:

ProjectItem.setOverridePixelAspectRatio()
*********************************************

``app.project.rootItem.children[index].setOverridePixelAspectRatio(int numerator, int denominator)``

**Description**

Sets the pixel aspect ratio for the project item.

**Parameters**

Integers representing the new numerator and denominator.

**Returns**

Returns **0** if the aspect ratio has successfully been changed.

----

.. _projectItem.setProjectMetadata:

ProjectItem.setProjectMetadata()
*********************************************

``app.project.rootItem.children[index].setProjectMetadata(String newPrivateProjectMetadata, arrayOfUpdatedFields)``

**Description**

Sets the private project metadata associated with the project item.

**Parameters**

A String representing the new, serialized private project metadata, and an array containing the names of the fields to be updated.

**Returns**

Returns 0 if update was successful.

----

.. _projectItem.setScaleToFrameSize:

ProjectItem.setScaleToFrameSize()
*********************************************

``app.project.rootItem.children[index].setScaleToFrameSize()``

**Description**

Turns on scaling to frame size, for when media from this project item is inserted into a sequence.

**Parameters**

None.

**Returns**

Undefined return value.

----

.. _projectItem.setStartTime:

ProjectItem.setStartTime()
*********************************************

``app.project.rootItem.children[index].setStartTime(timeInTicks)``

**Description**

Assigns a new start time to the project item

**Parameters**

New starting time, represented in ticks.

**Returns**

Returns ``0`` if successful.

----

.. _projectItem.setXMPMetadata:

ProjectItem.setXMPMetadata()
*********************************************

``app.project.rootItem.children[index].setXMPMetadata(newXMPAsString)``

**Description**

Sets the XMP metadata associated with the project item.

**Parameters**

A String representing the new, serialized XMP metadata.

**Returns**

Returns 0 if update was successful.

----

.. _projectItem.startTime():

ProjectItem.startTime()
*********************************************

``app.project.rootItem.children[index].startTime()``

**Description**

Returns a :ref:`time`, representing start time.

**Parameters**

None.

**Returns**

:ref:`time`.
