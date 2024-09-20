.. highlight:: javascript

.. _qe:

QE object
=========

.. warning:: The QE DOM project model's refreshing is unreliable and for that reason, amongst others, the QE DOM remains officially unsupported and not recommended.

``qe``

**Description**

The **QE** (Quality Engineering) DOM was initially developed for internal testing and automation. Although it was designed for internal use, it is now accessible to all and offers several significant features. Officially, the QE DOM is unsupported, but it is widely used to enable lots of interesting and useful functions.

To use anything from the QE DOM, you must first enable it with a call to :ref:`app.enableqe`. 

.. note:: The majority of QE attributes and methods are included in these docs, but to avoid unneccessary confusion, those that are exact duplicates of non-QE attributes or methods have been excluded. Of those included, some have not been fully investigated and thus have limited information attached to them. Please experiment and contribute if you can!

----

==========
Attributes
==========

.. _qe.audioChannelMapping:

QE.audioChannelMapping
**********************

``qe.audioDisplayFormat``

**Description**

Unknown.

**Type**

Integer; read-only.

----

.. _qe.codeProfiler:

QE.codeProfiler
***************

``qe.codeProfiler``

**Description**

Unknown.

**Type**

Object; read-only.

----

.. _qe.config:

QE.config
*********

``qe.config``

**Description**

Unknown.

**Type**

String; read-only.

----

.. _qe.ea:

QE.ea
*****

``qe.ea``

**Description**

Provides access to the :ref:`qeea`.

**Type**

:ref:`qeea`.

----

.. _qe.language:

QE.language
***********

``qe.language``

**Description**

Retrieves the language in which Premiere Pro is currently running. These language codes follow the BCP 47 standard, which specifies the language and region. One of:

==========  ==================
``String``  Language
==========  ==================
``de_DE``   German (Germany)
``en_US``   English (United States)
``es_ES``   Spanish (Spain)
``fr_FR``   French (France)
``it_IT``   Italian (Italy)
``ja_JP``   Japanese (Japan)
``ko_KR``   Korean (South Korea)
``pt_BR``   Portguese (Brazil)
``ru_RU``   Russian (Russia)
``zh_CN``   Chinese (mainland China)
``zh_TW``   Chinese (Taiwan)
==========  ==================

**Type**

String; read-only.

----

.. _qe.location:

QE.location
***********

``qe.location``

**Description**

Retrieves the file path of the Premiere Pro application.

**Type**

String; read-only.

----

.. _qe.name:

QE.name
*******

``qe.name``

**Description**

Retrieves the name of the Premiere Pro application. Unsurprisingly, it should return ``Premiere Pro``

**Type**

String; read-only.

----

.. _qe.platform:

QE.platform
************

``qe.platform``

**Description**

Retrieves the operating system on which Premiere Pro is currently running.

**Type**

String; read-only.

----

.. _qe.project:

QE.project
**********

``qe.project``

**Description**

Provides access to the :ref:`qeproject` of the currently active project.

**Type**

:ref:`qeproject`.

----

.. _qe.source:

QE.source
*********

``qe.source``

**Description**

Provides access to the :ref:`qesource`. This is similar to the :ref:`sourcemonitor`.

**Type**

:ref:`qesource`.

----

QE.tqm
******

``qe.tqm``

**Description**

Unknown.

**Type**

Object; read-only.

----

QE.version
**********

``qe.version``

**Description**

Retrieves the version of Premiere Pro that is currently running.

**Type**

String; read-only.

----

=======
Methods
=======

.. _qe.beginDroppedFrameLogging:

QE.beginDroppedFrameLogging()
*****************************

``qe.beginDroppedFrameLogging(arg)``

**Description**

Unknown.

**Parameters**

========  ==========  ===========
Argument    Type      Description
========  ==========  ===========
``arg``   ``String``  Unknown.
========  ==========  ===========

**Returns**

Returns a boolean.

----

.. _qe.disablePerformanceLogging:

QE.disablePerformanceLogging()
******************************

``qe.disablePerformanceLogging()``

**Description**

Unknown.

**Parameters**

