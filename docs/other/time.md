<a id="time"></a>

# Time object

`myTime = new Time();`

**Description**

An object representing a time. Internally, the time is computed in `ticks`; there are 254016000000 ticks per second. That time can be accessed in different representations, including as a timecode string.

---

## Attributes

<a id="time-seconds"></a>

### Time.seconds

`myTime.seconds`

**Description**

The time value, expressed in seconds.

**Type**

Number.

---

<a id="time-ticks"></a>

### Time.ticks

`myTime.ticks`

**Description**

The time value, expressed in ticks.

**Type**

String.

---

## Methods

<a id="time-getformatted"></a>

### Time.getFormatted()

`myTime.getFormatted(frameRate, displayFormat)`

**Description**

Returns the value of the `Time` passed, as a string, formatted in the specified display format.

**Parameters**

| Argument        | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `frameRate`     | `Time` | Time object with a duration of a single frame of the frame rate to be used.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `displayFormat` | `int`  | The display format to use. Will be one of the following:<br/><br/>TIMEDISPLAY_24Timecode                                = 100;<br/><br/>> TIMEDISPLAY_25Timecode                                = 101;<br/><br/>> TIMEDISPLAY_2997DropTimecode                  = 102;<br/><br/>> TIMEDISPLAY_2997NonDropTimecode               = 103;<br/><br/>> TIMEDISPLAY_30Timecode                                = 104;<br/><br/>> TIMEDISPLAY_50Timecode                                = 105;<br/><br/>> TIMEDISPLAY_5994DropTimecode                  = 106;<br/><br/>> TIMEDISPLAY_5994NonDropTimecode               = 107;<br/><br/>> TIMEDISPLAY_60Timecode                                = 108;<br/><br/>> TIMEDISPLAY_Frames                                    = 109;<br/><br/>> TIMEDISPLAY_23976Timecode                             = 110;<br/><br/>> TIMEDISPLAY_16mmFeetFrames                    = 111;<br/><br/>> TIMEDISPLAY_35mmFeetFrames                    = 112;<br/><br/>> TIMEDISPLAY_48Timecode                                = 113;<br/><br/>> TIMEDISPLAY_AudioSamplesTimecode          = 200;<br/><br/>> TIMEDISPLAY_AudioMsTimecode                   = 201; |

**Returns**

A `String`.

---

<a id="time-setsecondsasfraction"></a>

### Time.setSecondsAsFraction()

`myTime.setSecondsAsFraction(numerator, denominator)`

**Description**

Sets the Time object to the result of dividing the numerator by the denominator.

**Parameters**

Both the numerator and the denominator are `ints`.

**Returns**

Boolean; `true` if successful.
