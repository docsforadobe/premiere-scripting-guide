.. _App_object:

Overview
========

Premiere Pro provides an ExtendScript API, allowing for the access and manipulation of most project elements, including metadata, exporting and rendering options.

.. note:: This document does not teach ExtendScript, ExtendScript Toolkit debugging, or other development techniques. It focuses on the Premiere Pro ExtendScript API and the execution context for scripts.

While initially incomplete and intended only for internal testing, the Premiere Pro ExtendScript API has been growing steadily for many years. As of 12.0.1 (the current release, as of this writing), the API offers thorough access to (and, often, control over) all project elements, as well as application settings.

.. _example-code:

Example code
------------

The PProPanel sample exercises Premiere Pro's ExtendScript API: https://github.com/Adobe-CEP/Samples/tree/master/PProPanel.


.. _development-and-debugging-tools:

Development and debugging tools
-------------------------------

The ExtendScript Toolkit (ESTK) remains the best (and only) ExtendScript debugger available.

  http://www.adobe.com/products/extendscript-toolkit.html

ESTK can be used to execute stand-alone scripts in Premiere Pro, and debug ExtendScript invoked from within CEP panels. Commonly, developers test individual functions in ESTK, then debug them 'in context' running from within a CEP panel.

