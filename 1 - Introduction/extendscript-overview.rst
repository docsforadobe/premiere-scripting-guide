.. _extendscript-overview:

ExtendScript overview
=====================

Adobe provides an extended implementation of JavaScript, called ExtendScript, that is used by many
Adobe applications that provide a scripting interface. In addition to implementing the JavaScript
language according to the ECMA JavaScript specification, ExtendScript provides certain additional
features and utilities.

This document describes JavaScript modules, tools, utilities, and features that are available to all
JavaScript-enabled Adobe applications.

.. note:: Some modules, and features of some modules, are optional. Check the product documentation for each application for details of which modules and features are implemented.


.. _example-code:

Example code
------------
The Adobe ExtendScript SDK, which contains this document, also contains a set of code samples that
demonstrate how to use features of ScriptUI, interapplication communication, and external
communication. This book refers to these samples by name for illustration of concepts and techniques.

You can download the SDK from Adobe Developer Center, http://www.adobe.com/devnet/scripting/.

The samples are located under the ExtendScript SDK root directory:

- ``SDKroot/Samples/javascript/``: sample scripts
- ``SDKroot/Samples//javascript/resources/``: resources, such as image or flash files


.. _development-and-debugging-tools:

Development and debugging tools
-------------------------------
For help in developing, debugging, and testing scripts, Adobe provides the ExtendScript Toolkit, an
interactive development and testing environment for ExtendScript, which is installed with all
JavaScript-enabled applications. For complete details, see Chapter 2, :ref:`the-extendscript-toolkit`.

ExtendScript also provides global objects that support development and debugging:

- A global debugging object, the Dollar ($) object.
- A reporting utility for ExtendScript elements, the ExtendScript reflection interface.

For complete details, see Chapter 8, :ref:`extendscript-tools-and-features`.


.. _cross-platform-file-system-access:

Cross-platform file-system access
---------------------------------
Adobe ExtendScript defines File and Folder classes that simplify cross-platform file-system access. These
classes are available to all applications that support a JavaScript interface.

For complete details, see Chapter 3, :ref:`file-system-access`.


.. _user-interface-development-tools:

User-interface development tools
--------------------------------
Adobe provides the ScriptUI module, which works with the ExtendScript JavaScript interpreter to provide
JavaScript scripts with the ability to create and interact with user interface elements. It provides an object
model for windows and user-interface control elements within an Adobe application. For complete details,
see Chapter 4, :ref:`user-interface-tools`.
In addition, ExtendScript provides:

- Global functions for localization of display strings; see :ref:`localizing-extendscript-strings`
- Global functions for displaying short messages in dialog boxes; see :ref:`user-notification-dialogs`.
- An object type for specifying measurement values together with their units; see :ref:`specifying-measurement-values`.


.. _interapplication-communication-and-messaging:

Interapplication communication and messaging
--------------------------------------------
ExtendScript provides a common scripting environment for all Adobe JavaScript-enabled applications,
and allows interapplication communication through scripts.
Different levels of communication are provided through the cross-DOM and the messaging framework.

- Cross-DOM functions are a limited set of basic functions common across all message-enabled applications, which allow your script to, for example, open or print files in other applications, simply by calling the open or print function for that application. In addition to the basic set of common functions, some applications provide more extensive sets of exported JavaScript functions to other applications.
- The interapplication messaging framework is an application programming interface (API) that allows
  extensive control over communication between applications. The API allows you to send messages to
  other applications and receive results, and to receive messages sent by other applications and return
  results. Typically the data passed between applications are JavaScript scripts. However, the messaging
  framework is extensible. It allows you to define different types of data to send between applications,
  and to specify how they are handled.

For complete details, see Chapter 5, :ref:`interapplication-communication-with-scripts`.


.. _external-communication:

External communication
----------------------
ExtendScript offers tools for communicating with other computers or the internet using standard
protocols. The Socket object supports low-level TCP connections.

For complete details, see Chapter 6, :ref:`external-communication-tools`.


.. _external-shared-library-integration:

External shared-library integration
-----------------------------------
You can extend the JavaScript DOM for an application by writing a C or C++ shared library, compiling it for
the platform you are using, and loading it into JavaScript as an ExternalObject instance. A shared library
is implemented by a DLL in Windows, a bundle or framework in Mac OS, or a SharedObject in UNIX.

For complete details, see Chapter 7, :ref:`integrating-external-libraries`.


.. _additional-utilities-and-features:

Additional utilities and features
---------------------------------
ExtendScript provides these utilities and features:

- JavaScript language enhancements:
    - Tools for combining scripts, such as a ``#include`` directive. See :ref:`preprocessor-directives`.
    - Support for extending or overriding math and logical operator behavior on a class-by-class basis.
      See :ref:`operator-overloading`.

    For complete details, see Chapter 8, :ref:`extendscript-tools-and-features`.
- JavaScript compilation, through the ExtendScript Toolkit. See Chapter 2, :ref:`the-extendscript-toolkit`.
- XML integration: ExtendScript defines the XML object, which allows you to process XML with your
- JavaScript scripts. For complete details, see Chapter 9, :ref:`integrating-xml-into-javascript`.
- Scripting support for XMP metadata manipulation: XMPScript provides a JavaScript API for the Adobe
