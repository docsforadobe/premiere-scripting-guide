.. highlight:: javascript

.. _componentParam:

ComponentParam object
==========================

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index]``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index]``

**Description**

The **component parameter** object represents a parameter associated with a component, applied to a :ref:`trackItem`.

----

==========
Attributes
==========

.. _componentParam.displayName:

ComponentParam.displayName
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].displayName``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].displayName``

**Description**

The name of the component parameter, as it is displayed to the user. Localized.

**Type**

String; read-only.

----

=======
Methods
=======

.. _componentParam.addKey:

ComponentParam.addKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].addKey(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].addKey(time)``

**Description**

Adds a keyframe to the component parameter stream, at the specified time. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          :ref:`time`  When the keyframe should be added.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.areKeyframesSupported:

ComponentParam.areKeyframesSupported()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].areKeyframesSupported()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].areKeyframesSupported()``

**Description**

Retrieves whether keyframes are supported, for this component parameter.

**Parameters**

None.

**Returns**

Returns ``true`` if trackItem is selected; ``false`` if not.

----

.. _componentParam.findNearestKey:

ComponentParam.findNearestKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findNearestKey(timeToCheck, threshold)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findNearestKey(timeToCheck, threshold)``

**Description**

Sets whether the component parameter varies, over time. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``timeToCheck``                Start search from a given time
``threshold``                  A temporal distance, in either direction, in **ticks**.
================  ===========  =======================

**Returns**

Returns a **Time** value, indicating when the closest keyframe is.

----

.. _componentParam.findNextKey:

ComponentParam.findNextKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findNextKey(timeToCheck)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findNextKey(timeToCheck)``

**Description**

Returns the keyframe temporally subsequent to the provided ``timeToCheck``. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``timeToCheck``                Start search from a given time.
================  ===========  =======================

**Returns**

Returns a **Time** value, indicating when the closest keyframe is, or **0** if there is no available subsequent keyframe.

----

.. _componentParam.findPreviousKey:

ComponentParam.findPreviousKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findPreviousKey(timeToCheck)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findPreviousKey(timeToCheck)``

**Description**

Returns the keyframe temporally previous to the provided ``timeToCheck``. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``timeToCheck``                Start search from a given time.
================  ===========  =======================

**Returns**

Returns a **Time** value, indicating when the closest keyframe is, or **0** if there is no available previous keyframe.

----

.. _componentParam.getColorValue:

ComponentParam.getColorValue()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getColorValue()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getColorValue()``

**Description**

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

**Parameters**

None.

**Returns**

Returns a **Color** containing the values found in the component parameter stream, or **0** if unsuccessful.

----

.. _componentParam.getKeys:

ComponentParam.getKeys()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getKeys()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getKeys()``

**Description**

Returns an array of all keyframes on the ``timeToCheck`` component parameter. Note: This can only be set on parameters which support keyframing.

**Parameters**

None.

**Returns**

Returns an **Array** of **Time** values, indicating at what time each keyframe occurs, or **0** if no keyframes are available.

----

.. _componentParam.getValue:

ComponentParam.getValue()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValue()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValue()``

**Description**

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

**Parameters**

None.

**Returns**

Returns the value of the component parameter stream; the return varies with stream type.

----

.. _componentParam.getValueAtKey:

ComponentParam.getValueAtKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValueAtKey(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValueAtKey(time)``

**Description**

Retrieves the value of the component parameter stream, at the specified keyframe time. Note: Can only be used with keyframeable parameter streams.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          :ref:`time`  A time from which the keyframe value should be retrieved.
================  ===========  =======================

**Returns**

Returns the value of the component parameter stream at ``time``, or **0** if unsuccessful.

----

.. _componentParam.getValueAtTime:

ComponentParam.getValueAtTime()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValueAtTime(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValueAtTime(time)``

**Description**

Retrieves the value of the component parameter stream, at the specified time. If the value is between two keyframes then interpolation takes place.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          :ref:`time`  A time from which the keyframe value should be retrieved.
================  ===========  =======================

**Returns**

Returns the value of the component parameter stream at ``time``, or **0** if unsuccessful.

----

.. _componentParam.isTimeVarying:

ComponentParam.isTimeVarying()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].isTimeVarying()``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].isTimeVarying()``

