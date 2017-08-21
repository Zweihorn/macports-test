# The MacPorts-Test Repository
Developing and testing some ideas by revision of existing ports or by newly formed ports for the MacPorts project.

The **MacPorts Project** is an open-source community initiative to design an easy-to-use system for compiling, installing, and upgrading either command-line, X11 or Aqua based open-source software on the Mac operating system. Like many users I am enjoying the simplicity and availability of open-source software on my Mac by help of MacPorts for some years now. There are many ways one can get involved with MacPorts and peer users, system administrators & developers alike.

- The MacPorts Project official homepage - https://www.macports.org
- The MacPorts Guide - https://guide.macports.org/
- The MacPorts FAQ - https://trac.macports.org/wiki/FAQ

The **macports-test project** is an open-source effort to develop *Portfile* definitions and patch files to simplify the task of compiling and installing open-source software on your Mac. The macports-test project is a user initiative and is neither an official part of the MacPorts project nor a direct part of the open-source software projects referenced. 

Please feel free to download and applicate any experimental ports of macports-test on your own Mac at your own risk. You may find the information of both the [MacPorts Guide section 4.6. Local Portfile Repositories](https://guide.macports.org/#development.local-repositories) and the [MacPorts Guide section 2.2.4. Install Multiple MacPorts Copies](https://guide.macports.org/#installing.macports.source.multiple) quite helpful for such experiments. Please feel free to comment on my macports-test efforts and I would be happy to learn of your findings of such experiments on your own Mac if possible.

The revised versions of the existing ports addressed and my newly formed ports will be submitted as a pull request to the MacPorts project after completing basic application tests sufficiently to my best knowledge. If such experimental port will become available as an official port IMHO is solely up to the deliberations of the MacPorts team.

- - - 

# Existing Ports Addressed 
## forked-daapd
The version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using MacPorts) is yet not available as a MacPorts port and I am aiming at making a *forked-daapd v25.0 port* available.

## TBC
to be continued

# Newly Formed Ports
## libinotify-kqueue
The [libinotify-kqueue library](https://github.com/libinotify-kqueue/libinotify-kqueue) by Dmitry Matveev and Vladimir Kondratiev seems to be quite useful and is a required library for the version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using MacPorts).
> The purpose of this library is to provide inotify API on the BSD family of operating systems. The library uses kqueue(2) to monitor the file system activity.

> Copyright (c) 2011-2014 Dmitry Matveev <me@dmitrymatveev.co.uk>

> Copyright (c) 2014-2016 Vladimir Kondratiev <wulf@cicgroup.ru>

Currently, libinotify-kqueue was not available as a MacPorts port and I am making an experimental *libinotify-kqueue port* available.

My test version of a libinotify-kqueue 20170711 port is a newly formed port which installed successfuly on the commandline via the *port install libinotify-kqueue* command on a macOS Sierra 10.12.6 environment with MacPorts 2.4.1 and is awaiting inclusion and testing with the a.m. version 25.0 of the forked-daapd media server now. There will be a commit of libinotify-kqueue to hopefuly become a new official port to the MacPorts project after the testing with forked-daapd is completed.

## mxml
The tiny XML library [Mini-XML (mxml)](https://github.com/michaelrsweet/mxml) by Michael R Sweet seems to be quite useful and is a required library for the version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using MacPorts).
> Mini-XML is a small XML parsing library that you can use to read XML data files or strings in your application without requiring large non-standard libraries. Mini-XML only requires a "make" program and an ANSI C compatible compiler - GCC works, as do most vendors' ANSI C compilers.

> The Mini-XML library is Copyright 2003-2017 by Michael R Sweet. License terms are described in the file "COPYING".

Currently, mxml was not available as a MacPorts port and I am making an experimental *mxml port* available.

Establishing a new *Portfile* for mxml required two issues to be resolved through patches:
1. Bug Report [Problem with MXML_CUSTOM in Version mxml-2.10 #201](https://github.com/michaelrsweet/mxml/issues/201) - *patch-Makefile.in-DESTDIR.diff*
2. Missing GNU [DESTDIR: Support for Staged Installs](http://www.gnu.org/prep/standards/html_node/DESTDIR.html) - *patch-Makefile.in-DESTDIR.diff*

My test version of a mxml 2.10 port is a newly formed port which installed successfuly on the commandline via the *port install mxml* command on a macOS Sierra 10.12.6 environment with MacPorts 2.4.1 and is awaiting inclusion and testing with the a.m. version 25.0 of the forked-daapd media server now. There will be a commit of mxml to hopefuly become a new official port to the MacPorts project after the testing with forked-daapd is completed.

## TBC
to be continued

- - - 

# Getting Help And Reporting Problems
The macports-test project page provides access to the [Github issue tracking page](https://github.com/Zweihorn/macports-test/issues). Please be aware that I am not the developer of the open-source software projects referenced by my experimental ports and this project is just a user initiative.

# Legal Stuff
Copyright 2017 by Zweihorn. License terms are described in the file "LICENSE" of macports-test.

Please be aware that projects i.e. ports included in this repository may mainly be copies from existing ports and/or open-source software projects and the applicable license condition of the original project may apply as appropriate. However, this repository is claiming cover by the [MIT Licence](https://choosealicense.com/licenses/mit/) for all content and the Software included.

- - - 
