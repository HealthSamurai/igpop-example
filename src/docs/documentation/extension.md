---
title: Extensions
---

# Extensions
---
---

## New Extension
---

To define a new extension, use the following template:

your-extension-name:<br>
&nbsp;&nbsp;`type`: data type of the extension<br>
&nbsp;&nbsp;`description`: Natural language description of the structure definition<br>
&nbsp;&nbsp;`title`: Name for this structure definition (human friendly)<br>
&nbsp;&nbsp;`experimental`: For testing purposes, not real usage (false)<br>
&nbsp;&nbsp;`date`: Date last changed (e.g. "2020-12-18")<br>
&nbsp;&nbsp;`publisher`: Name of the publisher (organization or individual)<br>


## Root Extension Example
---

<pre>
elements:
  extension:
  - EmployeeReporter:
      type: string
      description: Employee Reporter
      title: Employee Reporter Extension
      experimental: false
      date: "2020-12-18"
      publisher: US Core
</pre>      