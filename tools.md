---
title: "Tools"
layout: docsPage
sections:  ["Awesome Static Analysis",
			"iPlasma",
			"MARPLE",
			"Roslynator",
			"NIST SARD",
			"SWAMP"]
---
# Tools
This page will provide documentation for tools used or considered for use by the lab. The title of each tool section will be a link to the 
associated website or location of the tool (if available), and references are included for further reading on each tool. 

## [Awesome Static Analysis](https://endler.dev/awesome-static-analysis/)
Awesome Static Analysis is an community contributed collection of static analysis tools.

## [iPlasma](http://loose.upt.ro/iplasma/) 
iPlasma (unsupported) is the integrated Platform for software modeling and analysis. 
This tool measures and visualizes design-based code smells using an 'overview pyramid' that considers three structural aspects of a system (size and complexity, coupling, and inheritance). These aspects are measured using several design-focused metrics, and are then ranked against other benchmarked projects. The results from this tool can be used to identify design smells and disharmonies, following Marinescu's (the creator of this tool) method of detection using design strategies.


### iPlasma References
Lanza, Michele, and Radu Marinescu. *Object-oriented metrics in practice: using software metrics to characterize, evaluate, and improve the design of object-oriented systems.* Springer Science & Business Media, 2007.

## [MARPLE](http://www.essere.disco.unimib.it/marple-2/)
> The MARPLE (Metrics and Architecture Recognition PLug-in for Eclipse) Project focuses on the development of a complete tool for the recognition of software architectures and of design patterns (also with the help of metrics, both common object-oriented and new ones) inside Java programs. As far as the Design Pattern Detection activity is concerned, the analysis provided by the tool are static and based upon the core concept of the identification of the so-called Design Pattern Clues, which are particular code structures and details which should give hints about the presence of design pattern inside the code.

## [Roslynator](https://github.com/JosefPihrt/Roslynator)
Roslynator is an open source collection of 500+ analyzers, refactorings and fixes for C#. This project is powered by [Roslyn](https://github.com/dotnet/roslyn), a .NET compiler for C#.
Roslynator is used in our C# QATCH quality model. It can be configured as an extension for Visual Studio and Visual Studio Code.

## [NIST SARD](https://samate.nist.gov/SRD/index.php)
The National Institute of Standards and Technology has put together the Software Assurance Reference Dataset (SARD) Project as a set of programs that exhibit a plethora of flaws.
This project give a massive collection which allows us to find and download projects for testing tools or benchmarking for static analysis. 
[This article](https://www.csiac.org/journal-article/sard-thousands-of-reference-programs-for-software-assurance/) gives a good overview of the purpose of SARD and how to use it.


## [SWAMP](https://continuousassurance.org/)
> The Software Assurance Marketplace (SWAMP) is an open, no-cost, high-performance computing platform designed to serve as a resource to the software community. Created to advance the state of cybersecurity, protect critical infrastructures, and improve the resilience of open-source software (applications, libraries, etc.), the ultimate goal of the SWAMP is to provide higher quality and more secure software for government agencies, businesses, academia, and end users. The SWAMP was developed to lower the barriers for software and tool developers, researchers, and educators/students (Audience/User Groups) to do continuous software assurance. By offering multiple software analysis tools and a library of software applications with known vulnerabilities, the SWAMP is committed to making it easier to integrate security into the software development life cycle.

> There are two ways to use the SWAMP: the ready-to-use cloud computing platform at mir-swamp.org and the SWAMP-in-a-Box (SiB) open-source distribution downloadable from GitHub.

SWAMP currently contains 27 open source and 4 commercial analysis tools (as of 2017), as well as 500 sample projects to run these tools on. 
These sample projects include some of the JULIET suite of test cases, which are designed to each contain a specific CWE.

This tool is unique because it can be run on the cloud, requiring that your code be uploaded to their site. 
This means that this tool can offer a lot while requiring very little in terms of computations.

### SWAMP References
See [this page](https://continuousassurance.org/about-us/white-papers-capabilities/) for documentation and white papers on SWAMP.