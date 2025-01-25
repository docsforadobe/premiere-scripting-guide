<a id="app-object"></a>

# Overview

Premiere Pro provides an ExtendScript API, allowing for the access and manipulation of most project elements, including metadata, exporting and rendering options.

#### NOTE
This document does not teach ExtendScript, ExtendScript debugging, or other development techniques. It focuses on the Premiere Pro ExtendScript API and the execution context for scripts.

While initially incomplete and intended only for internal testing, the Premiere Pro ExtendScript API has been growing steadily for many years. As of 12.1.1 (the current release, as of this writing), the API offers thorough access to (and, often, control over) all project elements, as well as application settings.

<a id="example-code"></a>

## Example code

The PProPanel sample exercises Premiere Pro’s ExtendScript API: [https://github.com/Adobe-CEP/Samples/tree/master/PProPanel](https://github.com/Adobe-CEP/Samples/tree/master/PProPanel).

<a id="development-and-debugging-tools"></a>

## Development and debugging tools

ExtendScript Toolkit (ESTK) is longer updated by Adobe; the recommended debugging environment for ExtendScript is  Microsoft Visual Studio Code, with Adobe’s ExtendScript debugging extension:

[https://marketplace.visualstudio.com/items?itemName=Adobe.extendscript-debug](https://marketplace.visualstudio.com/items?itemName=Adobe.extendscript-debug)
