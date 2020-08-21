.. highlight:: javascript

.. AudioChannelMapping:

AudioChannelMapping
===================

``app.project.rootItem.children[index].getAudioChannelMapping()``

**Description**

The AudioChannelMapping object defines the audio channel mapping applied to a given :ref:`projectItem`.

----

==========
Attributes
==========

.. _audioChannelMapping.audioChannelsType:

AudioChannelMapping.audioChannelsType
*********************************************

``app.project.rootItem.children[index].getAudioChannelMapping().audioChannelsType``

**Description**

The type of the audio contained in this channel. Will be 0, 1 or 2, corresponding to ``AUDIOCHANNELTYPE_Mono``, ``AUDIOCHANNELTYPE_Stereo``, or ``AUDIOCHANNELTYPE_51``.

----

.. _audioChannelMapping.audioClipsNumber:

AudioChannelMapping.audioClipsNumber
*********************************************

``app.project.rootItem.children[index].getAudioChannelMapping().audioClipsNumber``

**Description**

The number of audio clips associated with this audio channel.

----

=======
Methods
=======

.. _audioChannelMapping.setMappingForChannel:

AudioChannelMapping.setMappingForChannel()
*********************************************

``app.project.rootItem.children[index].setMappingForChannel(intChannelIndex, intSourceChannelIndex)``

**Description**

Maps a source channel to the specified channel index. 

**Parameters**

Index of channel to be mapped, index of source channel to map.

**Returns**

Returns **true** if successful, **false** if that mapping is unsupported.
