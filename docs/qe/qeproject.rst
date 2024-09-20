.. highlight:: javascript

.. _qeproject:

QEProject object
================

.. warning:: The QE DOM project model's refreshing is unreliable and for that reason, amongst others, the QE DOM remains officially unsupported and not recommended.

``qe.project``

**Description**

Represents a Premiere Pro project. As of Premiere Pro 12.0, multiple projects may be open at the same time.

----

==========
Attributes
==========

.. _qeproject.currentRendererName:

QEProject.currentRendererName
*****************************

``qe.project.currentRendererName``

**Description**

Retrieves the name of the renderer for the project.

**Type**

String; read-only.

----

.. _qeproject.importFailures:

QEProject.importFailures
************************

``qe.project.importFailures``

**Description**

Unknown.

**Type**

Object; read-only.

----

.. _qeproject.isAudioConforming:

QEProject.isAudioConforming
***************************

``qe.project.isAudioConforming``

**Description**

Whether or not audio is conforming in the project.

**Type**

Boolean; read-only.

----

.. _qeproject.isAudioPeakGenerating:

QEProject.isAudioPeakGenerating
*******************************

``qe.project.isAudioPeakGenerating``

**Description**

Whether or not audio peaks are currently generating in the project.

**Type**

Boolean; read-only.

----

.. _qeproject.isIndexing:

QEProject.isIndexing
********************

``qe.project.isIndexing``

**Description**

Whether or not the project is currently indexing.

**Type**

Boolean; read-only.

----

.. _qeproject.numActiveProgressItems:

QEProject.numActiveProgressItems
********************************

``qe.project.numActiveProgressItems``

**Description**

Unknown.

**Type**

Number; read-only.

----

.. _qeproject.numAudioPeakGeneratedFiles:

QEProject.numAudioPeakGeneratedFiles
************************************

``qe.project.numAudioPeakGeneratedFiles``

**Description**

Retrieves the number of generated audio peak files in the project.

**Type**

Number; read-only.

----

.. _qeproject.numBins:

QEProject.numBins
*****************

``qe.project.numBins``

**Description**

Retrieves the number of bins in the project.

**Type**

Number; read-only.

.. warning:: This appears to return the number of bins that exist when :ref:`app.enableqe` is called and doesn't update when new bins are created, moved or deleted.

----

.. _qeproject.numnumConformedFilesBins:

QEProject.numConformedFiles
***************************

``qe.project.numConformedFiles``

**Description**

Retrieves the number of conformed files in the project.

**Type**

Number; read-only.

----

.. _qeproject.numIndexedFiles:

QEProject.numIndexedFiles
*************************

``qe.project.numIndexedFiles``

**Description**

Retrieves the number of indexed files in the project.

**Type**

Number; read-only.

----

.. _qeproject.numItems:

QEProject.numItems
******************

``qe.project.numItems``

**Description**

Retrieves the number of items, in the :ref:`project.rootitem`, in the project.

**Type**

Number; read-only.

.. warning:: This appears to ignore any items that are bins.

----

.. _qeproject.numSequenceItems:

QEProject.numSequenceItems
**************************

``qe.project.numSequenceItems``

**Description**

Retrieves the number of sequences, in the :ref:`project.rootitem`, in the project.

**Type**

Number; read-only.

.. warning:: This appears to return the number of sequences that exist when :ref:`app.enableqe` is called and doesn't update when new sequences are created, moved or deleted.

----

.. _qeproject.numSequences:

QEProject.numSequences
**********************

``qe.project.numSequences``

**Description**

Retrieves the number of :ref:`Sequence <sequence>` objects in the project.

**Type**

Number; read-only.

----

=======
Methods
=======

.. _qeproject.close:

QEProject.close()
*****************

``qe.project.close(saveFirst, promptIfDirty)``

**Description**

Closes the project.

**Parameters**

=================  ===========  ==========================================================================================================
Argument           Type         Description
=================  ===========  ==========================================================================================================
``saveFirst``      ``Boolean``  If ``true``, the project will be saved before closing.
``promptIfDirty``  ``Boolean``  If ``true`` and there are unsaved changes, the user will be asked whether they want to save changes first.
=================  ===========  ==========================================================================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.deletePreviewFiles:

QEProject.deletePreviewFiles()
******************************

``qe.project.deletePreviewFiles(arg)``

**Description**

Deletes the preview files of the project.

**Parameters**

