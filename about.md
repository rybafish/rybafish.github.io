---
title: best SAP HANA monitoring tool
---

[RybaFish Charts](/) is an independent, open-source solution for SAP HANA DB monitoring, operating without affiliation to SAP. It delivers SAP HANA load graph capabilities optimized for both multi-tenant and scale-out environments. It also provides quite powerful [SQL-console](/sqlconsole).

~~Only one installation can be monitored~~: connection to two or more servers in parallel was not supported before 0.95 Ishkhan which has experimental support of multiple data provisers (HANA/non-HANA). Multiple SQL consoles were always supported.

## Key Features
* Multitenant HANA MDC Support
* [Custom KPIs](/customKPI) support
* [Gantt chart](/customKPIgantt) KPIs support
* Works for big scale-out installations, i.e. even 10+ nodes.
* Dynamic KPIs: list of available KPIs depends on DB revision: new metrics available right away and do not require the tool update
* powerful [SQL Console](/sqlconsole)
* Check some minor little things on [Tips and Tricks](/tips) page

To see development plans/progress or report issues - check out the project's [issues](https://github.com/rybafish/rybafish/issues) page.

Check out the introduction video:

{% include youtube.html id="7dm4MtOXavc" %}

### License
RybaFish Charts is free open source software released under GPLv3 license. The software provided "as is" without warranty of any kind, you can use it at your own risk.