**Description**

Retrieves whether the component parameter varies, over time. 

**Parameters**

None.

**Returns**

Returns ``true`` if the parameter varies over time; ``false`` if not.

----

.. _componentParam.removeKey:

ComponentParam.removeKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].removeKey(time)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].removeKey(time)``

**Description**

Removes a keyframe on the component parameter stream, at the specified time. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          :ref:`time`  A time value, indicating when the keyframe should be removed.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.removeKeyRange:

ComponentParam.removeKeyRange()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].removeKeyRange(startTime, endTime)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].removeKeyRange(startTime, endTime)``

**Description**

Removes all keyframes from the component parameter stream, between the specified times. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``startTime``     :ref:`time`  At what times (inclusive) to begin the removal of keyframes.
``endTime``       :ref:`time`  at what times to end the removal of keyframes.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.setColorValue:

ComponentParam.setColorValue()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setColorValue(alpha, red, green, blue, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setColorValue(alpha, red, green, blue, updateUI)``

**Description**

Sets the values within a component parameter stream, representing a Color.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``alpha``         ``Integer``  Alpha value.
``red``           ``Integer``  Red value.
``green``         ``Integer``  Green value.
``blue``          ``Integer``  Blue value.
``updateUI``      ``Integer``  Force to update UI after updating the value of the stream.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.setInterpolationTypeAtKey:

ComponentParam.setInterpolationTypeAtKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setInterpolationTypeAtKey(time, interpretationType)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setInterpolationTypeAtKey(time, interpretationType)``

**Description**

Specifies the interpolation typ to be assigned to the keyframe, at the specified time. Note: Can only be used with keyframeable parameter streams.

**Parameters**

=======================  ===========  =======================
Argument                 Type         Description
=======================  ===========  =======================
``time``                 :ref:`time`  A time  of keyframe to modify.
``interpretationType``   ``type``     Must be one of the following: 

                                      - 0 ``kfInterpMode_Linear``
                                      - 1 ``kfInterpMode_EaseIn_Obsolete``
                                      - 2 ``kfInterpMode_EaseOut_Obsolete``
                                      - 3 ``kfInterpMode_EaseInEaseOut_Obsolete``
                                      - 4 ``kfInterpMode_Hold``
                                      - 5 ``kfInterpMode_Bezier``
                                      - 6 ``kfInterpMode_Time``
                                      - 7 ``kfInterpMode_TimeTransitionStart``
                                      - 8 ``kfInterpMode_TimeTransitionEnd``
=======================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.setTimeVarying:

ComponentParam.setTimeVarying()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setTimeVarying(varying)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setTimeVarying(varying)``

**Description**

Sets whether the component parameter varies, over time. Note: This can only be set on parameters which support keyframing.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``varying``       ``Boolean``  If ``true``, component parameter will vary over time; if ``false``, it won't.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.setValue:

ComponentParam.setValue()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setValue(value, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setValue(value, updateUI)``

**Description**

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``value``                      Must be of the appropriate type for the component parameter stream.
``updateUI``      ``Integer``  If ``1``, will force Premiere Pro to update UI, after updating the value of the stream.
================  ===========  =======================

**Returns**

Returns **0** if successful.

----

.. _componentParam.setValueAtKey:

ComponentParam.setValueAtKey()
*********************************************

|   ``app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setValueAtKey(time, value, updateUI)``
|   ``app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setValueAtKey(time, value, updateUI)``

**Description**

Sets the value of the component parameter stream, at the specified keyframe time. Note: Can only be used with keyframeable parameter streams.

**Parameters**

================  ===========  =======================
Argument          Type         Description
================  ===========  =======================
``time``          :ref:`time`  A time at which the keyframe value should be set.
``value``                      A value to be set.
``updateUI``      ``Integer``  If ``1``, will force Premiere Pro to update UI, after updating the value of the stream.
================  ===========  =======================

**Returns**

Returns **0** if successful.
