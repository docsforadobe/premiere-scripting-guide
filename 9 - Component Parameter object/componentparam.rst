.. highlight:: javascript

.. _componentParam:

Component Parameter object
==========================

``Component Parameter``

**Description**

The **component parameter** object represents a parameter associated with a component, applied to a trackItem.


==========
Attributes
==========

.. _componentParam.displayName:

name
*********************************************

``componentParam.displayName``

**Description**

The name of the component parameter, as it is displayed to the user. Localized.

**Type**

String; read-only.


=======
Methods
=======


.. _componentParam.areKeyframesSupported:

areKeyframesSupported
*********************************************

``componentParam.areKeyframesSupported()``

**Description**

Retrieves whether keyframes are supported, for this component parameter.

**Parameters**

None.

**Returns**

Returns ``true`` if trackItem is selected; ``false`` if not.

----

.. _componentParam.isTimeVarying:

isTimeVarying
*********************************************

``componentParam.isTimeVarying()``

**Description**

Retrieves whether the component parameter varies, over time. 

**Parameters**

None.

**Returns**

Returns ``true`` if the parameter varies over time; ``false`` if not.

----

.. _componentParam.setTimeVarying:

setTimeVarying
*********************************************

``componentParam.setTimeVarying(boolVary)``

**Description**

Sets whether the component parameter varies, over time. Note: This can only be set on parameters which support keyframing.

**Parameters**

If ``boolVary`` is **true**, component parameter will vary over time; if **false**, it won't.

**Returns**

Returns **0** if successful.

----

.. _componentParam.findNearestKey:

findNearestKey
*********************************************

``componentParam.findNearestKey(timeToCheck, thresholdInTicks)``

**Description**

Sets whether the component parameter varies, over time. Note: This can only be set on parameters which support keyframing.

**Parameters**

Starts search from ``timeToCheck``, for ``thresholdInTicks`` temporal distance, in either direction.

**Returns**

Returns a **Time** value, indicating when the closest keyframe is.

----

.. _componentParam.findPreviousKey:

findPreviousKey
*********************************************

``componentParam.findPreviousKey(timeToCheck)``

**Description**

Returns the keyframe temporally previous to the provided ``timeToCheck``. Note: This can only be set on parameters which support keyframing.

**Parameters**

Starts search from ``timeToCheck``.

**Returns**

Returns a **Time** value, indicating when the closest keyframe is, or **0** if there is no available previous keyframe.

----

.. _componentParam.findNextKey:

findNextKey
*********************************************

``componentParam.findNextKey(timeToCheck)``

**Description**

Returns the keyframe temporally subsequent to the provided ``timeToCheck``. Note: This can only be set on parameters which support keyframing.

**Parameters**

Starts search from ``timeToCheck``.

**Returns**

Returns a **Time** value, indicating when the closest keyframe is, or **0** if there is no available subsequent keyframe.

----

.. _componentParam.getKeys:

getKeys
*********************************************

``componentParam.getKeys()``

**Description**

Returns an array of all keyframes on the ``timeToCheck`` component parameter. Note: This can only be set on parameters which support keyframing.

**Parameters**

None.

**Returns**

Returns an **Array** of **Time** values, indicating at what time each keyframe occurs, or **0** if no keyframes are available.


----

.. _componentParam.addKey:

addKey
*********************************************

``componentParam.addKey(time)``

**Description**

Adds a keyframe to the component parameter stream, at the specified time. Note: This can only be set on parameters which support keyframing.

**Parameters**

A **Time** value, indicating when the keyframe should be added.

**Returns**

Returns **0** if successful.

----

.. _componentParam.removeKey:

removeKey
*********************************************

``componentParam.removeKey(time)``

**Description**

Removes a keyframe on the component parameter stream, at the specified time. Note: This can only be set on parameters which support keyframing.

**Parameters**

A **Time** value, indicating when the keyframe should be removed.

**Returns**

Returns **0** if successful.

----

.. _componentParam.removeKeyRange:

removeKeyRange
*********************************************

``componentParam.removeKeyRange(startTime, endTime)``

**Description**

