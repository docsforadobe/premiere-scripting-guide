.. highlight:: javascript

.. _encoder:

Encoder object
==========================

``encoder``

**Description**

The **encoder** object represents Adobe Media Encoder, and is used for local rendering, outside of Premiere Pro.


==========
Attributes
==========

None.

=======
Methods
=======


.. _encoder.launchEncoder:

launchEncoder
*********************************************

``encoder.launchEncoder()``

**Description**

Launches Adobe Media Encoder.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _encoder.startBatch:

startBatch
*********************************************

``encoder.startBatch()``

**Description**

Makes Adobe Media Encoder start rendering its render queue.

**Parameters**

None.

**Returns**

Returns **0** if successful.

----

.. _encoder.encodeSequence:

encodeSequence
*********************************************

``encoder.encodeSequence(sequenceToRender, fullOutputPath, presetPath, workArea, boolRemoveUponCompletion)``

**Description**

Makes Adobe Media Encoder render the specified sequence, with the specified settings.

**Parameters**

+------------------------------+---------------------------------------------------+
| ``sequenceToRender``         | The **sequence** to render.                       |
+------------------------------+---------------------------------------------------+
| ``fullOutputPath``           | **String**, path to output file.                  |
+------------------------------+---------------------------------------------------+
| ``presetPath``               | **String**, path to preset (.epr) file.           |
+------------------------------+---------------------------------------------------+
| ``workArea``                 | **Integer** denoting work area to be used:        |
|                              |    - 0 ENCODE_ENTIRE                              |
|                              |    - 1 ENCODE_IN_TO_OUT                           |
|                              |    - 2 ENCODE_WORK_AREA                           |
+------------------------------+---------------------------------------------------+
| ``boolRemoveUponCompletion`` | If **1**, job will be removed once complete.      |
+------------------------------+---------------------------------------------------+

**Returns**

Returns a job ID as a **String**, for the render job added to the AME queue, or **0** if unsuccessful.

----

.. _encoder.encodeProjectItem:

encodeProjectItem
*********************************************

``encoder.encodeProjectItem(projectItem, fullOutputPath, presetPath, workArea, boolRemoveUponCompletion)``

**Description**

Makes Adobe Media Encoder render (optionally, a specified range from) the specified projectItem, with the specified settings.

**Parameters**

+------------------------------+---------------------------------------------------+
| ``projectItem``              | The **projectItem** to render.                    |
+------------------------------+---------------------------------------------------+
| ``fullOutputPath``           | **String**, path to output file.                  |
+------------------------------+---------------------------------------------------+
| ``presetPath``               | **String**, path to preset (.epr) file.           |
+------------------------------+---------------------------------------------------+
| ``workArea``                 | Integer denoting work area to be used:            |
|                              |    - 0 ENCODE_ENTIRE                              |
|                              |    - 1 ENCODE_IN_TO_OUT                           |
|                              |    - 2 ENCODE_WORK_AREA                           |
+------------------------------+---------------------------------------------------+
| ``boolRemoveUponCompletion`` | If **1**, job will be removed once complete.      |
+------------------------------+---------------------------------------------------+

**Returns**

Returns a job ID as a **String**, for the render job added to the AME queue, or **0** if unsuccessful.

----

.. _encoder.EncodeFile:

EncodeFile
*********************************************

``encoder.EncodeFile(fileToRender, fullOutputPath, presetPath, workArea, boolRemoveUponCompletion)``

**Description**

Makes Adobe Media Encoder render (optionally, a specified range from) the specified file, with the specified settings.

**Parameters**

+------------------------------+---------------------------------------------------+
| ``fileToRender``             | **String** of file path, to render.               |
+------------------------------+---------------------------------------------------+
| ``fullOutputPath``           | **String**, path to output file.                  |
+------------------------------+---------------------------------------------------+
| ``presetPath``               | **String**, path to preset (.epr) file.           |
+------------------------------+---------------------------------------------------+
| ``workArea``                 | Integer denoting work area to be used:            |
|                              |    - 0 ENCODE_ENTIRE                              |
|                              |    - 1 ENCODE_IN_TO_OUT                           |
|                              |    - 2 ENCODE_WORK_AREA                           |
+------------------------------+---------------------------------------------------+
| ``boolRemoveUponCompletion`` | If **1**, job will be removed once complete.      |
+------------------------------+---------------------------------------------------+
| ``inPoint``                  | A **Time**, for the in point of new file.         |
+------------------------------+---------------------------------------------------+
| ``outPoint``                 | A **Time**, for the out point of new file.        |
+------------------------------+---------------------------------------------------+

**Returns**

Returns a job ID as a **String**, for the render job added to the AME queue, or **0** if unsuccessful.

----

.. _encoder.setSidecarXMPEnabled:

setSidecarXMPEnabled
*********************************************

``encoder.setSidecarXMPEnabled(enabledOrNot)``

**Description**

Determines whether a sidecar file containing XMP metadata, will be output.

**Parameters**

Pass **1** to enable sidecar output, **0** to disable.

**Returns**

Returns **0** if successful.

----

.. _encoder.setEmbeddedXMPEnabled:

setEmbeddedXMPEnabled
*********************************************

``encoder.setEmbeddedXMPEnabled(enabledOrNot)``

**Description**

Determines whether embedded XMP metadata, will be output.

**Parameters**

Pass **1** to enable sidecar output, **0** to disable.

**Returns**

Returns **0** if successful.

Note: Premiere Pro and Adobe Media Encoder will output sidecar XMP for some file formats, and embed XMP for most. The applications make this determination based on numerous factors, and there is no API control to "force" sidecar or embedded output, for formats which normally use "the other approach".