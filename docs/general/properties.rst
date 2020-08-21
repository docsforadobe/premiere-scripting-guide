.. highlight:: javascript

.. _properties:

Properties object
===================

``app.properties``

**Description**

*add description here*

----

==========
Attributes
==========

None.

----

=======
Methods
=======

.. _properties.clearProperty:

Properties.clearProperty()
*********************************************

``app.properties.clearProperty()``

**Description**

*add description here*

**Parameters**

*add parameters here*

**Returns**

*add return value/type here*

----

.. _properties.doesPropertyExist:

Properties.doesPropertyExist()
*********************************************

``app.properties.doesPropertyExist(property)``

**Description**

Checks whether a given property exists in preferences.

**Parameters**

============  ==========  ===================
parameter     type        description
============  ==========  ===================
``property``  ``String``  A property to check
============  ==========  ===================

**Returns**

``Boolean``.

**Example**

Check whether labels with indices 10 and 99 exist in preferences:

.. code:: javascript

    var property = 'BE.Prefs.LabelNames.10';
    var exists = app.properties.doesPropertyExist(property);
    alert('Property "' + property + '" exists: ' + exists.toString());

    property = 'BE.Prefs.LabelNames.99';
    exists = app.properties.doesPropertyExist(property);
    alert('Property "' + property + '" exists: ' + exists.toString());

----

.. _properties.getProperty:

Properties.getProperty()
*********************************************

``app.properties.getProperty(property)``

**Description**

Returns a property value.

**Parameters**

============  ==========  =============================
parameter     type        description
============  ==========  =============================
``property``  ``String``  A property to get a value for
============  ==========  =============================

**Returns**

``String``.

**Example**

Get label name at a given index:

.. code:: javascript

    var labelIndex = 0;
    var property = 'BE.Prefs.LabelNames.' + labelIndex;

    if (app.properties.doesPropertyExist(property)) {
        alert(app.properties.getProperty(property));
    } else {
        alert('Property "' + property + '" does not exist');
    }

----

.. _properties.isPropertyReadOnly:

Properties.isPropertyReadOnly()
*********************************************

``app.properties.isPropertyReadOnly()``

**Description**

Checks whether a given property can be overwritten by the user. Returns `false` if such property does not exist.

**Parameters**

``property`` as a string.

**Returns**

``Boolean``.

----

.. _properties.setProperty:

Properties.setProperty()
*********************************************

``app.properties.setProperty(property, value, persistent, createIfNotExist)``

**Description**

Set property value.

**Parameters**

====================  ===========  ================================================
parameter             type         description
====================  ===========  ================================================
``property``          ``String``   A property to create
``value``             ``Any``      A value for a property
``persistent``        ``Boolean``  Whether if should be persistent between sessions
``createIfNotExist``  ``Boolean``  Should create, if such property does not exist
====================  ===========  ================================================

**Returns**

``null``.

**Example**

Change label name:

.. code:: javascript

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
