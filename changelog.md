---
title: Changelog
---

Links for most recent macOS builds available [here](https://github.com/rybafish/rybafish/issues/771).

# Upcoming build
* linux, macOS builds for Ishkhan
* fix of [scriptsFolder](/config#scriptsFolder) setting bug
* ctrl+mouse wheel to increase/decrease font in SQL consoles and resultsets
* to_date('') --> exception instead NULL, pyhdb bug fix.
* server processing time for SQL consoles
* time scale 8 hours (experimental)
* ess legend crash fix
* [reconnectTimer](/config#reconnectTimer)

# 095 Ishkhan
[<b>095 Ishkhan</b>](https://github.com/rybafish/rybafish/releases/download/095/RybaFish_095Ishkhan.7z) last major build, 2023-08-12
* warning in sql consoles for prodution db
* log rotation feature, [logSizeMax](/config#logSizeMax)
* [async](/customMultiline#async) multiline mode
* Timezones management, [details](/timezones)
* CSV [import wizard](https://youtu.be/Q1kp02MtZHg): timestamp, integer and varchar types supported for now
* updated delta merges KPI, made in course of [this](https://youtu.be/BCVW2asUgqk) tutorial
* multiple [variables](/variables) bugfixes
* bugfix for grid labels on 4 hours scale (maximum zoom out)
* minor performance improvements
* stack upgrade (3.10 -> 3.11)
* major internal structures/interfaces rework
* **Experimental** (you need to set `experimental: True` in config.yaml to use those) extremely powerful features:
    * SQLite support for charts: if m_load_history* tables detected in SQLite database - standard SAP HANA KPIs will work
    * SQLite support for sql consoles: you can just use RybaFish to work with SQLite databases
    * Secondary connection / Multiple data providers: now you can show charts from two or more HANA/non-HANA sources on the same chart
    * Smile and stay well.

# 093 beta III
[<b>093 beta III</b>](https://github.com/rybafish/rybafish/releases/download/093betaIII/RybaFish_093betaIII.7z) (2023-07-02)
* updated delta merges KPI from [this](https://youtu.be/BCVW2asUgqk) tutorial
* stack upgrade (3.10 -> 3.11)

# 093 beta II
[<b>093 beta II</b>](https://github.com/rybafish/rybafish/releases/download/093betaII/RybaFish_093betaII.7z) (2023-05-18)
* new log file, automatic log truncation, [logSizeMax](/config#logSizeMax)
* multiple [variables](/variables) bugfixes

# 093 beta I
[<b>093 beta I</b>](https://github.com/rybafish/rybafish/releases/download/093betaI/RybaFish_093betaI.7z) (2023-04-12)
* async multiline mode
* Timezones management, [link](/timezones)
* trace import fix: data might be loaded just partially in some cases

# 093 beta 0
[<b>093 beta 0</b>](https://github.com/rybafish/rybafish/releases/download/093beta0/RybaFish_093beta0.7z) (2023-02-16)
* SQLite support (experimental mode only)
* multiple data providers support  (experimental mode only)
* CSV [import wizard](https://youtu.be/Q1kp02MtZHg): timestamp, integer and varchar types supported for now
* safe thread exceptions handling

# 091 Sig/ssl

[<b>091 Sig/ssl</b>](https://github.com/rybafish/rybafish/releases/download/092sigssl/RybaFish_092sigssl.7z) (2022-11-01)
* improved number formatting performance, can switch off by setting [newNumbersFormatting](/config#newNumbersFormatting): False
* enforce [thousandsSeparator](/config#thousandsSeparator) and [decimalPoint](/config#decimalPoint) - work only for newNumbersFormatting
* minor editor (crashable) bugfixes
* web infrastructure moved to amazon s3+cf
* SSL support

## Sig Changelog
[<b>091 Sig</b>](https://github.com/rybafish/rybafish/releases/download/091sig/RybaFish_091sig.7z) (2022-08-12)

* Change KPI color dialog (context menu in KPIs table).
* LOB containing consoles will have own indication
* it is rather markdown and not ABAP-style copy now. can be disabled by copy-markdown: False
* import of nameserver_history.trc update for newer formats
* support of timezone for nameserver_history.trc import: [import_timezone_offset](/config#import_timezone_offset).
* countdown secods before triggering autorefresh now displayed

[<b>091 beta IV</b>](https://github.com/rybafish/rybafish/releases/download/091betaIV/RybaFish_091betaIV.7z) (2022-06-30)
* [macOS](https://github.com/rybafish/rybafish/releases/download/091betaIV/RybaFish_MacOS_091betaIV.zip) now available, runs on Intel/ARM.
* Alt+Up/Down - to move highlighted point between KPIs. ~~Only regular KPIs supported for now~~ Regular+Multiline KPIs supported.
* and Gantt as well
* beta versions will be checking for newly published betas, can be controlled by [updatesCheckBeta](/config#updatesCheckBeta): True/False.
* SQL console syntax highlighter performance boost approx. 2 times
* Configurable connectionsFile, screensFolder, customKPIsFolder, contextSQLsFolder [settings](/config#customKPIsFolder).
* simple [SQL scripts organizer](/sqlconsole#sqlbrowser), menu->SQL or F11
* SQL Console toolbar
* finally, documentation on [sql console](/sqlconsole)

[<b>091 beta III</b>](https://github.com/rybafish/rybafish/releases/download/091betaIII/RybaFish_091betaIII.7z) (2022-05-29)
* "McAfee Endpoint Security Alert" RybaFish detected as a malware for no reason, beta III should fix this issue.

[<b>091 beta II</b>](https://github.com/rybafish/rybafish/releases/download/091betaII/RybaFish_091betaII.7z) (2022-05-06)
* Alt+N to switch tabs
* multiline KPIs have 'others' property: single entry to include everything else
* profiler to track expensive calls, useProfiler: True.

[<b>091 beta I</b>](https://github.com/rybafish/rybafish/releases/download/beta/RybaFish_091betaI.7z) (2022-04-24)
* [variables](variables) support
* simple connections manager, save encrypted passwords
* DB interface introduced: can implement alternative connection protocols now
* automatic updates checker, set updatesCheckInterval: 0 to disable
* Screen DPI awareness (DPIAwareness: False to disable)

# Previous Release
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
