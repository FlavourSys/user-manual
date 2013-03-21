.. FlavourSys Strawberry documentation convention,
   created by Mick on Fri 01.03.2013 15:42
.. _documentation_conventions:

##################################
Internal Documentation Conventions
##################################

.. topic:: Overview

	This document describes the standard conventions used in the Strawberry manual.  The manual is written in reStructuredText, which can be easily converted to a lot of different formats (static html, xml, epub, pdf, tex, etc.).

	The reStructuredText (RST) syntax provides an easy-to-read, what-you-see-is-what-you-get plain-text markup syntax and parser system.

		* RST syntax is sensitive to indentation!
		* RST requires blank lines between paragraphs

	This entire document is written with the RST syntax.  In the right sidebar, there is a link **show source**, which shows the RST source code of this page.

	:Date: |today|
	:Author: Mick Hohmann

.. contents::
	:depth: 3


*******
Headers
*******

The following header conventions are used in the Strawberry documentation:

.. code-block:: rest

	####
	Part
	####

	*******
	Chapter
	*******

	Section
	=======

	Subsection
	----------

	Subsubsection
	^^^^^^^^^^^^^

	Paragraph
	"""""""""



***************
Text Formatting
***************

There are a few special characters used to format text.  The special character "``*``" is used to define bold and italic text as shown in the table below.  The backquote character "`````" is another special character and used to either define verbatim text, or to create links to external web pages.

=========== ============================================= ===================================
Usage       Syntax                                        HTML rendering
=========== ============================================= ===================================
italic      `*italic*`                                    *italic*
bold        `**bold**`                                    **bold**
Filenames   ````verbatim````                              ``verbatim``
Links/URLs  ```FlavourSys <http://www.flavoursys.com>`_``  `FlavourSys <http://www.flavoursys.com>`_
=========== ============================================= ===================================


Indented blocks
===============

.. code-block:: rest

		This is an indented block of text, used for quoted text or to emphasize a complete paragraph.

creates this:

	This is an indented block of text, used for quoted text or to emphasize a complete paragraph.

[tbc.]


****************
List and Bullets
****************

The following code:

.. code-block:: rest

	* This is a bullet list.
	* It has two items, the second
	  item uses two lines. (note the indentation)

	1. This is a numbered list.
	2. It has two items too.

	#. This is a numbered list.
	#. It has two items too.

	Definitionlist : Classification
		This is the first entry in the definition list

		This is another entry in the definition list


results in:

* This is a bullet list.
* It has two items, the second
  item uses two lines. (note the indentation)

1. This is a numbered list.
2. It has two items too.

#. This is a numbered list.
#. It has two items too.

Definitionlist: term 1
	Definition 1.

Definitionlist: term 2
	Definition 2, paragraph 1.

	Definition 2, paragraph 2.


.. note:: if two lists are separated by a blank line only, then the two lists are not differentiated as you can see above.


******
Tables
******

There are several ways to write tables.  The rendering of the table depends on the CSS/HTML style, not on Sphinx itself.  For the Strawberry Manual we use the folling way:

Multicells Table
================

This is the simplified syntax:

.. code-block:: rest

	=====  =====  ======
	   Inputs     Output
	------------  ------
	  A      B    A or B
	=====  =====  ======
	False  False  False
	True   False  True
	=====  =====  ======

results in:

=====  =====  ======
   Inputs     Output
------------  ------
  A      B    A or B
=====  =====  ======
False  False  False
True   False  True
=====  =====  ======


******************
Images and Figures
******************

In order to include images into the Strawberry Manual, the file(s) needs to be copied to the **images** directory in the Strawberry Manual main folder.  And next use either of the following options:

Include Images
==============

Use the following block:

.. code-block:: rest

	.. image:: images/flavoursys_logo_S.png
		:width: 800px
		:align: center
		:alt: FlavourSys Logo

to auto-scale the logo to 800px width and the place the FlavourSys logo centered on the page:

.. image:: images/flavoursys_logo_S.png
	:width: 800px
	:align: center
	:alt: FlavourSys Logo


Include a Figure
=================

The following block:

.. code-block:: rest

	.. figure:: images/flavoursys_logo_S.png
		:width: 600px
		:height: 200px
		:align: center
		:alt: FlavourSys Logo
		:figclass: align-center

		Figure(s) are like images but with a caption (like this one).

creates this output (with an distorted scaled FlavourSys logo):

.. figure:: images/flavoursys_logo_S.png
	:width: 600px
	:height: 200px
	:align: center
	:alt: FlavourSys Logo
	:figclass: align-center

	Figure(s) are like images but with a caption (like this one).


The option **figclass** is a CSS class that can be tuned for the final HTML rendering.


***************************
Internal and External Links
***************************

With Sphinx/RST, there are 3 type of links:
	#. `External Links`_ (http-like)
	#. `Implicit Links`_ to Title
	#. `Explicit Links`_ to user-defined label (e.g., to refer to external titles).

External Links
==============

To create a link to an external website, the syntax is:

.. code-block:: rest

	`FlavourSys <http://www.flavoursys.com/>`_

which appears as `FlavourSys <http://www.flavoursys.com/>`_ .  Please note the underscore after the final single quote.  Since the full name of the link is not always simple or meaningful, please specify a label--as seen above (note the space between the label and link name).

.. note:: In order to use an underscore within the label/name, it needs to be escaped it with a "\\" (backslash) character.


.. _implicit links:

Implicit Links to Titles
========================

All titles are considered as hyperlinks.  A link to a title is just its name within quotes and a final underscore:

.. code-block:: rest

	`Internal and External Links`_

This syntax works only if the title and link are within the same RST file.  In order to link to labels/sections in other documentation files, please create a label before the title and refer to this new link explicitly, as explained in `Explicit Links`_ section.


Explicit Links
==============

To create links in an RST file, which are accessible/referable from other files, create an explicit label.  For instance, this document has a label at the top called ``documentation_conventions``, which is specified by typing:

.. code-block:: rest

	.. _documentation_conventions:

You can refer to this label using two different methods:

.. code-block:: rest
	:linenos:

	documentation_conventions_
	:ref:`documentation_conventions`

With the first method, the link appears as documentation_conventions_, whereas the second method use the first header name found after the link.  Therefore the second method will appear as :ref:`documentation_conventions`.

Note that the second method is compulsory if the link is located in an other RST file.  For instance, the index page is an external page (another file) with a label called ``index`` at the top of the page.  To jump there write ``:ref:`index```, which appears as: :ref:`index`.

.. note:: Note that if you use the ``ref`` role, the final underscore is not required anymore.


*********************************
Literal Blocks and Inserting Code
*********************************

There are two ways to include code snipplets or shell output into the documentation.  Either use the **code-block** directive and insert the code directly into the RST file, or use the **literalinclude** directive and let Sphinx include an external file automatically.

Code-Block Directive
====================

This directive requires to specify the language using the **code-block** directive as follows:

.. code-block:: rest

	.. code-block:: bash
		:linenos:

		$ cd /root
		$ ls -lhAF .*

produces

.. code-block:: bash
	:linenos:

	$ cd /root
	$ ls -lhAF .*

In the Strawberry manual, the following languages are used:

#. **bash**: either for bash shell scripts or for inputs in the console
#. **console**: used for console output only
#. **[tbc.]**


Include Code with the literalinclude Directive
==============================================

The **literalinclude** directive loads a file and pastes the contents of the files into the output (the content can be limited to specific lines, using options):

.. code-block:: rest

	.. literalinclude:: filename.ext
		:linenos:
		:language: bash
		:lines: 1, 3-5
		:start-after: 3
		:end-before: 5

For instance, the **sample.sh** file contents can be included directly:

.. literalinclude:: scripts/sample.sh
	:linenos:
	:language: bash


*****
Boxes
*****

Colored boxes: note, seealso and warnings
=========================================

There are simple directives like **seealso** that creates nice colored boxes:

.. code-block:: rest

	.. seealso:: This is a simple *seealso* note.

creates the folowing:

.. seealso:: This is a simple *seealso* note.


There is also the **note** directive:

.. code-block:: rest

	.. note::  This is a *note* box.

which creates:

.. note::  This is a *note* box.


And the warning directive:

.. code-block:: rest

	.. warning:: note the space between the directive and the text

generates:

.. warning:: note the space between the directive and the text


Topic directive
===============

The **Topic** directive allows to write a title and a text together within a box similarly to the **note** directive.  The follwing code:

.. code-block:: rest

	.. topic:: The Topic Title

		Subsequent indented lines comprise
		the body of the topic, and are
		interpreted as body elements.

provides the following output:

.. topic:: Your Topic Title

	Subsequent indented lines comprise
	the body of the topic, and are
	interpreted as body elements.


**************************************************************************
Usefull Links to Documentation about the reStructured Text & Sphinx Syntax
**************************************************************************

#. `Restructured Text (reST) and Sphinx CheatSheet <http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html>`_ - a good cheatsheet for RST

#. `reStructuredText Primer <http://sphinx-doc.org/rest.html>`_ - the official documentation of the reStructured Text directives used and available in Sphinx

#. `Pygments Lexers <http://pygments.org/docs/lexers/>`_ - the official list of all supported lexers used by Pygments
