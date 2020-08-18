.. highlight:: javascript

.. _anywhere:

Anywhere object
==========================

``anywhere``

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

getAuthenticationToken
*********************************************

``anywhere.getAuthenticationToken()``

**Description**

Retrieves an authentication token.

**Parameters**

None.

**Returns**

A **String** containing the login token, or **0** if unsuccessful.

----

.. _anywhere.getCurrentEditingSessionActiveSequenceURL:

getCurrentEditingSessionActiveSequenceURL
*********************************************

``anywhere.getCurrentEditingSessionActiveSequenceURL()``

**Description**

Retrieves the URL of the currently active sequence, within a production.

**Parameters**

None.

**Returns**

Returns a **String** containing the asset's URL, or **0** if unsuccessful (including if there is no active sequence, or if no editing session is opened).

----

.. _anywhere.getCurrentEditingSessionSelectionURL:

getCurrentEditingSessionSelectionURL
*********************************************

``anywhere.getCurrentEditingSessionSelectionURL()``

**Description**

Retrieves the URL of the currently selected single asset. Will fail if more or fewer than one item is selected.

**Parameters**

None.

**Returns**

Returns a **String** containing the asset's URL, or **0** if unsuccessful (including if more or fewre than one item is selected).

----

.. _anywhere.getCurrentEditingSessionURL:

getCurrentEditingSessionURL
*********************************************

``anywhere.getCurrentEditingSessionURL()``

**Description**

Retrieves the URL of the Production, currently being edited.

**Parameters**

None.

**Returns**

Returns a **String** containing the production's URL, or **0** if unsuccessful.

----

.. _anywhere.isProductionOpen:

isProductionOpen
*********************************************

``anywhere.isProductionOpen()``

**Description**

Retrieves whether an Anywhere or Team Projects production is currently open.

**Parameters**

None.

**Returns**

Returns ``true`` if a production is open; ``false`` if not.

----

.. _anywhere.listProductions:

listProductions
*********************************************

``anywhere.listProductions()``

**Description**

Retrieves production names, available to the current user, on the current server. 

**Parameters**

**Returns**

Returns an Array of **Strings** containing the names of avialable productions, or 0 if unsuccessful.

----

.. _anywhere.openProduction:

openProduction
*********************************************

``anywhere.openProduction(productionURL)``

**Description**

Opens the production at the specified URL.

**Parameters**

A **String** containing the url of the production to open. 

**Returns**

Returns **0** if successful.

----

.. _anywhere.setAuthenticationToken:

setAuthenticationToken
*********************************************

``anywhere.setAuthenticationToken(token, emailAddress)``

**Description**

Logs the specified email address into the server, using the provided token.

**Parameters**

Takes an authorization ``token``, and the associated email address.

**Returns**

Returns **0** if successful.