Disables ``FE.PerformanceLogging``, in the 'Debug Database View', in the console.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.enablePerformanceLogging:

QE.enablePerformanceLogging()
*****************************

``qe.enablePerformanceLogging()``

**Description**

Enables ``FE.PerformanceLogging``, in the 'Debug Database View', in the console.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.enablePlayStats:

QE.enablePlayStats()
********************

``qe.enablePlayStats()``

**Description**

Enables ``Player.EnablePerformanceStatics``, in the 'Debug Database View', in the console.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.endDroppedFrameLogging:

QE.endDroppedFrameLogging()
***************************

``qe.endDroppedFrameLogging()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a boolean.

----

.. _qe.executeConsoleCommand:

QE.executeConsoleCommand()
**************************

``qe.executeConsoleCommand(command)``

**Description**

Runs a command in Premiere Pro's console.

.. note:: The console must be open before you run this method. Open the console by pressing CTRL/CMD + F12.

**Parameters**

===========  ==========  ==============================
Argument     Type        Description
===========  ==========  ==============================
``command``  ``String``  Command to run in the console.
===========  ==========  ==============================

**Returns**

Returns a boolean; ``true`` if successful.

**Example**

.. code-block:: javascript

    var cmd = "con.help";
    qe.executeconsoleCommand(cmd); //shows all currently installed commands in the console.

----

.. _qe.method:

QE.exit()
*********

``qe.exit()``

**Description**

Closes Premiere Pro. If any open projects are unsaved, a prompt will appear before closing.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.getDebugDatabaseEntry:

QE.getDebugDatabaseEntry()
**************************

``qe.getDebugDatabaseEntry(debugVariable)``

**Description**

Retrieves the value of the debug variable from the debug database.

**Parameters**

=================  ==========  =======================================
Argument           Type        Description
=================  ==========  =======================================
``debugVariable``  ``String``  Debug variable from the debug database.
=================  ==========  =======================================

**Returns**

Returns a string.

----

.. _qe.getDroppedFrames:

QE.getDroppedFrames()
*********************

``qe.getDroppedFrames()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a string.

----

.. _qe.getModalWindowID:

QE.getModalWindowID()
*********************

``qe.getModalWindowID()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a string.

----

.. _qe.getProgressContainerJSON:

QE.getProgressContainerJSON()
*****************************

``qe.getProgressContainerJSON()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a JSON string.

**Example**

.. code-block:: json

    {
        "mProgressCategories": [
            {
                "mProgressItems": [],
                "mShowNumberOfProcessingProgressItems": false,
                "mTitle": "Auto Reframe"
            },
            {
                "mProgressItems": [],
                "mShowNumberOfProcessingProgressItems": false,
                "mTitle": "Auto Saving Projects"
            },
            {
                "mProgressItems": [
                    {
                        "mState": {
                            "mEndTime": "",
                            "mMaxValue": 1,
                            "mProgressIsUnknown": false,
                            "mProgressState": 0,
                            "mRemainingTime": "",
                            "mRemoveAfterCancellation": false,
                            "mStartTime": "2024-Jul-28 19:51:52",
                            "mStatusMessage": "",
                            "mTitle": "Initializing AudioCategorization-20230406",
                            "mToolTip": "",
                            "mType": "00000000-0000-0000-0000-000000000000",
                            "mValue": 1
                        }
                    }
                ],
                "mShowNumberOfProcessingProgressItems": false,
                "mTitle": "Initializing Machine Learning Model"
            },
            {
                "mProgressItems": [],
                "mShowNumberOfProcessingProgressItems": false,
                "mTitle": "Auto-Tagging Audio"
            }
        ]
    }

    

----

.. _qe.getSequencePresets:

QE.getSequencePresets()
***********************

``qe.getSequencePresets()``

**Description**

Retrieves file paths of all available sequence presets (.sqpreset file) .

**Parameters**

None.

**Returns**

Returns an array.

----

.. _qe.isFeatureEnabled:

QE.isFeatureEnabled()
*********************

``qe.isFeatureEnabled(arg)``

**Description**

Unknown.

**Parameters**

