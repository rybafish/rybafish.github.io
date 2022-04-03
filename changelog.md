# Upcoming Release
**091 beta I**, (not released yet)
* [variables](variables) support
* simple connections manager, save encrypted passwords
* DB interface introduced: can implement alternative connection protocols now

# Current Release
[<b>0.9 Paltus</b>](https://github.com/rybafish/rybafish/releases/download/09paltus/RybaFish_09Paltus.7z) (2022-02-17)

## Paltus Changelog

[<b>0.9 beta XI</b>](https://github.com/rybafish/rybafish/releases/download/09betaXI/RybaFish09betaXI.7z) (2022-01-26)
* legendTenantName and legendServiceName configuration options
* explain plan for sql plan cache entry now works in console
* manual scales in KPIs table are blue. If you post an empty value manual scale --> autoscale itself!
* gantt render performance **boost**: can be disabled by ganttOldImplementation: True
* gantt gradient feature: in KPI definitin gradient: True + gradientTo: '#F88' ([details](/customKPIgantt)),
* config option _chartWidth_ for cases when the default 1 is not thick enough.
* it is possible now to set Y range other than from 0 to something. To achieve this put, for example, 2000-5000 in Y-Scale.

[<b>0.9 beta 9</b>](https://github.com/rybafish/rybafish/releases/download/09beta9/RybaFish_09beta9.7z) (2021-12-23) 
* bugfix affecting multiple resultsets
* last available beta is now reported in the About dialog

<b>0.9 beta 8</b> (2021-12-21), <span style="color:blue">withdrawn</span>.
* [gantt](/customKPIgantt) bars can have titles: little text labels right inside the bar
* there is no 32k limit anymore (bug [#181](https://github.com/rybafish/rybafish/issues/181))

[<b>0.9 beta 7</b>](https://github.com/rybafish/rybafish/releases/download/09beta7/RybaFish_09beta7.7z) (2021-11-24)
* avg value is now reported in KPIs table
* basic [alerting](/soundAlerts) functionality
* hosts table enriched with service name and tenant information
* numerous bugfixes…

<b>0.9 beta 5</b> (2021-09-30), <span style="color:blue">withdrawn</span>.
* ABAP-style results copy: right mouse click in results
* Colorize KPIs option: Actions menu -> Colorize
* sql console parser fix: first statement was not recognized correctly in beta4.
* tenant name and revision reported in the window title

<b>0.9 beta 4</b> (2021-09-14), <span style="color:blue">withdrawn</span>.
* Ctrl+Shift+O auto-formats the SQL
* Ctrl+Shift+X explains plan of the selected statement
* error line now highlighted
* only the highlighted block will have line numbers on DB Exception
* date in "to" field now transates to YYYY-MM-DD **23:59:59**
* skip initial KPIs reload option
* $duration placeholder for gantt custom kpis will report human readable duration
* [multiline](/customMultiline) KPIs support
* save window layout feature (experimental)
* Bugs fixed
  * syntax highlighter now forced on paste
  * undo/redo queue cleaned up

[0.9 beta](https://github.com/rybafish/rybafish/releases/download/09beta/RybaFish09beta.7z) (2021-08-15)
* [Context SQLs](/contextSQLs): right mouse click on PLAN_ID column in results
* autocomplete in SQL Console (Ctrl+Space)
* shift highlighted point inside KPI (Alt+Left/Right)
* right click on the chart will compose a between predicate when there is already a timestamp in the clipboard
* improved SQL parsing: leading comments ignored now
* sleep() pseudo-call for sql consoles
* COMMIT and ROLLBACK are supported now
* click on indicator (right part of the status bar) switches to corresponding tab
* if there is a statement runnig, hovering mouse over indicator reports the run time
* result set highlighting: highlight particular value +  highlight value changes
* tenant neame now requested and displayed in the window title

# Release history
[0.8 Plotva](https://github.com/rybafish/rybafish/releases/download/08/RybaFish_08Plotva.7z), 22.07.2021
* switch to ESS support
* full stack upgrade
* auto-refresh result set (experimental)
* final (?) suspended statements fix

[0.7 poehali/gl](https://github.com/rybafish/rybafish/releases/download/07/RybaFish_07poehaliGL.7z), 12.04.2021
* full gas sql console support
* resurrected import of nameserver_history.trc
* layout feature: same sql tabs open after the restart

[0.6 EVH](https://github.com/rybafish/rybafish/releases/download/06/RybaFish06evh.7z), 10.10.2020
* [gantt KPIs](/customKPIgantt) type support
* chart legend now available

0.5 poehali, 12.04.2020
* sql console (experimental mode only)
* custom KPIs available as standard feature