========  ===========  ===========
Argument  Type         Description
========  ===========  ===========
``arg``   ``String``   Unknown.
========  ===========  ===========

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.findItemByID:

QEProject.findItemByID()
************************

``qe.project.findItemByID(id)``

**Description**

Retrieves the :ref:`qeprojectitem` with the specified id. 

**Parameters**

========  ===========  =========================
Argument  Type         Description
========  ===========  =========================
``id``    ``String``   :ref:`projectitem.nodeid` 
========  ===========  =========================

**Returns**

Returns a :ref:`qeprojectitem`.

----

.. _qeproject.flushCache:

QEProject.flushCache()
**********************

``qe.project.flushCache()``

**Description**

Flushes the project cache.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.getActiveSequence:

QEProject.getActiveSequence()
*****************************

``qe.project.getActiveSequence()``

**Description**

Retrieves the currently active sequence.

**Parameters**

None.

**Returns**

Returns a :ref:`qesequence`.

----

.. _qeproject.getAudioEffectByName:

QEProject.getAudioEffectByName()
********************************

``qe.project.getAudioEffectByName(name, channelType)``

**Description**

Retrieves an audio effect.

**Parameters**

===============  ===========  =======================================================================
Argument         Type         Description
===============  ===========  =======================================================================
``name``         ``String``   The **localized** name of the audio effect.
``channelType``  ``Integer``  The channel type. Optional, default is ``1``. Use ``4`` as a catch-all.
===============  ===========  =======================================================================

===============  ===========
``channelType``  Description
===============  ===========
``0``            Mono
``1``            Stereo
``2``            5.1
``4``            All
===============  ===========

**Returns**

Returns a :ref:`qeaudioeffect`.

----

.. _qeproject.getAudioEffectList:

QEProject.getAudioEffectList()
******************************

``qe.project.getAudioEffectList(channelType)``

**Description**

Retrieves a list of all audio effect names, with the specified channel type.

**Parameters**

===============  ===========  ============================================
Argument         Type         Description
===============  ===========  ============================================
``channelType``  ``Integer``  The channel type. Optional, default is ``1``
===============  ===========  ============================================

===============  ===========
``channelType``  Description
===============  ===========
``0``            Mono
``1``            Stereo
``2``            5.1
``4``            All
===============  ===========

**Returns**

Returns an array of **localized** strings.

----

.. _qeproject.getAudioTransitionByName:

QEProject.getAudioTransitionByName()
************************************

``qe.project.getAudioTransitionByName(name)``

**Description**

Retrieves an audio transition.

**Parameters**

========  ==========  ===============================================
Argument  Type        Description
========  ==========  ===============================================
``name``  ``String``  The **localized** name of the audio transition.
========  ==========  ===============================================

**Returns**

Returns a :ref:`qeaudiotransition`.

----

.. _qeproject.getAudioTransitionList:

QEProject.getAudioTransitionList()
**********************************

``qe.project.getAudioTransitionList()``

**Description**

Retrieves a list of all audio transition names.

**Parameters**

None.

**Returns**

Returns an array of **localized** strings.

----

.. _qeproject.getBinAt:

QEProject.getBinAt()
********************

``qe.project.getBinAt(index)``

**Description**

Retrieves a bin, in the project, by its index. The indices are set in creation order.

**Parameters**

=========  ===========  =====================
Argument   Type         Description
=========  ===========  =====================
``index``  ``Integer``  The index of the bin.
=========  ===========  =====================

**Returns**

Returns a :ref:`qeprojectitemcontainer`

----

.. _qeproject.getItemAt:

QEProject.getItemAt()
*********************

``qe.project.getItemAt(index)``

**Description**

Retrieves a project item, in the :ref:`project.rootitem`, by its index. The indices are set in creation order.

**Parameters**

=========  ===========  =====================
Argument   Type         Description
=========  ===========  =====================
``index``  ``Integer``  The index of the bin.
=========  ===========  =====================

**Returns**

Returns a :ref:`qeprojectitem`.

.. warning:: This appears to ignore any items that are bins.

----

.. _qeproject.getRemainingMetadataCacheIndexCount:

QEProject.getRemainingMetadataCacheIndexCount()
***********************************************

``qe.project.getRemainingMetadataCacheIndexCount()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a number.

----

.. _qeproject.getRendererNames:

QEProject.getRendererNames()
****************************

``qe.project.getRendererNames()``

**Description**

Retrieves a list of the available renderer names for the project.

**Parameters**