========  ==========  ===========
Argument    Type      Description
========  ==========  ===========
``arg``   ``String``  Unknown.
========  ==========  ===========

**Returns**

Returns a boolean.

----

.. _qe.isPerformanceLoggingEnabled:

QE.isPerformanceLoggingEnabled()
********************************

``qe.isPerformanceLoggingEnabled()``

**Description**

Returns whether or not performance logging is enabled.

Enable or disable performance logging with :ref:`qe.enableperformancelogging` and :ref:`qe.disableperformancelogging`.  

**Parameters**

None.

**Returns**

Returns a boolean.

----

.. _qe.localize:

QE.localize()
*************

``qe.localize(arg)``

**Description**

Unknown.

**Parameters**

========  ==========  ===========
Argument    Type      Description
========  ==========  ===========
``arg``   ``String``  Unknown.
========  ==========  ===========

**Returns**

Returns a string.

----

.. _qe.newProject:

QE.newProject()
***************

``qe.newProject(filePath)``

**Description**

Creates a new Premiere Pro project file at the specified file path.

**Parameters**

============  ==========  ==========================================================
Argument      Type        Description
============  ==========  ==========================================================
``filePath``  ``String``  File path to new project, including .pproj file extension.
============  ==========  ==========================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.open:

QE.open()
*********

``qe.open(filePath)``

**Description**

Opens the Premiere Pro project file with the specified file path.

**Parameters**

============  ==========  ===========================================================
Argument      Type        Description
============  ==========  ===========================================================
``filePath``  ``String``  File path of project file, including .pproj file extension.
============  ==========  ===========================================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.outputToconsole:

QE.outputToconsole()
********************

``qe.outputToconsole(message)``

**Description**

Outputs a message to the console.

.. note:: The console must be open to see the message. Open the console by pressing CTRL/CMD + F12.

**Parameters**

===========  ==========  =====================================
Argument     Type        Description
===========  ==========  =====================================
``message``  ``String``  The message to output to the console.
===========  ==========  =====================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.resetProject:

QE.resetProject()
*****************

``qe.resetProject()``

**Description**

Resets the currently active project, although it's unclear what settings or parameters this resets.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.setAudioChannelMapping:

QE.setAudioChannelMapping()
***************************

``qe.setAudioChannelMapping(arg)``

**Description**

Unknown.

**Parameters**

========  ===========  ===========
Argument  Type         Description
========  ===========  ===========
``arg``   ``Integer``  Unknown.
========  ===========  ===========

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.setDebugDatabaseEntry:

QE.setDebugDatabaseEntry()
**************************

``qe.setDebugDatabaseEntry(arg1, arg2)``

**Description**

Sets the value of the debug variable in the debug database.

**Parameters**

=================  ==========  =========================================
Argument           Type        Description
=================  ==========  =========================================
``debugVariable``  ``String``  Debug variable from the debug database.
``debugValue``     ``String``  Value to which to set the debug variable.
=================  ==========  =========================================

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.startPlayback:

QE.startPlayback()
******************

``qe.startPlayback()``

**Description**

Starts playback in the currently active sequence.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.stop:

QE.stop()
*********

``qe.stop()``

**Description**

Unknown.

**Parameters**

None.

**Returns**

Returns a boolean.

----

.. _qe.stopPlayback:

QE.stopPlayback()
*****************

``qe.stopPlayback()``

**Description**

Stops playback in the currently active sequence.

**Parameters**

None.

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.wait:

QE.wait()
*********

``qe.wait(milliseconds)``

**Description**

Suspends the calling thread for the given number of milliseconds.

**Parameters**

================  ===========  =============
Argument          Type         Description
================  ===========  =============
``milliseconds``  ``Integer``  Milliseconds.
================  ===========  =============

**Returns**

Returns a boolean; ``true`` if successful.

----

.. _qe.write:

QE.write()
**********

``qe.write(arg)``

**Description**

Unknown.

**Parameters**

========  ==========  ===========
Argument    Type      Description
========  ==========  ===========
``arg``   ``String``  Unknown.
========  ==========  ===========

**Returns**

Returns a boolean.