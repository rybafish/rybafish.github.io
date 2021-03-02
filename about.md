[RybaFish Charts](/) is an open source software for monitoring of SAP HANA DB. RybaFish is not affiliated with SAP. It provides HANA load graph functionay for multi-tenant installations.

## Key Features
* Multitenant HANA MDC Support
* [Custom KPIs](/customKPI) support
* [Gantt chart](/customKPIgantt) KPIs support
* Works for big scale-out installations, i.e. even 10+ nodes.
* Dynamic KPIs: list of available KPIs depends on DB revision: new metrics available right away and do not require the tool update
* Simple SQL Console
* Check some minor little things on [Tips and Tricks](/tips) page

## Known Limitations
### Limitations
* No microseconds support in timestamps (LONGDATE) -- full support planned in v.07
* Some of the network calls are synchronous (chart, connects)
* Bind variables are not supported, only literals

### Bugs
* KPI highlighting feature is not perfect yet
* console: no multiple resultsets supported for procedures - PyHDB driver limitation -- fix planned in v.07
* console: 32000 output rows limit (likely a PyHDB limitation)

You can also review future plans in [TODO](/todo) list.

To see the rest of the bugs or report some - check the project's [issues](https://github.com/rybafish/rybafish/issues) page.

### License
RybaFish Charts is free open source software released under GPLv3 license. The software provided "as is" without warranty of any kind, you can use it at your own risk.
