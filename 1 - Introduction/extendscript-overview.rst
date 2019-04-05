.. _App_object:

Overview
========

Premiere Pro provides an ExtendScript API, allowing for the access and manipulation of most project elements, including metadata, exporting and rendering options.

.. note:: This document does not teach ExtendScript, ExtendScript Toolkit debugging, or other development techniques. It focuses on the Premiere Pro ExtendScript API and the execution context for scripts.

While initially incomplete and intended only for internal testing, the Premiere Pro ExtendScript API has been growing steadily for many years. As of 12.1.1 (the current release, as of this writing), the API offers thorough access to (and, often, control over) all project elements, as well as application settings.

.. _example-code:

Example code
------------

The PProPanel sample exercises Premiere Pro's ExtendScript API: https://github.com/Adobe-CEP/Samples/tree/master/PProPanel.


.. _development-and-debugging-tools:

Development and debugging tools
-------------------------------

ExtendScript Toolkit (ESTK) will no longer be updated by Adobe; the recommended debugging environment for ExtendScript is to use Microsoft Visual Studio Code, and Adobe's ExtendScript debugging extension:

https://marketplace.visualstudio.com/items?itemName=Adobe.extendscript-debug

Both ESTK and VSCode with our extension can be used to execute stand-alone scripts in Premiere Pro, and debug ExtendScript invoked from within CEP panels.

