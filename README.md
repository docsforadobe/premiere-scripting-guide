# Premiere Pro Scripting Guide

This repo hosts the Premiere Pro Scripting Guide RST docs, linked into a http://readthedocs.io system hosted at https://ppro-scripting.docsforadobe.dev/

Things to note:

- `./index.html` is the main Table of Contents, and the root of the site. I've left in entries from the JS Tools Guide for reference on structure.
- `./1 - Introduction/`
	- Again, left here just for reference. I've left links in
	- index.html in each subfolder will be the main page loaded for each 'chapter'

---

## Build HTML Locally

You may want to build the HTML locally before pushing, in order to ensure that the result is what you'd expect. These files aren't included in the git repo, nor are they used online; this is solely to create a local, offline version of the online docs.

- Install ``Python``
- Install ``pip``
- Navigate to the project directory and use the command ``pip install -r requirements.txt``
- Build the docs using ``make html``

---

## Contributing

This project uses reStructuredText for a reference on how to write reStructuredText check out this [quickref](http://docutils.sourceforge.net/docs/user/rst/quickref.html).

### How to

#### Text

```
**bold**, *italics*, ``code``
```

#### Headers

```
H1. line must be at least as long as text
=========================================

h2
--

h3
**

h4
++
```

#### Bullet lists

```
- Bullet point lists must start with one empty line above
  - Indented bullet points are indented with 2 spaces
  - very long bullet point that goes over multiple lines
    have the additional lines indented one more level
- Bullet point
```

#### Paragraphs

```

New paragraphs starts with an empty line above.
If there are no empty line above. The line will be added to the end of the previous line.

Correct way to start a new paragraph.

Header
======
Paragraphs can start directly underneath headers, an empty line is not needed in that case.
```

#### Links

##### Making an anchor:

At the start of a page or section, this format on its own line defines an anchor: `.. _cross-platform-file-system-access:`

##### Creating a link:

To refer to the above anchor, you can use either:

```
- :ref:`the-extendscript-toolkit` to have the docs pull the link text from the first title it finds after the anchor
- :ref:`The Mystical, Magical Extendscript Toolkit <the-extendscript-toolkit>` to use the supplied title
```

These will both search project-wide for the link. Any duplicates or malformed links will be reported upon build in your console window.

### Parameters

For consistency, please use the table below to defined function arguments and their types:

|   Argument    |   Type   |     Description     |
| ------------- | -------- | ------------------- |
| ``argument1`` | ``type`` | What it's all about |
| ``argument2`` | ``type`` | What it's all about |
| ``argument3`` | ``type`` | What it's all about |

