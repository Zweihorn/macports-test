# The MacPorts-Test Repository
Developing and testing some ideas by revision of existing ports or by newly formed ports for the MacPorts project.

The **MacPorts Project** is an open-source community initiative to design an easy-to-use system for compiling, installing, and upgrading either command-line, X11 or Aqua based open-source software on the Mac operating system. Like many users I am enjoying the simplicity and availability of open-source software on my Mac by help of MacPorts for some years now. There are many ways one can get involved with MacPorts and peer users, system administrators & developers alike.

- The MacPorts Project official homepage - https://www.macports.org
- The MacPorts Guide - https://guide.macports.org/
- The MacPorts FAQ - https://trac.macports.org/wiki/FAQ

Please be aware you should use the [port lint](https://guide.macports.org/#using.port.lint) command if you modified a Portfile before submitting patches back to MacPorts. The lint action checks if the Portfile conforms to the [MacPorts development standards](https://guide.macports.org/#development).

The **macports-test project** is an open-source effort to develop *Portfile* definitions and patch files to simplify the task of compiling and installing open-source software on your Mac. The macports-test project is a user initiative and is neither an official part of the MacPorts project nor a direct part of the open-source software projects referenced. 

Please feel free to download and test any experimental ports from macports-test on your own Mac at your own risk. Before you start this you may find the information of both the [MacPorts Guide section 4.6. Local Portfile Repositories](https://guide.macports.org/#development.local-repositories) and the [MacPorts Guide section 2.2.4. Install Multiple MacPorts Copies](https://guide.macports.org/#installing.macports.source.multiple) quite helpful for such experiments. Please feel free to comment on my macports-test efforts and I would be happy to learn of your findings of such experiments on your own Mac if possible.

The revised versions of the existing ports addressed and my newly formed ports will be submitted as a pull request to the MacPorts project after completing basic application tests sufficiently to my best knowledge. A final run of the [port lint](https://guide.macports.org/#using.port.lint) command shall ensure the *Portfile* conforms to the [MacPorts development standards](https://guide.macports.org/#development). When and if such an experimental port will become available as an official port is solely at the deliberations of the MacPorts team. 

Currently the goal of a **forked-daapd** port is the main driver of my efforts.

- - - 

# Existing Ports Revised 

## antlr3
[ANTLRv3](http://www.antlr3.org), ANother Tool for Language Recognition, is the legacy version of a language tool that provides a framework for constructing recognizers, compilers, and translators from grammatical descriptions containing Java, C#, or C++ actions.

> ANTLR, ANother Tool for Language Recognition, is a language tool that provides a framework for constructing recognizers, interpreters, compilers, and translators from grammatical descriptions containing actions in a variety of target languages. ANTLR provides excellent support for tree construction, tree walking, translation, error recovery, and error reporting.

> Terence Parr is the maniac behind ANTLR and has been working on language tools since 1989.

There is an official [antlr3 3.2 Portfile](https://github.com/macports/macports-ports/blob/master/lang/antlr3/Portfile) available but this does not meet the requirements for the b.m. **forked-daapd** port. Furthermore, I aim for a newly formed *antlr3-no-st3* to avoid conflicts with other ports depending on the antlr3 3.2 port and to better meet the forked-daapd port requirements at the same time.

A more recent 4+ version of [ANTLR](http://www.antlr.org) is available. IMHO it is completlely unclear if this could be added to improve a revised version of the forked-daapd port in the future.

## gperf @3.0.4
This is an **outdated version of the gperf port** and please be advised to always install the gperf 3.1+ port from MacPorts instead.

Although forked-daapd requires gperf the latter cannot be installed in its recent version due to a incompatibility between *gperf* and *gindent* causing a broken build. The workaround depends on the availability of an outdated gperf port and the combination of gperf @3.0.4_2 and gindent @2.2.11_0 can be built and installed successfully.

The recently introduced incompatibility between *gperf* and *gindent* is one of the obstacles in establishing the forked-daapd experimental port. Please refer to the MacPorts Ticket "[#54466 assigned defect - gindent @2.2.11: build fails](https://trac.macports.org/ticket/54466)" for background information. There is a workaround procedure by downgrading gperf, building gindent, and then upgrading gperf again. However, you would have to follow the well documented but cumbersome procedure as detailed by the [MacPorts Wiki: How to install an older version of a port](https://trac.macports.org/wiki/howto/InstallingOlderPort) if you could not reactivate gperf @3.0.4 from a prior port install.

I make a copy of the **outdated gperf @3.0.4 port** available in this repository as the procedure to search and download an outdated port from the MacPorts repository could become quite a challenge. This is quite experimental and solely to allow continued development of the experimental forked-daapd port as long as the a.m. issue is not resolved sufficiently.

## TBC
to be continued

# Newly Formed Ports

## forked-daapd
The [forked-daapd project](https://ejurgensen.github.io/forked-daapd/) by @ejurgensen is an open-source Linux/FreeBSD DAAP (iTunes) and MPD media server with support for AirPlay devices (multiroom), Apple Remote (and compatibles), Chromecast, Spotify and internet radio. The [forked-daapd media server](https://github.com/ejurgensen/forked-daapd/releases) inherits a version for macOS (using MacPorts) but is yet not available on MacPorts itself.

>forked-daapd is an iTunes-compatible media server for sharing your media library over the local network with DAAP clients like iTunes. Like iTunes, it can be controlled by Apple Remote (and compatibles) and stream music directly to AirPlay devices. It also supports streaming to RSP clients (Roku devices) and streaming from Spotify.

The [installation instructions for forked-daapd](https://github.com/ejurgensen/forked-daapd/blob/master/INSTALL) is an excellent source of documentation for developers. It contains instructions for installing forked-daapd for Raspbian (Raspberry Pi), Debian/Ubuntu, Fedora, FreeBSD and certainly macOS (using MacPorts). 

The following ports all have to be newly formed in first place to establish a *Portfile* for a forked-daapd installation.

### forked-daapd 25.0
Starting with version 25.0 the [forked-daapd media server](https://github.com/ejurgensen/forked-daapd/releases) is certainly aimed at an installation on macOS (using MacPorts) but is yet not available at MacPorts. My goal is to make a *forked-daapd v25.0 port* available.

Unfortunately, I found several obstacles in [available MacPorts ports](https://www.macports.org/ports.php) required by while developing the experimental forked-daapd Portfile:

- [X] *gperf 3.1* - GNU perfect hash generator
  - cannot be installed in its recent version due to a incompatibility between *gperf* and *gindent* causing a broken build (see *gperf @3.0.4* above)
  - workaround available
- [ ] *avahi 0.6.32* - implementation of the DNS Service Discovery and mDNS for Zeroconf Networking
  - cannot be installed due to a "Undefined symbols for architecture x86_64" failure
  - open

On the positive side, most if not all of the newly formed ports for forked-daapd listed below were installed successfuly on the commandline via the *port install* command in my current [MacPorts Copy](https://guide.macports.org/#installing.macports.source.multiple) testbed environment on macOS Sierra 10.12.6 with XCode 8.3.3 and MacPorts 2.4.1 and are awaiting inclusion and testing with this version 25.0 of the forked-daapd media server now. There will be several commits of *Portfiles* which hopefuly become new official ports to the MacPorts project after the testing with forked-daapd is completed.

### antlr3-no-st3
There is an official antlr3 3.2 Portfile available (see above) but this does not meet the forked-daapd requirements.

The ANTLRv3 is a *Java* tool to be downloded as *antlr-3.5.2-complete-no-st3.jar* package from the [ANTLRv3 Downloads](http://www.antlr3.org/download.html) page.

My test version of a antlr3 3.5.2 port was successfuly installed on the a.m. envrironment by the *port install antlr3* command. 

The name of this port will be changed to to *antlr3-no-st3* to avoid disambiguation with the existing official antlr3 port.

### libantlr3c
The ANTLRv3 C runtime engine for the antlr3 parser can be downloded from http://www.antlr3.org/download/C as *libantlr3c-3.4.tar.gz* tarball. Apparanetly there is no more recent version of the ANTLRv3 C runtime library available. However, the combination of libantlr3c 3.4 with antlr3 3.5.2 does meet the requirements of forked-daapd since the version 24.2 of forked-daapd obviously.

My test version of a libantlr3c 3.4 port was successfuly installed on the a.m. environment by the *port install libantlr3c* command. 

### libinotify-kqueue
The [libinotify-kqueue library](https://github.com/libinotify-kqueue/libinotify-kqueue) by Dmitry Matveev and Vladimir Kondratiev seems to be quite useful and is a required library for the version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using MacPorts).
> The purpose of this library is to provide inotify API on the BSD family of operating systems. The library uses kqueue(2) to monitor the file system activity.

> Copyright (c) 2011-2014 Dmitry Matveev <me@dmitrymatveev.co.uk>

> Copyright (c) 2014-2016 Vladimir Kondratiev <wulf@cicgroup.ru>

Currently, libinotify-kqueue is not a MacPorts port and I am making an experimental *libinotify-kqueue port* available.

My test version of a libinotify-kqueue 20170711 port was installed successfuly on the a.m. environment by the *port install libinotify-kqueue* command. 

### mxml
The tiny XML library [Mini-XML (mxml)](https://github.com/michaelrsweet/mxml) by Michael R Sweet seems to be quite useful and is a required library for the version 25.0 of the [forked-daapd media server](https://ejurgensen.github.io/forked-daapd/) for macOS (using MacPorts).
> Mini-XML is a small XML parsing library that you can use to read XML data files or strings in your application without requiring large non-standard libraries. Mini-XML only requires a "make" program and an ANSI C compatible compiler - GCC works, as do most vendors' ANSI C compilers.

> The Mini-XML library is Copyright 2003-2017 by Michael R Sweet. License terms are described in the file "COPYING".

Currently, mxml was not available as a MacPorts port and I am making an experimental *mxml port* available.

Establishing a new *Portfile* for mxml required two issues to be resolved through patches:
1. Bug Report [Problem with MXML_CUSTOM in Version mxml-2.10 #201](https://github.com/michaelrsweet/mxml/issues/201) - *patch-mxml-file.c-issue201.diff*
2. Missing GNU [DESTDIR: Support for Staged Installs](http://www.gnu.org/prep/standards/html_node/DESTDIR.html) - *patch-Makefile.in-DESTDIR.diff*

My test version of a mxml 2.10 port was installed successfuly on the a.m. environment by the *port install mxml* command. 

## TBC
to be continued

- - - 

# Getting Help And Reporting Problems
The macports-test project page provides access to the [Github issue tracking page](https://github.com/Zweihorn/macports-test/issues). Please be aware that I am not the developer of the open-source software projects referenced by my experimental ports and this project is just a user initiative.

# Legal Stuff
Copyright 2017 by Zweihorn. License terms are described in the file "LICENSE" of macports-test.

Please be aware that projects i.e. ports included in this repository may mainly be copies from existing ports and/or open-source software projects and the applicable license condition of the original project may apply as appropriate. However, this repository is claiming cover by the [MIT Licence](https://choosealicense.com/licenses/mit/) for all content and the Software included.

- - - 
