---
layout: page
title: SonarQube Plugins
permalink: /sonarqube_plugins/
---

## SonarQube plugins developed by students at MSUSEL
Currently we have developed two separate plugins for the SonarQube system.
- FrontEnd Visualization Plugin - provides visualization widgets for use with our other plugins.
- Quamoco Plugin - provides an implementation of the Quamoco metamodel and analysis framework for SonarQube

#### Version 1.1.1
Requirements:
- SonarQube 5.6.5 LTS
- Java 8
- Optional: Windows for C# analysis

Installation:
- These plugins can be installed by simply dropping the jar files into the extensions/plugins of your SonarQube
installation.
The FrontEnd widgets can be added to a dashboard by simply selecting the MSUSEL Bullet Chart widget whenediting your SonarQube dashboards.

Downloads:
- [MSUSEL Visualization Plugin](https://github.com/MSUSEL/msusel-maven-repo/raw/releases/edu/montana/gsoc/msusel/sonar/msusel-frontend-plugin/1.1.1/msusel-frontend-plugin-1.1.1.jar)
- [MSUSEL Quamoco Plugin](https://github.com/MSUSEL/msusel-maven-repo/raw/releases/edu/montana/gsoc/msusel/sonar/msusel-quamoco-plugin/1.1.1/msusel-quamoco-plugin-1.1.1.jar)