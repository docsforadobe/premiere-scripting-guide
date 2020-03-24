.. highlight:: javascript

.. AudioChannelMapping:

AudioChannelMapping
===================

``AudioChannelMapping``

**Description**

The AudioChannelMapping object defines the audio channel mapping applied to a given **projectItem**.

==========
Attributes
==========

.. AudioChannelMapping.audioClipsNumber:

audioClipsNumber
*********************************************

``AudioChannelMapping.audioClipsNumber``

**Description**

The number of audio clips associated with this audio channel.

.. _AudioChannelMapping.audioChannelsType:

audioChannelsType
*********************************************

``AudioChannelMapping.audioChannelsType``

**Description**

The type of the audio contained in this channel. Will be either ``AUDIOCHANNELTYPE_Mono``, ``AUDIOCHANNELTYPE_Stereo``, or ``AUDIOCHANNELTYPE_51``.

=======
Methods
=======

.. _AudioChannelMapping.setMappingForChannel:

setMappingForChannel
*********************************************

``mapping.setMappingForChannel(intChannelIndex, intSourceChannelIndex)``

**Description**

Maps a source channel to the specified channel index. 

**Parameters**

Index of channel to be mapped, index of source channel to map.

**Returns**

Returns **true** if successful, **false** if that mapping is unsupported.