None.

**Returns**

Returns an array of strings.

----

.. _qeproject.getSequenceAt:

QEProject.getSequenceAt()
*************************

``qe.project.getSequenceAt(index)``

**Description**

Retrieves a sequence, in the :ref:`project.rootitem`, by its index. The indices are set in creation order.

**Parameters**

=========  ===========  ==========================
Argument   Type         Description
=========  ===========  ==========================
``index``  ``Integer``  The index of the sequence.
=========  ===========  ==========================

**Returns**

Returns a :ref:`qesequence`.

.. warning:: This appears to only work with sequences that exist when :ref:`app.enableqe` is called.

----

.. _qeproject.getSequenceItemAt:

QEProject.getSequenceItemAt()
*****************************

``qe.project.getSequenceItemAt(index)``

**Description**

Retrieves the :ref:`qeprojectitem`, of the specified sequence, in the project, by its index. The indices are set in creation order.
 
**Parameters**

=========  ===========  ==========================
Argument   Type         Description
=========  ===========  ==========================
``index``  ``Integer``  The index of the sequence.
=========  ===========  ==========================

**Returns**

Returns a :ref:`qeprojectitem`.

.. warning:: This appears to only work with sequences that exist when :ref:`app.enableqe` is called.

----

.. _qeproject.getVideoEffectByName:

QEProject.getVideoEffectByName()
********************************

``qe.project.getVideoEffectByName(name, isMatchName)``

**Description**

Retrieves a video effect.

**Parameters**

===============  ===========  ===============================================
Argument         Type         Description
===============  ===========  ===============================================
``name``         ``String``   The **localized** name of the video effect.
``isMatchName``  ``Boolean``  If ``true``, the specified name is a matchName.
===============  ===========  ===============================================

**Returns**

Returns a :ref:`qevideoeffect`.

----

.. _qeproject.getVideoEffectList:

QEProject.getVideoEffectList()
******************************

``qe.project.getVideoEffectList(effectType)``

**Description**

Retrieves a list of all video effect names of the specified type.

**Parameters**

==============  ===========  ===========================================
Argument        Type         Description
==============  ===========  ===========================================
``effectType``  ``Integer``  The effect type. Optional, default is ``0``
==============  ===========  ===========================================

==============  ====================
``effectType``  Description
==============  ====================
``0``           All
``1``           Accelerated Effects
``2``           32-bit Color Effects
``3``           YUV Effects
==============  ====================

**Returns**

Returns an array of **localized** strings.

----

.. _qeproject.getVideoTransitionByName:

QEProject.getVideoTransitionByName()
************************************

``qe.project.getVideoTransitionByName(name)``

**Description**

Retrieves an video transition.

**Parameters**

========  ==========  =================================
Argument  Type        Description
========  ==========  =================================
``name``  ``String``  The name of the video transition.
========  ==========  =================================

**Returns**

Returns a :ref:`qevideotransition`.

----

.. _qeproject.getVideoTransitionList:

QEProject.getVideoTransitionList(transitionType)
************************************************

``qe.project.getVideoTransitionList()``

**Description**

Retrieves a list of all video transition names of the specified type.

**Parameters**

==================  ===========  ===============================================
Argument            Type         Description
==================  ===========  ===============================================
``transitionType``  ``Integer``  The transition type. Optional, default is ``0``
==================  ===========  ===============================================

==================  ====================
``transitionType``  Description
==================  ====================
``0``               All
``1``               Accelerated Effects
``2``               32-bit Color Effects
``3``               YUV Effects
==================  ====================

**Returns**

Returns an array of **localized** strings.

----

.. _qeproject.newBin:

QEProject.newBin()
******************

``qe.project.newBin(name)``

**Description**

Creates a bin in the :ref:`project.rootitem` of the project, with the specified name. 

**Parameters**

========  ==========  ==================================
Argument  Type        Description
========  ==========  ==================================
``name``  ``String``  The name of the bin to be created.
========  ==========  ==================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.newBin:

QEProject.newBin()
******************

``qe.project.newBin(name)``

**Description**

Creates a bin in the :ref:`project.rootitem` of the project, with the specified name. 

**Parameters**

========  ==========  ==================================
Argument  Type        Description
========  ==========  ==================================
``name``  ``String``  The name of the bin to be created.
========  ==========  ==================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.newBlackVideo:

QEProject.newBlackVideo()
*************************

``qe.project.newBlackVideo(width, height, timebase, numerator, denominator)``

