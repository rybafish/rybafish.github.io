[RybaFish Charts](/) is an open source software for monitoring HANA MDC. It provides HANA load graph functionay for multi-tenant installations.

## Key Features
* Multitenant HANA MDC Support
* [Custom KPIs](/customKPI) support
* Faster refresh due to SQL interface instead of trc file parsing
* No Java/Eclipse legacy: reduced memory requirements
* It actually works for scale-out installations, i.e. even 10+ nodes.
* No random refresh/rescale/adjust events
* More precise time scale: HANA Studio is known for putting stuff on wrong timestamps (sometimes 20-30 seconds off!)
* Accurate time/date labels 
* Dynamic KPIs: list of available KPIs depends on DB revision: new metrics available right away and do not require the tool update
* Simple SQL Console
* Check some minor little things on [Tips and Tricks](/tips) page

## Known Limitations
### Limitations
* Some of the network calls are synchronous (chart, connects)
* Separate select statement per host - design limitation

### Missing functionality
* Increase/Decrease and manual scale only works for memory metrics
* KPIs table does not have hierarchy
* KPIs columns Average and Sum do not work (does anybody ever need those?)

### Bugs
* KPI highlighting feature is not really perfect
* console: no multiple resultsets supported for procedures - driver limitation
* console: 32000 output rows limit (probably driver limitation)

You can also review future plans in [TODO](/todo) list.

To see the rest of the bugs or report some - check the project's [issues](https://github.com/rybafish/rybafish/issues) page.
