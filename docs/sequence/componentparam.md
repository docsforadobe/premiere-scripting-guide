# ComponentParam object

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index]`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index]`
<br/>

#### Description

The ComponentParam object represents a parameter associated with a component, applied to a [TrackItem object](../item/trackitem.md).

!!! note
    For a developer working across different localizations, it's possible to find the corresponding keys by comparing ZStrings.

    Below is an example between En and De. Here are the paths to the files:
    `C:\Program Files\Adobe\Adobe Premiere Pro 2024\Dictionaries\de_DE\zdictionary_PPRO_de_DE.dat` - ("…anti-Flimmer Filter")
    `C:\Program Files\Adobe\Adobe Premiere Pro 2024\Dictionaries\en_DE\zdictionary_PPRO_en_US.dat` - ("…anti-flicker Filter")

---

## Attributes

### ComponentParam.displayName

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].displayName`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].displayName`
<br/>

#### Description

The name of the component parameter, as it is displayed to the user. Localized.

#### Type

String; read-only.

---

## Methods

### ComponentParam.addKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].addKey(time)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].addKey(time)`
<br/>

#### Description

Adds a keyframe to the component parameter stream, at the specified time. Note: This can only be set on parameters which support keyframing.

#### Parameters

| Argument |              Type               |            Description             |
| -------- | ------------------------------- | ---------------------------------- |
| `time`   | [Time object](../other/time.md) | When the keyframe should be added. |

#### Returns

Returns `0` if successful.

---

### ComponentParam.areKeyframesSupported()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].areKeyframesSupported()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].areKeyframesSupported()`
<br/>

#### Description

Retrieves whether keyframes are supported, for this component parameter.

#### Parameters

None.

#### Returns

Returns `true` if keyframes are supported; `false` if not.

---

### ComponentParam.findNearestKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findNearestKey(timeToCheck, threshold)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findNearestKey(timeToCheck, threshold)`
<br/>

#### Description

Sets whether the component parameter varies, over time. Note: This can only be set on parameters which support keyframing.

#### Parameters

|   Argument    |  Type   |                     Description                     |
| ------------- | ------- | --------------------------------------------------- |
| `timeToCheck` |         | Start search from a given time                      |
| `threshold`   | Integer | A temporal distance, in either direction, in ticks. |

#### Returns

Returns a Time value, indicating when the closest keyframe is.

---

### ComponentParam.findNextKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findNextKey(timeToCheck)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findNextKey(timeToCheck)`
<br/>

#### Description

Returns the keyframe temporally subsequent to the provided `timeToCheck`. Note: This can only be set on parameters which support keyframing.

#### Parameters

|   Argument    | Type |           Description           |
| ------------- | ---- | ------------------------------- |
| `timeToCheck` |      | Start search from a given time. |

#### Returns

Returns a Time value, indicating when the closest keyframe is, or `0` if there is no available subsequent keyframe.

---

### ComponentParam.findPreviousKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].findPreviousKey(timeToCheck)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].findPreviousKey(timeToCheck)`
<br/>

#### Description

Returns the keyframe temporally previous to the provided `timeToCheck`. Note: This can only be set on parameters which support keyframing.

#### Parameters

|   Argument    | Type |           Description           |
| ------------- | ---- | ------------------------------- |
| `timeToCheck` |      | Start search from a given time. |

#### Returns

Returns a Time value, indicating when the closest keyframe is, or `0` if there is no available previous keyframe.

---

### ComponentParam.getColorValue()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getColorValue()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getColorValue()`
<br/>

#### Description

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

#### Parameters

None.

#### Returns

Returns a Color containing the values found in the component parameter stream, or `0` if unsuccessful.

---

### ComponentParam.getKeys()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getKeys()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getKeys()`
<br/>

#### Description

Returns an array of all keyframes on the `timeToCheck` component parameter. Note: This can only be set on parameters which support keyframing.

#### Parameters

None.

#### Returns

Returns an array of Time values, indicating at what time each keyframe occurs, or `0` if no keyframes are available.

---

### ComponentParam.getValue()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValue()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValue()`
<br/>

#### Description

Obtains the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

#### Parameters

None.

#### Returns

Returns the value of the component parameter stream; the return varies with stream type.

---

### ComponentParam.getValueAtKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValueAtKey(time)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValueAtKey(time)`
<br/>

#### Description

Retrieves the value of the component parameter stream, at the specified keyframe time. Note: Can only be used with keyframeable parameter streams.

#### Parameters

| Argument |              Type               |                        Description                        |
| -------- | ------------------------------- | --------------------------------------------------------- |
| `time`   | [Time object](../other/time.md) | A time from which the keyframe value should be retrieved. |

#### Returns

Returns the value of the component parameter stream at `time`, or `0` if unsuccessful.

---

### ComponentParam.getValueAtTime()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].getValueAtTime(time)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].getValueAtTime(time)`
<br/>

#### Description

Retrieves the value of the component parameter stream, at the specified time. If the value is between two keyframes then interpolation takes place.

#### Parameters

| Argument |              Type               |                        Description                        |
| -------- | ------------------------------- | --------------------------------------------------------- |
| `time`   | [Time object](../other/time.md) | A time from which the keyframe value should be retrieved. |

#### Returns

Returns the value of the component parameter stream at `time`, or `0` if unsuccessful.

---

### ComponentParam.isTimeVarying()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].isTimeVarying()`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].isTimeVarying()`
<br/>