**Description**

Creates a new black video in the :ref:`project.rootitem` of the project, with the specified name.

**Parameters**

===============  ==========  ======================================
Argument         Type        Description
===============  ==========  ======================================
``width``        ``Number``  The width of the black video.
``height``       ``Number``  The height of the black video.
``frameRate``    ``Number``  The frame rate, in **seconds**.
``numerator``    ``Number``  Numerator of the pixel aspect ratio.
``denominator``  ``Number``  Denominator of the pixel aspect ratio.
===============  ==========  ======================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.newColorMatte:

QEProject.newColorMatte()
*************************

``qe.project.newColorMatte(width, height, timebase, numerator, denominator)``

**Description**

Creates a new color matte in the :ref:`project.rootitem` of the project, with the specified name.

**Parameters**

===============  ==========  ======================================
Argument         Type        Description
===============  ==========  ======================================
``width``        ``Number``  The width of the color matte.
``height``       ``Number``  The height of the color matte.
``frameRate``    ``Number``  The frame rate, in **seconds**.
``numerator``    ``Number``  Numerator of the pixel aspect ratio.
``denominator``  ``Number``  Denominator of the pixel aspect ratio.
===============  ==========  ======================================

**Returns**

Returns a boolean; ``true`` if successful.

.. note:: This will bring up a 'Color Picker' dialog, followed by a 'Choose Name' dialog. Both must be completed for the new color matte to be created.

----

.. _qeproject.newTransparentVideo:

QEProject.newTransparentVideo()
*******************************

``qe.project.newTransparentVideo(width, height, timebase, numerator, denominator)``

**Description**

Creates a new transparent video in the :ref:`project.rootitem` of the project, with the specified name.

**Parameters**

===============  ==========  ======================================
Argument         Type        Description
===============  ==========  ======================================
``width``        ``Number``  The width of the transparent video.
``height``       ``Number``  The height of the transparent video.
``frameRate``    ``Number``  The frame rate, in **seconds**.
``numerator``    ``Number``  Numerator of the pixel aspect ratio.
``denominator``  ``Number``  Denominator of the pixel aspect ratio.
===============  ==========  ======================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.newUniversalCountingLeader:

QEProject.newUniversalCountingLeader()
**************************************

``qe.project.newUniversalCountingLeader(width, height, timebase, numerator, denominator, sampleRate)``

**Description**

Creates a new universal counting leader in the :ref:`project.rootitem` of the project, with the specified name.

**Parameters**

===============  ==========  ============================================
Argument         Type        Description
===============  ==========  ============================================
``width``        ``Number``  The width of the universal counting leader.
``height``       ``Number``  The height of the universal counting leader.
``frameRate``    ``Number``  The frame rate, in **seconds**.
``numerator``    ``Number``  Numerator of the pixel aspect ratio.
``denominator``  ``Number``  Denominator of the pixel aspect ratio.
``sampleRate``   ``Number``  Sample rate, in Hz. Use ``0`` for default.
===============  ==========  ============================================

**Returns**

Returns a boolean; ``true`` if successful.

.. note:: This will bring up the 'Universal Counting Leader Setup' dialog which must be completed for the new universal counting leader to be created.

----

.. _qeproject.redo:

QEProject.redo()
****************

``qe.project.redo()``

**Description**

Redoes the last action, in the project.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.resetNumFilesCounter:

QEProject.resetNumFilesCounter()
********************************

``qe.project.resetNumFilesCounter()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.setRenderer:

QEProject.setRenderer()
***********************

``qe.project.setRenderer(name)``

**Description**

Sets the renderer of the project.

**Parameters**

========  ==========  =========================
Argument  Type        Description
========  ==========  =========================
``name``  ``String``  The name of the renderer.
========  ==========  =========================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.sizeOnDisk:

QEProject.sizeOnDisk()
**********************

``qe.project.sizeOnDisk()``

**Description**

Retreives the size of the project, in bytes, including any external media.

**Parameters**

None.

**Returns**

Returns a number.

----

.. _qeproject.undo:

QEProject.undo()
****************

``qe.project.undo()``

**Description**

Undoes the last action, in the project.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qeproject.undoStackIndex:

QEProject.undoStackIndex()
**************************

``qe.project.undoStackIndex()``

**Description**

Retreives the current position within the undo stack. This is the amount of actions that can be undone.

**Parameters**

None

**Returns**

Returns a boolean; ``true`` if successful.