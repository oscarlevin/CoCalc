The Calculus Companion
=============

An open textbook to support students taking calculus by providing reminders of prerequisite material.



## Compilation Instructions

This text is written in [Mathbook XML](http://mathbook.pugetsound.edu), so the primary source files can be found in the MBX directory.  These can be compiled into html or LaTeX files (as well as some other formats).  If you do not want to bother with this step or just want to grab some LaTeX to use in a worksheet or the like, the generated LaTeX is already provided in the latex folder.

### MBX Compilation

To compile from source, you will need a copy of the mathbook xsl stylesheets, as well as xsltproc installed (should be easy on linux or MacOS, but also possible on Windows---see some [windows installation notes](http://mathbook.pugetsound.edu/doc/author-guide/html/windows-install-notes.html)).

Open up a terminal and in your preferred directory, clone the mathbook and CoCalc repositories:

`git clone https://github.com/rbeezer/mathbook`

`git clone https://github.com/oscarlevin/CoCalc`

To generate LaTeX, change to the latex directory of the CoCalc folder:

`cd CoCalc/latex`


and run


`xsltproc --xinclude ../xsl/custom-latex.xsl ../mbx/cocalc.mbx`

This will use the custom thin xsl stylesheet I have created with some customizations.  It calls the mathbook-latex.xsl file from mathbook using relative paths, so it is important that you leave the mathbook and CoCalc directories parallel.

To generate html, change to the html folder.  We first need to generate the svg images from the mbx code.  This is done using the mbx script from mathbook:

`../../mathbook/script/mbx -v -c latex-image -f svg -d images ../mbx/cocalc.mbx`

You will need to have python and some other tools installed.  See the mathbook documentation.  Then to produce the html, run:

`xsltproc --xinclude ../xsl/custom-html.xsl ../mbx/cocalc.mbx`

## Contributing

Any and all suggestions to improve the text are welcome.  Thanks to those who have already pointed out typos/issues they have found.  If you would like to make a more substantial contribution, please contact me so we can discuss how best to proceed.
