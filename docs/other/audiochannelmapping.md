<a id="audiochannelmapping"></a>

# AudioChannelMapping object

`app.project.rootItem.children[index].getAudioChannelMapping`

**Description**

The AudioChannelMapping object defines the audio channel mapping applied to a given [ProjectItem object](../item/projectitem.md#projectitem).

---

## Attributes

<a id="audiochannelmapping-audiochannelstype"></a>

### AudioChannelMapping.audioChannelsType

`app.project.rootItem.children[index].getAudioChannelMapping.audioChannelsType`

**Description**

The type of the audio contained in this channel. Will be 0, 1 or 2, corresponding to `AUDIOCHANNELTYPE_Mono`, `AUDIOCHANNELTYPE_Stereo`, or `AUDIOCHANNELTYPE_51`.

---

<a id="audiochannelmapping-audioclipsnumber"></a>

### AudioChannelMapping.audioClipsNumber

`app.project.rootItem.children[index].getAudioChannelMapping.audioClipsNumber`

**Description**

The number of audio clips associated with this audio channel.

---

## Methods

<a id="audiochannelmapping-setmappingforchannel"></a>

### AudioChannelMapping.setMappingForChannel()

`app.project.rootItem.children[index].setMappingForChannel(channelIndex, sourceChannelIndex)`

**Description**

Maps a source channel to the specified channel index.

**Parameters**

| Argument             | Type      | Description                           |
|----------------------|-----------|---------------------------------------|
| `channelIndex`       | `Integer` | The index of a channel to be mapped.  |
| `sourceChannelIndex` | `Integer` | The index of a source channel to map. |

**Returns**

Returns **true** if successful, **false** if that mapping is unsupported.
