---
layout: page
title: "External Tools"
author: "Andrew Johnson"
categories: documentation
tags: [documentation]
---

This page will provide documentation for tools used or considered for use by the lab. The title of each tool section will be a link to the 
associated website or location of the tool (if available), and references are included for further reading on each tool. 


## Table of Contents

[Angr](#angr)

[Awesome Static Analysis](#awesome-static-analysis)

[Ghidra](#ghidra)

[Idaho National Lab Tools](#idaho-national-lab-tools)

[iPlasma](#iplasma)

[MARPLE](#marple)

[NIST SARD](#nist-sard)

[Roslynator](#roslynator)

[SWAMP](#swamp)

[Triton](#triton)



## [Angr](https://angr.io/)
Angr is "a python framework for analyzing binaries. It combines both static and dynamic symbolic ("concolic") analysis, making it applicable to a variety of tasks." This tool may be used for a variety of purposes, including but not limited to control-flow graph recovery, symbolic execution, ROP chain building, and binary hardening. 

## [Awesome Static Analysis](https://endler.dev/awesome-static-analysis/)
Awesome Static Analysis is an community contributed collection of static analysis tools.

## [Idaho National Lab Tools](https://github.com/idaholab/)

#### [atDisCo](https://github.com/idaholab/atDisco) 
"Annotated and Translated Disassembled Code (@DisCo) is a graph based datastore designed to organize firmware and software analysis data across builds, packages and systems, providing a highly scalable platform enabling automated binary software analysis tasks including corpora construction and storage for machine learning."

#### [STIG](https://github.com/idaholab/STIG)
"Structured Threat Intelligence Graph (STIG) is an open source tool for creating, editing, querying, analyzing and visualizing threat intelligence. It uses STIX version 2 as its data format and uses a graph database (OrientDB) to store the data."

#### [STOTS](https://github.com/idaholab/STOTS)
"Structured Threat Observable Tool Set (STOTS) is a tool set, not an application, developed by Idaho National Laboratory (INL) as part of the California Energy Systems for the 21st Century (CES-21) project. STOTS uses Structured Threat Information Expression (STIX) as a method for detection and monitoring. These tools can be used by cyber personnel with familiarity of command line scripting to find Indicators of Compromise (IOCs) on configuration specific systems. The tools developed in STOTS focus on surgical detection and response for a specific threat, enabling cyber defenders to be more agile in defense against cyber adversaries. This provides an agnostic tool set which enables detection in the absence of, or in coordination with commercial-off-the-shelf (COTS) products."

#### [WiiBin](https://github.com/idaholab/WiiBin)
WiiBin, or 'What is it Binary?' utilizes machine learning to identify the machine architecture and locate important code segments. This tool boasts the ability to detect architecture with >80% accuracy with as little as 30% of the original file.


## [iPlasma](http://loose.upt.ro/iplasma/) 
iPlasma (unsupported) is the integrated Platform for software modeling and analysis. 
This tool measures and visualizes design-based code smells using an 'overview pyramid' that considers three structural aspects of a system (size and complexity, coupling, and inheritance). These aspects are measured using several design-focused metrics, and are then ranked against other benchmarked projects. The results from this tool can be used to identify design smells and disharmonies, following Marinescu's (the creator of this tool) method of detection using design strategies.

### iPlasma References
Lanza, Michele, and Radu Marinescu. *Object-oriented metrics in practice: using software metrics to characterize, evaluate, and improve the design of object-oriented systems.* Springer Science & Business Media, 2007.

## [Ghidra](https://ghidra-sre.org/)
Ghidra is a tool developed by the NSA for binary reverse engineering. It was released to the public in 2019 and has quickly found
widespread use. For an example of how this tool can be used, see [Ghidra Ninja's Youtube series](https://www.youtube.com/playlist?list=PLniOzp3l9V83Yf52IXJTvW9rjstdqkduP)
on reversing the Wannacry malware using Ghidra.

## [MARPLE](http://www.essere.disco.unimib.it/marple-2/)
"The MARPLE (Metrics and Architecture Recognition PLug-in for Eclipse) Project focuses on the development of a complete tool for the recognition of software architectures and of design patterns (also with the help of metrics, both common object-oriented and new ones) inside Java programs. As far as the Design Pattern Detection activity is concerned, the analysis provided by the tool are static and based upon the core concept of the identification of the so-called Design Pattern Clues, which are particular code structures and details which should give hints about the presence of design pattern inside the code."

## [MISP](https://www.misp-project.org/index.html)
"A threat intelligence platform for gathering, sharing, storing and correlating Indicators of Compromise of targeted attacks, threat intelligence, financial fraud information, vulnerability information or even counter-terrorism information."

## [NIST SARD](https://samate.nist.gov/SRD/index.php)
The National Institute of Standards and Technology has put together the Software Assurance Reference Dataset (SARD) Project as a set of programs that exhibit a plethora of flaws.
This project give a massive collection which allows us to find and download projects for testing tools or benchmarking for static analysis. 
[This article](https://www.csiac.org/journal-article/sard-thousands-of-reference-programs-for-software-assurance/) gives a good overview of the purpose of SARD and how to use it.

## [Roslynator](https://github.com/JosefPihrt/Roslynator)
Roslynator is an open source collection of 500+ analyzers, refactorings and fixes for C#. This project is powered by [Roslyn](https://github.com/dotnet/roslyn), a .NET compiler for C#.
Roslynator is used in our C# QATCH quality model. It can be configured as an extension for Visual Studio and Visual Studio Code.

## [SWAMP](https://continuousassurance.org/)
"The Software Assurance Marketplace (SWAMP) is an open, no-cost, high-performance computing platform designed to serve as a resource to the software community. Created to advance the state of cybersecurity, protect critical infrastructures, and improve the resilience of open-source software (applications, libraries, etc.), the ultimate goal of the SWAMP is to provide higher quality and more secure software for government agencies, businesses, academia, and end users. The SWAMP was developed to lower the barriers for software and tool developers, researchers, and educators/students (Audience/User Groups) to do continuous software assurance. By offering multiple software analysis tools and a library of software applications with known vulnerabilities, the SWAMP is committed to making it easier to integrate security into the software development life cycle."

"There are two ways to use the SWAMP: the ready-to-use cloud computing platform at mir-swamp.org and the SWAMP-in-a-Box (SiB) open-source distribution downloadable from GitHub."

SWAMP currently contains 27 open source and 4 commercial analysis tools (as of 2017), as well as 500 sample projects to run these tools on. 
These sample projects include some of the JULIET suite of test cases, which are designed to each contain a specific CWE.

This tool is unique because it can be run on the cloud, requiring that your code be uploaded to their site. 
This means that this tool can offer a lot while requiring very little in terms of computations.

### SWAMP References
See [this page](https://continuousassurance.org/about-us/white-papers-capabilities/) for documentation and white papers on SWAMP.

## [Triton](https://triton.quarkslab.com/)
Triton is a dynamic binary analysis framework developed by quarkslab. This framework enables python bindings for components such as 
a dynamic symbolic execution engine, dynamic taint engine, abstract syntax tree representations of x86, x86-64 and AArch64 Instructions Set 
Architecture, and satisfiability modulo theories simplification and solving. 