#### Description

Retrieves whether the component parameter varies, over time.

#### Parameters

None.

#### Returns

Returns `true` if the parameter varies over time; `false` if not.

---

### ComponentParam.removeKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].removeKey(time)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].removeKey(time)`
<br/>

#### Description

Removes a keyframe on the component parameter stream, at the specified time. Note: This can only be set on parameters which support keyframing.

#### Parameters

| Argument |              Type               |                          Description                          |
| -------- | ------------------------------- | ------------------------------------------------------------- |
| `time`   | [Time object](../other/time.md) | A time value, indicating when the keyframe should be removed. |

#### Returns

Returns `0` if successful.

---

### ComponentParam.removeKeyRange()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].removeKeyRange(startTime, endTime)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].removeKeyRange(startTime, endTime)`
<br/>

#### Description

Removes all keyframes from the component parameter stream, between the specified times. Note: This can only be set on parameters which support keyframing.

#### Parameters

|  Argument   |              Type               |                       Description                        |
| ----------- | ------------------------------- | -------------------------------------------------------- |
| `startTime` | [Time object](../other/time.md) | The times (inclusive) to begin the removal of keyframes. |
| `endTime`   | [Time object](../other/time.md) | The times to end the removal of keyframes.               |

#### Returns

Returns `0` if successful.

---

### ComponentParam.setColorValue()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setColorValue(alpha, red, green, blue, updateUI)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setColorValue(alpha, red, green, blue, updateUI)`
<br/>

#### Description

Sets the values within a component parameter stream, representing a Color.

#### Parameters

|  Argument  |  Type   |                                      Description                                      |
| ---------- | ------- | ------------------------------------------------------------------------------------- |
| `alpha`    | Integer | Alpha value.                                                                          |
| `red`      | Integer | Red value.                                                                            |
| `green`    | Integer | Green value.                                                                          |
| `blue`     | Integer | Blue value.                                                                           |
| `updateUI` | Integer | If `1`, will force Premiere Pro to update UI, after updating the value of the stream. |

#### Returns

Returns `0` if successful.

---

### ComponentParam.setInterpolationTypeAtKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setInterpolationTypeAtKey(time, interpretationType, [updateUI])`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setInterpolationTypeAtKey(time, interpretationType, [updateUI])`
<br/>

#### Description

Specifies the interpolation type to be assigned to the keyframe, at the specified time. Note: It Can only be used with keyframeable parameter streams.

#### Parameters

|      Argument       |              Type               |                                                                                                                                                                                                     Description                                                                                                                                                                                                     |
| ------------------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `time`              | [Time object](../other/time.md) | A time of keyframe to modify.                                                                                                                                                                                                                                                                                                                                                                                       |
| `interpolationType` | `type`                          | One of:<ul><li>`0` - `KF_Interp_Mode_Linear`</li><li>`1` - `kfInterpMode_EaseIn_Obsolete`</li><li>`2` - `kfInterpMode_EaseOut_Obsolete`</li><li>`3` - `kfInterpMode_EaseInEaseOut_Obsolete`</li><li>`4` - `KF_Interp_Mode_Hold`</li><li>`5` - `KF_Interp_Mode_Bezier`</li><li>`6` - `KF_Interp_Mode_Time`</li><li>`7` - `kfInterpMode_TimeTransitionStart`</li><li>`8` - `kfInterpMode_TimeTransitionEnd`</li></ul> |
| `updateUI`          | Boolean                         | Whether to update UI afterward.                                                                                                                                                                                                                                                                                                                                                                                     |

#### Returns

Returns `0` if successful.

---

### ComponentParam.setTimeVarying()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setTimeVarying(varying)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setTimeVarying(varying)`
<br/>

#### Description

Sets whether the component parameter varies, over time. Note: This can only be set on parameters which support keyframing.

#### Parameters

| Argument  |  Type   |                                Description                                |
| --------- | ------- | ------------------------------------------------------------------------- |
| `varying` | Boolean | If `true`, component parameter will vary over time; if `false`, it won't. |

#### Returns

Returns `0` if successful.

---

### ComponentParam.setValue()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setValue(value, updateUI)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setValue(value, updateUI)`
<br/>

#### Description

Sets the value of the component parameter stream. Note: This can only work on parameters which are not time-variant.

#### Parameters

|  Argument  |  Type   |                                      Description                                      |
| ---------- | ------- | ------------------------------------------------------------------------------------- |
| `value`    |         | Must be of the appropriate type for the component parameter stream.                   |
| `updateUI` | Integer | If `1`, will force Premiere Pro to update UI, after updating the value of the stream. |

#### Returns

Returns `0` if successful.

---

### ComponentParam.setValueAtKey()

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties[index].setValueAtKey(time, value, updateUI)`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties[index].setValueAtKey(time, value, updateUI)`
<br/>

#### Description

Sets the value of the component parameter stream, at the specified keyframe time. Note: Can only be used with keyframeable parameter streams.

#### Parameters

|  Argument  |              Type               |                                      Description                                      |
| ---------- | ------------------------------- | ------------------------------------------------------------------------------------- |
| `time`     | [Time object](../other/time.md) | A time at which the keyframe value should be set.                                     |
| `value`    |                                 | A value to be set.                                                                    |
| `updateUI` | Integer                         | If `1`, will force Premiere Pro to update UI, after updating the value of the stream. |

#### Returns

Returns `0` if successful.
