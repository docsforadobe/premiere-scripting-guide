.. highlight:: javascript

.. _anywhere:

Anywhere object
==========================

``app.anywhere``

**Description**

The **anywhere** object represents any Adobe Anywhere or Team Projects servers available.

----

==========
Attributes
==========

None.

----

=======
Methods
=======

.. _anywhere.getAuthenticationToken:

Anywhere.getAuthenticationToken()
*********************************************

``app.anywhere.getAuthenticationToken()``

**Description**

Retrieves an authentication token.

**Parameters**

None.

**Returns**

A **String** containing the login token, or **0** if unsuccessful.

----

.. _anywhere.getCurrentEditingSessionActiveSequenceURL:

Anywhere.getCurrentEditingSessionActiveSequenceURL()
******************************************************

``app.anywhere.getCurrentEditingSessionActiveSequenceURL()``

**Description**

Retrieves the URL of the currently active sequence, within a production.

**Parameters**

None.

**Returns**

Returns a **String** containing the asset's URL, or **0** if unsuccessful (including if there is no active sequence, or if no editing session is opened).

----

.. _anywhere.getCurrentEditingSessionSelectionURL:

Anywhere.getCurrentEditingSessionSelectionURL()
******************************************************

``app.anywhere.getCurrentEditingSessionSelectionURL()``

**Description**

Retrieves the URL of the currently selected single asset. Will fail if more or fewer than one item is selected.

**Parameters**

None.

**Returns**

Returns a **String** containing the asset's URL, or **0** if unsuccessful (including if more or fewre than one item is selected).

----

.. _anywhere.getCurrentEditingSessionURL:

Anywhere.getCurrentEditingSessionURL()
*********************************************

``app.anywhere.getCurrentEditingSessionURL()``

**Description**

Retrieves the URL of the Production, currently being edited.

**Parameters**

None.

**Returns**

Returns a **String** containing the production's URL, or **0** if unsuccessful.

----

.. _anywhere.isProductionOpen:

Anywhere.isProductionOpen()
*********************************************

``app.anywhere.isProductionOpen()``

**Description**

Retrieves whether an Anywhere or Team Projects production is currently open.

**Parameters**

None.

**Returns**

Returns ``true`` if a production is open; ``false`` if not.

----

.. _anywhere.listProductions:

Anywhere.listProductions()
*********************************************

``app.anywhere.listProductions()``

**Description**

Retrieves production names, available to the current user, on the current server. 

**Parameters**

**Returns**

Returns an Array of **Strings** containing the names of avialable productions, or 0 if unsuccessful.

----

.. _anywhere.openProduction:

Anywhere.openProduction()
*********************************************

``app.anywhere.openProduction(productionURL)``

**Description**

Opens the production at the specified URL.

**Parameters**

A **String** containing the url of the production to open. 

**Returns**

Returns **0** if successful.

----

.. _anywhere.setAuthenticationToken:

Anywhere.setAuthenticationToken()
*********************************************

``app.anywhere.setAuthenticationToken(token, emailAddress)``

**Description**

Logs the specified email address into the server, using the provided token.

**Parameters**

Takes an authorization ``token``, and the associated email address.

**Returns**

Returns **0** if successful.
