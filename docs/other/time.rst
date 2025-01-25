.. highlight:: javascript

.. _time:

Time object
===================

``myTime = new Time();``

#### Description

An object representing a time. Internally, the time is computed in ``ticks``; there are 254016000000 ticks per second. That time can be accessed in different representations, including as a timecode string.

----

==========
Attributes
==========

.. _time.seconds:

Time.seconds
*********************************************

``myTime.seconds``

#### Description

The time value, expressed in seconds.

#### Type

Number.

----

.. _time.ticks:

Time.ticks
*********************************************

``myTime.ticks``

#### Description

The time value, expressed in ticks.

#### Type

String.

----

=======
Methods
=======

.. _time.getFormatted:

Time.getFormatted()
*********************************************

``myTime.getFormatted(frameRate, displayFormat)``

#### Description

Returns the value of the ``Time`` passed, as a string, formatted in the specified display format.

#### Parameters

===================  ===========  =======================
Argument             Type         Description
===================  ===========  =======================
``frameRate``        ``Time``     Time object with a duration of a single frame of the frame rate to be used.
``displayFormat``    ``int``      The display format to use. Will be one of the following:

                                  TIMEDISPLAY_24Timecode				= 100;

								  TIMEDISPLAY_25Timecode				= 101;

								  TIMEDISPLAY_2997DropTimecode			= 102;

								  TIMEDISPLAY_2997NonDropTimecode		= 103;

								  TIMEDISPLAY_30Timecode				= 104;

								  TIMEDISPLAY_50Timecode				= 105;

								  TIMEDISPLAY_5994DropTimecode			= 106;

								  TIMEDISPLAY_5994NonDropTimecode		= 107;

								  TIMEDISPLAY_60Timecode				= 108;

								  TIMEDISPLAY_Frames					= 109;

								  TIMEDISPLAY_23976Timecode				= 110;

								  TIMEDISPLAY_16mmFeetFrames			= 111;

								  TIMEDISPLAY_35mmFeetFrames			= 112;

								  TIMEDISPLAY_48Timecode				= 113;

								  TIMEDISPLAY_AudioSamplesTimecode	    = 200;

								  TIMEDISPLAY_AudioMsTimecode			= 201;
===================  ===========  =======================

#### Returns

A `String`.

----

.. _time.setSecondsAsFraction:

Time.setSecondsAsFraction()
*********************************************

``myTime.setSecondsAsFraction(numerator, denominator)``

#### Description

Sets the Time object to the result of dividing the numerator by the denominator.

#### Parameters

Both the numerator and the denominator are ``ints``.

#### Returns

Boolean; ``true`` if successful.
