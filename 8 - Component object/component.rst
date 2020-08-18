.. highlight:: javascript

.. _component:

Component object
===================

``Component``

**Description**

The **component** object represents something which has been added or applied to a trackItem.

----

==========
Attributes
==========

.. _component.displayName:

Component.displayName
*********************************************

``component.displayName``

**Description**

The name of the component, as it is displayed to the user. Localized.

**Type**

String; read-only.

----

.. _component.matchName:

Component.matchName
*********************************************

``component.matchName``

**Description**

The name of the component, as it is loaded from disk; used to uniquely identify effect plug-ins.

**Type**

String; read-only.

----

.. _component.properties:

Component.properties
*********************************************

``component.properties``

**Description**

The properties of the component in question; typically, these are effect parameters.

**Type**

Array of components, read-only.
