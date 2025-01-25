# Properties object

`app.properties`

**Description**

*add description here*

---

## Attributes

None.

---

## Methods

### Properties.clearProperty()

`app.properties.clearProperty()`

**Description**

*add description here*

**Parameters**

*add parameters here*

**Returns**

*add return value/type here*

---

### Properties.doesPropertyExist()

`app.properties.doesPropertyExist(property)`

**Description**

Checks whether a given property exists in preferences.

**Parameters**

| Argument   | Type     | Description         |
|------------|----------|---------------------|
| `property` | `String` | A property to check |

**Returns**

`Boolean`.

**Example**

Check whether labels with indices 10 and 99 exist in preferences:

```javascript
var property = 'BE.Prefs.LabelNames.10';
var exists = app.properties.doesPropertyExist(property);
alert('Property "' + property + '" exists: ' + exists.toString());

property = 'BE.Prefs.LabelNames.99';
exists = app.properties.doesPropertyExist(property);
alert('Property "' + property + '" exists: ' + exists.toString());
```

---

### Properties.getProperty()

`app.properties.getProperty(property)`

**Description**

Returns a property value.

**Parameters**

| Argument   | Type     | Description                   |
|------------|----------|-------------------------------|
| `property` | `String` | A property to get a value for |

**Returns**

`String`.

**Example**

Get label name at a given index:

```javascript
var labelIndex = 0;
var property = 'BE.Prefs.LabelNames.' + labelIndex;

if (app.properties.doesPropertyExist(property)) {
    alert(app.properties.getProperty(property));
} else {
    alert('Property "' + property + '" does not exist');
}
```

---

### Properties.isPropertyReadOnly()

`app.properties.isPropertyReadOnly(property)`

**Description**

Checks whether a given property can be overwritten by the user. Returns false if such property does not exist.

**Parameters**

| Argument   | Type     | Description          |
|------------|----------|----------------------|
| `property` | `String` | A property to check. |

**Returns**

`Boolean`.

---

### Properties.setProperty()

`app.properties.setProperty(property, value, persistent, createIfNotExist)`

**Description**

Set property value. NOTE: For any file paths to be used in Premiere Pro’s preferences, a trailing path seperator is mandatory.

**Parameters**

| Argument           | Type      | Description                                      |
|--------------------|-----------|--------------------------------------------------|
| `property`         | `String`  | A property to create                             |
| `value`            | `Any`     | A value for a property                           |
| `persistent`       | `Boolean` | Whether if should be persistent between sessions |
| `createIfNotExist` | `Boolean` | Should create, if such property does not exist   |

**Returns**

`null`.

**Example**

Change label name:

```javascript
var labelIndex = 0;
var property = 'BE.Prefs.LabelNamesX.' + labelIndex;

var newValue = 'Changed via Script';
var persistent = true;
var createIfNotExist = true;

if (app.properties.doesPropertyExist(property)) {
    if (app.properties.isPropertyReadOnly(property)) {
        alert('Could not rename property "' + property + '" because it is read-only.');
    } else {
        var oldValue = app.properties.getProperty(property);
        app.properties.setProperty(property, newValue, persistent, createIfNotExist);
        alert('Value changed from "' + oldValue + '" to "' + newValue + '"');
    }
} else {
    app.properties.setProperty(property, newValue, persistent, createIfNotExist);
    alert('Created new property "' + property + '" with value "' + newValue + '"');
}
```
