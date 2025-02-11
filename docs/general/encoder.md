# Encoder object

`app.encoder`

#### Description

The `encoder` object represents Adobe Media Encoder, and is used for local rendering, outside of Premiere Pro.

!!! warning
    `app.encoder` is broken on Premiere Pro 14.3.1 - 15 on Mac only. Fixed in 22 and up. [See here.](https://community.adobe.com/t5/premiere-pro-discussions/missing-the-object-app-encoder-14-3-1-15-0-15-1-15-2/m-p/12544488)

---

## Attributes

None.

---

## Methods

### Encoder.encodeFile()

`app.encoder.encodeFile(filePath, outputPath, presetPath, workArea, removeUponCompletion, inPoint, outPoint)`

#### Description

Makes Adobe Media Encoder render (optionally, a specified range from) the specified file, with the specified settings.

#### Parameters

+------------------------+---------------------------------+-----------------------------------------------+
|       Parameter        |              Type               |                  Description                  |
+========================+=================================+===============================================+
| `filePath`             | String                          | A path to a file to render.                   |
+------------------------+---------------------------------+-----------------------------------------------+
| `outputPath`           | String                          | A path to an output file.                     |
+------------------------+---------------------------------+-----------------------------------------------+
| `presetPath`           | String                          | A path to a preset (.epr) file.               |
+------------------------+---------------------------------+-----------------------------------------------+
| `workArea`             | Integer                         | Integer denoting work area to be used:        |
|                        |                                 |                                               |
|                        |                                 | - `0` - `ENCODE_ENTIRE`                       |
|                        |                                 | - `1` - `ENCODE_IN_TO_OUT`                    |
|                        |                                 | - `2` - `ENCODE_WORK_AREA`                    |
+------------------------+---------------------------------+-----------------------------------------------+
| `removeUponCompletion` | Integer                         | If `1`, job will be removed once complete.    |
+------------------------+---------------------------------+-----------------------------------------------+
| `inPoint`              | [Time object](../other/time.md) | A Time object, for the in point of new file.  |
+------------------------+---------------------------------+-----------------------------------------------+
| `outPoint`             | [Time object](../other/time.md) | A Time object, for the out point of new file. |
+------------------------+---------------------------------+-----------------------------------------------+

#### Returns

Returns a job ID as a String, for the render job added to the AME queue, or `0` if unsuccessful.

---

### Encoder.encodeProjectItem()

`app.encoder.encodeProjectItem(projectItem, outputPath, presetPath, workArea, removeUponCompletion)`

#### Description

Makes Adobe Media Encoder render (optionally, a specified range from) the specified [ProjectItem object](../item/projectitem.md), with the specified settings.

#### Parameters

+------------------------+----------------------------------------------+--------------------------------------------+
|       Parameter        |                     Type                     |                Description                 |
+========================+==============================================+============================================+
| `projectItem`          | [ProjectItem object](../item/projectitem.md) | A project item to render.                  |
+------------------------+----------------------------------------------+--------------------------------------------+
| `outputPath`           | String                                       | A path to an output file.                  |
+------------------------+----------------------------------------------+--------------------------------------------+
| `presetPath`           | String                                       | A path to a preset (.epr) file.            |
+------------------------+----------------------------------------------+--------------------------------------------+
| `workArea`             | Integer                                      | Integer denoting work area to be used:     |
|                        |                                              |                                            |
|                        |                                              | - `0` - `ENCODE_ENTIRE`                    |
|                        |                                              | - `1` - `ENCODE_IN_TO_OUT`                 |
|                        |                                              | - `2` - `ENCODE_WORK_AREA`                 |
+------------------------+----------------------------------------------+--------------------------------------------+
| `removeUponCompletion` | Integer                                      | If `1`, job will be removed once complete. |
+------------------------+----------------------------------------------+--------------------------------------------+

#### Returns

Returns a job ID as a String, for the render job added to the AME queue, or `0` if unsuccessful.

---

### Encoder.encodeSequence()

`app.encoder.encodeSequence(sequence, outputPath, presetPath, workArea, removeUponCompletion)`

#### Description

Makes Adobe Media Encoder render the specified [Sequence object](../sequence/sequence.md), with the specified settings.

#### Parameters

+------------------------+--------------------------------------------+--------------------------------------------+
|       Parameter        |                    Type                    |                Description                 |
+========================+============================================+============================================+
| `sequence`             | [Sequence object](../sequence/sequence.md) | A sequence to render.                      |
+------------------------+--------------------------------------------+--------------------------------------------+
| `outputPath`           | String                                     | A path to an output file.                  |
+------------------------+--------------------------------------------+--------------------------------------------+
| `presetPath`           | String                                     | A path to a preset (.epr) file.            |
+------------------------+--------------------------------------------+--------------------------------------------+
| `workArea`             | Integer                                    | Integer denoting work area to be used:     |
|                        |                                            |                                            |
|                        |                                            | - `0` - `ENCODE_ENTIRE`                    |
|                        |                                            | - `1` - `ENCODE_IN_TO_OUT`                 |
|                        |                                            | - `2` - `ENCODE_WORK_AREA`                 |
+------------------------+--------------------------------------------+--------------------------------------------+
| `removeUponCompletion` | Integer                                    | If `1`, job will be removed once complete. |
+------------------------+--------------------------------------------+--------------------------------------------+

#### Returns

Returns a job ID as a String, for the render job added to the AME queue, or `0` if unsuccessful.

---

### Encoder.launchEncoder()

`app.encoder.launchEncoder()`

#### Description

Launches Adobe Media Encoder.

#### Parameters

None.

#### Returns

Returns `0` if successful.

---

### Encoder.setEmbeddedXMPEnabled()

`app.encoder.setEmbeddedXMPEnabled(enabled)`

#### Description

Determines whether embedded XMP metadata, will be output.

#### Parameters

| Parameter |  Type   |                    Description                     |
| --------- | ------- | -------------------------------------------------- |
| `enabled` | Integer | Pass `1` to enable sidecar output, `0` to disable. |

#### Returns

Returns `0` if successful.

!!! note
    Premiere Pro and Adobe Media Encoder will output sidecar XMP for some file formats, and embed XMP for most.

    The applications make this determination based on numerous factors, and there is no API control to "force" sidecar or embedded output, for formats which normally use "the other approach".

---

### Encoder.setSidecarXMPEnabled()

`app.encoder.setSidecarXMPEnabled(enabled)`

#### Description

Determines whether a sidecar file containing XMP metadata, will be output.

#### Parameters

| Parameter |  Type   |                    Description                     |
| --------- | ------- | -------------------------------------------------- |
| `enabled` | Integer | Pass `1` to enable sidecar output, `0` to disable. |

#### Returns

Returns `0` if successful.

---

### Encoder.startBatch()

`app.encoder.startBatch()`

#### Description

Makes Adobe Media Encoder start rendering its render queue.

#### Parameters

None.

#### Returns

Returns `0` if successful.
