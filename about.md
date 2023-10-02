---
title: About RybaFish Charts
---

[RybaFish Charts](/) is an open source cross-platform software for monitoring of SAP HANA DB. RybaFish is not affiliated with SAP. It provides HANA load graph functionay for multi-tenant installations.

~~Only one installation can be monitored~~: connection to two or more servers in parallel was not supported before 0.95 Ishkhan which has experimental support of multiple data provisers (HANA/non-HANA). Anyway, several SQL consoles were always supported.

## Key Features
* Multitenant HANA MDC Support
* [Custom KPIs](/customKPI) support
* [Gantt chart](/customKPIgantt) KPIs support
* Works for big scale-out installations, i.e. even 10+ nodes.
* Dynamic KPIs: list of available KPIs depends on DB revision: new metrics available right away and do not require the tool update
* powerful [SQL Console](/sqlconsole)
* Check some minor little things on [Tips and Tricks](/tips) page

## Known Limitations
### Limitations
* Charts: chart network calls are synchronous
* SQL console: bind variables are not supported, only literals

### Bugs
* KPI highlighting feature is not perfect yet - but you can move highligted point by Alt+Left/Right/Up/Down
* console: ~~32000 output rows limit (PyHDB bug)~~ - fixed in v0.9 Paltus

You can also review future plans in [TODO](/todo) list.

To see the rest of the bugs or report some - check the project's [issues](https://github.com/rybafish/rybafish/issues) page.

### License
RybaFish Charts is free open source software released under GPLv3 license. The software provided "as is" without warranty of any kind, you can use it at your own risk.