Removes all keyframes from the component parameter stream, between the specified times. Note: This can only be set on parameters which support keyframing.

**Parameters**

**Time** values, indicating at what times (inclusive) to begin and eng the removal of keyframes from the component parameter stream.

**Returns**

Returns **0** if successful.

----

.. _componentParam.getValue:

getValue
*********************************************

``componentParam.getValue()``

**Description**

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

**Parameters**

None.

**Returns**

Returns the value of the component parameter stream; the return varies with stream type.

----

.. _componentParam.setValue:

setValue
*********************************************

``componentParam.setValue(newValue, boolUpdateUI)``

**Description**

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

**Parameters**

The ``newValue`` must be of the appropriate type for the component parameter stream; passing **1** for ``boolUpdateUI`` will force Premiere Pro to update its UI, after updating the value of the stream.

**Returns**

Returns **0** if successful.

----

.. _componentParam.getColorValue:

getColorValue
*********************************************

``componentParam.getColorValue()``

**Description**

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

**Parameters**

The ``newValue`` must be of the appropriate type for the component parameter stream; passing **1** for ``boolUpdateUI`` will force Premiere Pro to update its UI, after updating the value of the stream.

**Returns**

Returns a **Color** containing the values found in the component parameter stream, or **0** if unsuccessful.


----

.. _componentParam.setColorValue:

setColorValue
*********************************************

``componentParam.setColorValue(intAlpha, intRed, intGreen, intBlue, boolUpdateUI)``

**Description**

Sets the values within a component parameter stream, representing a Color.

**Parameters**

Integers representing the alpha, red, green and blue values to be used in the component parameter stream; ``boolUpdateUI`` will force Premiere Pro to update its UI, after updating the value of the stream.

**Returns**

Returns **0** if successful.


----

.. _componentParam.getValueAtKey:

getValueAtKey
*********************************************

``componentParam.getValueAtKey(time)``

**Description**

Retrieves the value of the component parameter stream, at the specified keyframe time. Note: Can only be used with keyframeable parameter streams.

**Parameters**

A ``Time`` from which the keyframe value should be retrieved;

**Returns**

Returns the value of the component parameter stream at ``time``, or **0** if unsuccessful.

----

.. _componentParam.setValueAtKey:

setValueAtKey
*********************************************

``componentParam.setValueAtKey(time, newValue, boolUpdateUI)``

**Description**

Sets the value of the component parameter stream, at the specified keyframe time. Note: Can only be used with keyframeable parameter streams.

**Parameters**

A ``Time`` at which the keyframe value should be set, and a ``newValue`` representing the value to be stored at the keyframe time; ``boolUpdateUI`` will force Premiere Pro to update its UI, after updating the value of the stream..

**Returns**

Returns **0** if successful.

----

.. _componentParam.setInterpolationTypeAtKey:

setInterpolationTypeAtKey
*********************************************

``componentParam.setInterpolationTypeAtKey(time, interpretationType)``

**Description**

Specifies the interpolation typ to be assigned to the keyframe, at the specified time. Note: Can only be used with keyframeable parameter streams.

**Parameters**

A ``Time`` at which the interpretation type should be set (and which must correspond to an extant keyframe), and an ``interpretationType`` being set.

+----------------------------+---------------------------------------------------+
| ``Time``                   | **Time** of keyframe to modify.                   |
+----------------------------+---------------------------------------------------+
| ``interpretationType``     | Must be one of the following:                     |
|                            |    - 0 kfInterpMode_Linear                        |
|                            |    - 1 kfInterpMode_EaseIn_Obsolete               |
|                            |    - 2 kfInterpMode_EaseOut_Obsolete              |
|                            |    - 3 kfInterpMode_EaseInEaseOut_Obsolete        |
|                            |    - 4 kfInterpMode_Hold                          |
|                            |    - 5 kfInterpMode_Bezier                        |
|                            |    - 6 kfInterpMode_Time                          |
|                            |    - 7 kfInterpMode_TimeTransitionStart           |
|                            |    - 8 kfInterpMode_TimeTransitionEnd             |
+----------------------------+---------------------------------------------------+



**Returns**

Returns **0** if successful.

