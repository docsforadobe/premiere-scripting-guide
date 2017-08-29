.. _App_object:

Overview
========

Premiere Pro provides an ExtendScript-based API, allowing for the access and manipulation of most project elements, including metadata, exporting and rendering options.

This document does not teach ExtendScript, ExtendScript Toolkit debugging, or other development techniques. It focuses on the Premiere Pro ExtendScript API and the execution context for scripts.

.. _example-code:

Example code
------------

The PProPanel example is available from the Adobe CEP GitHub repository: https://github.com/Adobe-CEP/Samples/tree/master/PProPanel.

The samples are located under the ExtendScript SDK root directory:

- ``SDKroot/Samples/javascript/``: sample scripts
- ``SDKroot/Samples//javascript/resources/``: resources, such as image or flash files


.. _development-and-debugging-tools:

Development and debugging tools
-------------------------------

The ExtendScript Toolkit (ESTK) remains the best (and only) ExtendScript debugger available.

  http://www.adobe.com/products/extendscript-toolkit.html

ESTK can be used to execute stand-alone scripts in Premiere Pro, and debug ExtendScript invoked from within CEP panels. 

