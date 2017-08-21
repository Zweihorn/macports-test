# The macports-test repository
Testing some ideas on existing ports or newly invented ports for the MacPorts project.

The **MacPorts Project** is an open-source community initiative to design an easy-to-use system for compiling, installing, and upgrading either command-line, X11 or Aqua based open-source software on the Mac operating system. Apparently there are many ways one can get involved with MacPorts and peer users, system administrators & developers alike.

- The MacPorts Project official homepage - https://www.macports.org
- The MacPorts Guide - https://guide.macports.org/
- The MacPorts FAQ - https://trac.macports.org/wiki/FAQ

Please be aware that projects included in this repository may mainly be copies from existing ports and the applicable license condition of the original project may apply as appropriate. However, this repository is claiming cover of the [MIT Licence](https://choosealicense.com/licenses/mit/) for all content included.
- - - 
# Existing ports addressed 
## forked-daapd
The version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using macports) is yet not available as a macports port and I am aiming at making a *forked-daapd v25.0 port* available.

## TBC
to be continued

# Newly invented ports
## mxml
The tiny XML library [Mini-XML (mxml)](https://github.com/michaelrsweet/mxml) by Michael R Sweet seems to be quite useful and is a required library for the version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using macports).
> Mini-XML is a small XML parsing library that you can use to read XML data files or strings in your application without requiring large non-standard libraries. Mini-XML only requires a "make" program and an ANSI C compatible compiler - GCC works, as do most vendors' ANSI C compilers.

> The Mini-XML library is Copyright 2003-2017 by Michael R Sweet. License terms are described in the file "COPYING".

Currently, mxml is not yet available as a macports port and I am aimed at making a *mxml port* available.

Establishing a new *portfile* for mxml required two issues to be resolved through patches:
1. Bug Report [Problem with MXML_CUSTOM in Version mxml-2.10 #201](https://github.com/michaelrsweet/mxml/issues/201)
2. GNU [DESTDIR: Support for Staged Installs](http://www.gnu.org/prep/standards/html_node/DESTDIR.html)

My test version of a mxml 2.10 port is a newly invented port which installs successfuly on a macOS Sierra 10.12.6 environment with MacPorts 2.4.1 and is awaiting inclusion and testing with the a.m. version 25.0 of the forked-daapd media server now. There will be a commit of mxml to become a new official port to the MacPorts project after the testing with forked-daapd is completed.

## TBC
to be continued
- - - 
