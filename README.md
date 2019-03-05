# README #

This is a repo for the Premiere Scripting Guide. Things to note:

- `./index.html` is the main Table of Contents, and the root of the site. I've left in entries from the JS Tools Guide for reference on structure.
- `./1 - Introduction/`
	- Again, left here just for reference. I've left links in
	- index.html in each subfolder will be the main page loaded for each 'chapter'

### Building Locally ###

- Run `make html` in the project directory
- The project will be built in a subfolder at `_build/html` where you can open index.html in a browser as expected
- Any issues / warnings will be displayed in the console


### Contributing ###

This project uses reStructuredText for a reference on how to write reStructuredText check out this [quickref](http://docutils.sourceforge.net/docs/user/rst/quickref.html).


### How to ###


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