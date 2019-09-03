[RybaFish Charts](/) is an open source software for monitoring HANA MDC. It returns HANA load graph functionay for multitenant installations.

## Key Features
* Multitenant HANA MDC Support
* Faster refresh due to SQL interface instead of trc file parsing
* No Java/Eclipse legacy: reduced memory requirements
* It actually works for scale-out installations, i.e. even 10+ nodes.
* No random refresh/rescale/adjust events
* More precise time scale: HANA Studio is known for putting stuff on wrong timestamps (sometimes 20-30 seconds off!)
* Accurate time/date labels 
* Dynamic KPIs: list of available KPIs depends on DB revision: new metrics available right away and do not require the tool update
* Check some minor little things on [Tips and Tricks](/tips) page

## Known Limitations
### Limitations
* All the network calls are synchronous
* Separate select statement per host - design limitation

### Missing functionality
* Not correct per-sample metrics display: it's smth/sample and not smth/sec (example statements/per second), Absolute values for such metrics are not the same as in SAP HANA Studio.
* Most of the metrics not scaled down (disk size is 30000000000 bytes)
* ~~No Y-Scale grid~~
* ~~No auto-refresh available~~
* Increase/Decrease and manual scale only works for memory metrics
* KPIs table does not have hierarchy
* KPIs columns Average and Sum do not work (does anybody ever need those?)

### Bugs
* KPI highlighting feature is not really perfect

You can also review future plans in [TODO](/todo) list.

To see the rest of the bugs or report some - check the project's [issues](https://github.com/rybafish/rybafish/issues) page.
