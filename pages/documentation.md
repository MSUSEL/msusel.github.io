---
layout: page
title: "Documentation"
author: "Thane Richard"
categories: documentation
tags: [documentation]
image: margaret_hamilton.jpg
---

![hamilton](/assets/img/margaret_hamilton.jpg)

# Quality Analysis

The primary project of the MSU Software Engineering Lab is the grant-funded creation of software that measures the quality of other software. Due to the needs of our funder, the current version (v0.3.0) is designed to measure software written in the C# language. However, the quality framework we have selected, QATCH, is bifurcated into language-agnostic and language-specific elements, making expansion beyond C# a more manageable task for the quality-enthusiastic reader.

## Table of Contents

1. [Introduction](#introduction)
   1. [Attribution](#attribution)
   2. [What is QATCH?](#what-is-qatch)
   3. [How It Works](#how-it-works)
	   a. [Benchmark Repository](#benchmark-repository)
	   b. [Quality hierarchy](#quality-hierarchy)
		 c. [Tool Selection](#Tool-Selection)
2. [Installation](#installation)
   1. [Requirements](#requirements)
   2. [Where to download](#github-pages-installation)
   3. [Local Installation](#local-installation)
3. [Our Live Demo](#our-live-demo)


# Introduction

## Attribution

This project is a fork of the QATCH project found at QuthEceSoftEng's [GitHub](https://github.com/AuthEceSoftEng/qatch) and [Website](http://83.212.105.167:8080/OnlineProjectEvaluator/).  

This fork modifies QATCH to behave more like a library primarily through: modularizing code, introducing Maven project structure, removing GUI elements, removing main methods, and having all methods be language and tool agnostic.

Legacy build, config, rulesets, and default model files are left in an archive folder.

## What is QATCH?

QATCH, which is an acronym for Quality Analysis Tool Chain, is a framework for analyzing software quality. Analyzing software quality is a tricky business. First, there are the different syntax's and conventions of different software languages. We handle this in our implementation of QATCH by separating language-agnostic elements of the quality analysis from the tools (more on tools later) that are language-specific. In our current instance, the software we are analyzing is written in C#, so the tools we use are developed for the specific parsing of C# code. But adding support for a language is limited more by 1) the availability of analysis tools and 2) the ease of use of those tools. In our "Adding Tool Support" section (coming soon), we will show how to hook up new tools to QATCH. Our QATCH implementation is written in Java.

The second element of quality analysis that is a bit tricky is the subjective nature of the entire concept of "quality." Ask a game developer what "quality" means to them and they may list out compatibility across multiple platforms, software performance (no one wants a game that LAAAAAAAAAAAAGS), or readability so that multiple developers can collaborate easily and push updates frequently. Conversely, ask a developer at an autonomous vehicle company what "quality" means and the emphasis will likely be on completely different characteristics such as safety, reliability, and security.

Fortunately, the International Organization for Standardization (ISO) has come up with eight quality characteristics called the [ISO 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010). Those eight characteristics are:
 1. Functional Suitability
 2. Performance Efficiency
 3. Compatibility
 4. Usability
 5. Reliability
 6. Security
 7. Maintainability
 8. Portability

The QATCH framework uses these eight characteristics of software quality as the foundation upon which the quality model is built. But that still does not answer the "game developer versus autonomous vehicle" dilemma of how to value those eight characteristics.

To address this challenge, an important part of setting up QATCH for use on your software as an individual or as part of a team is taking a calm reflective moment to decide what quality means to you. After coming back from your cave in the mountains, you should update a .CSV file that gives relative weights to each of the characteristics. We have bundled a fairly generic comparison matrix with our QATCH release that you can see [here](https://github.com/msusel-qatch/msusel-qatch).

## How It Works

Understanding how QATCH works is the subject of several Master's theses and PhD dissertations in our department as well as within the field of software engineering more broadly. That is not to say that the instructions are very complicated, but they reflect decisions that are very much in-flux and up for academic debate. I will flag these as we move through the Instructions, but I do not want this to distract from the practical implementation of QATCH.

Here are the main elements to cover to have an entry-level understanding of QATCH:
1. ~~Comparison matrices~~ (see previous section)
2. Benchmark repository
3. Quality hierarchy
4. Tool Selection

### Benchmark Repository
Let's zoom in on two specific tools  (more on tools in "[Tool Selection](#tool-selection)") that we use to scan C# code:

 - [RCS1037](https://github.com/JosefPihrt/Roslynator/blob/master/src/Analyzers/README.md): Remove Trailing White-space
 - [RCS????](https://github.com/JosefPihrt/Roslynator/blob/master/src/Analyzers/README.md): Outdated hash function

When we run these tools, it is expected that there would be several instances of finding trailing white-space and maybe, for the sake of our example, one instance of using a non-secure outdated method of creating hashes. Clearly the one occurrence of the hashing function has much more of an impact on quality than a few extra white-spaces, but what if you or your team valued Maintainability (where the white-space tool would likely live) over Security?

Before QATCH considers the values from your comparison matrix, we need to normalize the results of running our tools to determine a baseline. To do this, we first run QATCH on what we call the "Benchmark Repository." This is a collection of software projects that are deemed to be of high quality. We created this Benchmark Repository by combing through GitHub and finding about sixty projects that had a 5-star rating *(Academic Discussion: what is the best method for creating a robust collection of benchmark software?)*. This is then normalized further by dividing the number of occurrences of any tool finding by the total lines of code of the project. We discard outliers and come up with a spectrum for what is expected in a quality software project.

In terms of how your implementation of QATCH uses this benchmark information, there is a

### Quality Hierarchy
Coming soon!


### Tool Selection

Coming soon!

---

# Installation

1. Requirements
2. Where to Download
3. Local Installation

## Requirements

QATCH needs the following in order to run:

- **Maven**.
You can learn more about Maven and how to install Maven [here](https://maven.apache.org/).
To see whether you have maven installed, run the following command in your terminal:

```
$ mvn -v
```

- **The R Language**.
This is only required for deriving a fresh model, which we recommend each organization do as an exercise for determining what quality means (see [What is QATCH?](#what-is-qatch)). For expediency and to get familiar with QATCH, we include a generic quality model in the download, which avoids the need for installing R.

  We are working to remove this dependency as it is not really necessary and is the result of some legacy code that needs updating. But, for now, you can download R [here](https://cran.r-project.org/).



## Where to Download

The latest version of the QATCH software is on the ["Releases" page](https://github.com/msusel-qatch/msusel-qatch/releases) of the MSUSEL-QATCH GitHub repository.

Download to any directory.

## Local Installation

### Update or Download the Code To Be Evaluated
Run `$ git fetch` to update your local repository or `$ git clone https://yourcoderepository.com` to create a local directory of the code whose quality you are looking to analyze. Remember, at this time MSUSEL QATCH only has language support for projects written in C#.

The first thing that the