---
layout: viz
title: Demonstration of a QATCH Quality Dashboard
---

The MSU Software Engineering Lab is actively working on the best ways to implement and visualize the data that QATCH generates. This page is meant to be copied, improved, and remixed for however you best wish to monitor the quality of your software.

## Quality Displayed by Commit Over Time

<div id="observablehq-e77ea6c2"></div>
<script type="module">
import {Runtime, Inspector} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@4/dist/runtime.js";
import define from "https://api.observablehq.com/@thaneofcawddor/stacked-to-grouped-bars.js?v=3";
const inspect = Inspector.into("#observablehq-e77ea6c2");
(new Runtime).module(define, name => (name === "viewof layout") && inspect());
</script>

<div id="observablehq-b1f67b3e"></div>
<script type="module">
import {Runtime, Inspector} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@4/dist/runtime.js";
import define from "https://api.observablehq.com/@thaneofcawddor/stacked-to-grouped-bars.js?v=3";
const inspect = Inspector.into("#observablehq-b1f67b3e");
(new Runtime).module(define, name => (name === "chart") && inspect());
</script>

Draft of a quality over time graph that will feature overlaid bars of different colors to represent the various ISO quality characteristics. The graph will be interactive, allowing the user to zoom in on the underlying data (e.g. code findings, raw occurrence values, affected measures). Bars will be grouped by commit, so quality over the course of commits to the code repository can be monitored. Changes that led to quality changes will be viewable at the commit level.

## Raw Quantity of Tool Findings Grouped by Measure Category

<div id="observablehq-a77758d2"></div>
<script type="module">
import {Runtime, Inspector} from "https://cdn.jsdelivr.net/npm/@observablehq/runtime@4/dist/runtime.js";
import define from "https://api.observablehq.com/@thaneofcawddor/software-quality-weights-and-scores.js?v=3";
const inspect = Inspector.into("#observablehq-a77758d2");
(new Runtime).module(define, name => (name === "chart") && inspect());
</script>

When zooming in on a visualization to find the exact code finding that caused a quality score to change, bringing up all of the details in the .JSON output file will be important. Here is a selection of findings from the .JSON file:

```json
"findings": [
  {
    "characterNumber": 19,
    "filePath": "C:\\path\to\\project\\Int2BinaryTests.cs",
    "lineNumber": 53,
    "severity": 0
  },
  {
    "characterNumber": 19,
    "filePath": "C:\\path\to\\project\\Int2BinaryTests.cs",
    "lineNumber": 33,
    "severity": 0
  }
],
"toolName": "Roslynator",
"name": "RCS1032",
"description": "Remove redundant parentheses",
"value": 2
```

As you can see, there is quite a bit of data about each instance of a finding. Naturally, this data also depends on the robustness of the tool you are using. We make it easy to add new tools (See our documentation entry on [Tool Support](/pages/documentation.html#tool-addition)) where each tool needs to implement just two methods via an Interface in Java (QATCH is written in Java but language agnostic in what it can evaluate).

In the .JSON file, each finding is nested underneath the measure it corresponds to. You can also see that when there are no findings, the "findings" list in the entry is empty. We made sure the results did not omit tools that return zero findings, allowing confirmation of negative results and tracking of total toolset implementation at each run of QATCH.

```json
"Format": {
  "measure": {
    "diagnostics": [
      {
        "findings": [],
        "toolName": "Roslynator",
        "name": "RCS1001",
        "description": "Add braces (when expression spans over multiple lines)",
        "value": 0
      },

      "** MANY MORE TOOLS **"

      ]

    "name": "Format Findings",
    "value": 0.0007907979870596693
  },
  "positive": false,
  "thresholds": [
      0.0061,
      0.0242,
      0.0621
    ],
  "name": "Format",
  "description": "Code formatting. This involves how the code is written as it appears to a human reader. Common synonyms include 'Style', 'Simplification', 'Readability', 'Convention', 'Verbosity', 'Naming'.",
  "value": 1

```
