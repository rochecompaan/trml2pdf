Name
----

trml2pdf - convert a Report Markup Langage (RML) file to a PDF


Synopsis
--------

	trml2pdf --help
	trml2pdf <input.rml >ouput.pdf

Description
-----------

Tiny RML2PDF is a tool to easily create PDF document without programming. It
can be used as a Python library or as a standalone binary. It converts a RML,
an XML dialect that lets you define the precise appearance of a printed
document, to a PDF. You can use your existing tools to generate an input file
that exactly describes the layout of a printed document, and RML2PDF converts
it into PDF. RML is a much more powerfull and flexible alternative to XSL:FO.

The executable read a RML file to the standard input and output a PDF file to
the standard output.


Command-line options
--------------------

	--help: command line options

Examples
--------

Create a PDF file:

	trml2pdf <input.rml

or:

        trml2pdf utf-8 <input.rml

Use it as a python module:

	import trml2pdf
	print trml2pdf.parseString(file('file.rml','r').read(),
                                   encoding='utf-8')

Notes
-----

Tiny RML2PDF is a component of the Open Report project. It can be used with the
Tiny Reporting Server to have a complete solution to render PDF file on the
fly.

The implementations of sequences, named strings, forward look ups, eval string,
and more is severely limited and basically is only implemented as far as needed
to achieve the popular "page x of y" output.

Due to the hacky way that forward references are implemented, they do not
inherit the styling around them. For this reason the <name> tag has
x and y attributes to place it, plus fontName, fontSize and fontColor to
style it. If your template is not too complicated then probably only x
and y will be required.

Check rmls/ex14.rml for a simple example of page numbers, or rmls/ex15.rml for
a more complex example using sequences so that the page number can be reset
during bulk generation.

Authors
------

Fabien Pinckaers (http://tiny.be)
Kyle MacFarlane
