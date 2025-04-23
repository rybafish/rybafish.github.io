---
title: Changelog
---

Links for most recent macOS builds available [here](https://github.com/rybafish/rybafish/issues/771).

# Upcoming build
* linux, macOS builds for 096
* alt+click in SQL console result set will highlight the row
* ctrl+alt+click in SQL console result set will highlight value
* ctrl+shift+click in SQL console result set will highlight changes
* you can change order of selected KPIs: right mouse click in KPIs table or Alt+Up/Down
* option to temporary hide KPIs from chart, migh be useful to make clean screenshot, RMC on chart. Multiline supported.
* alt+click on result set column header to instant hide it (width -> 0)
* [legendGanttDetails](/config#legendGanttDetails) setting to report gantt KPI stats on legend

 True rybafish junkies can try rybafish [nightly build](https://files.rybafish.net/keira/rybafish_knightly.7z) (<span style="color:blue">executable only</span>)

# 096 beta III
[<b>096 beta III</b>](https://github.com/rybafish/rybafish/releases/download/096biii/RybaFish_096betaIII.7z) (2024-04-27)
* initial password reset support
* password change dialog added (file menu)
* file save dialog fix

# 096 beta II
[<b>096 beta II</b>](https://github.com/rybafish/rybafish/releases/download/096bii/RybaFish_096betaII.7z) (2024-03-13)
* KPIs presets: menu Layout -> Presets
* in-line filtering in KPIs table: just start typing, ESC to reset
* trimming spaces during import feature
* m_load_history* tables structure validation during connection to SQLite DBs
* Ctrl+Shift+L to hide/show gantt labels
* sql console toolbar button: sound notification on SQL termination
* [manual_color](/customKPIgantt#manual_color) feature for Gantt charts
* **Cloud/BTP connections support** (Temporary experimental)

# 096 beta I
[<b>096 beta I</b>](https://github.com/rybafish/rybafish/releases/download/096bi/RybaFish_096betaI.7z) (2023-12-12)
* advanced [highlighter](/highlight) (experimental)
* databar feature: right-mouse click in ressult set column with numbers
* fix of [scriptsFolder](/config#scriptsFolder) setting bug
* ctrl+mouse wheel to increase/decrease font in SQL consoles and resultsets
* to_date('') --> exception instead NULL, pyhdb bug fix.
* server processing time for SQL consoles
* time scale 8 and 12 hours, experimental
* ess legend crash fix
* **warning:** daylight saving fix (?), set [serverTZ](/config#servertz): False to revert
* [reconnectTimer](/config#reconnectTimer) setting

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
093 beta III (2023-07-02)
* updated delta merges KPI from [this](https://youtu.be/BCVW2asUgqk) tutorial
* stack upgrade (3.10 -> 3.11)

# 093 beta II
093 beta II (2023-05-18)
* new log file, automatic log truncation, [logSizeMax](/config#logSizeMax)
* multiple [variables](/variables) bugfixes

# 093 beta I
093 beta I (2023-04-12)
* async multiline mode
* Timezones management, [link](/timezones)
* trace import fix: data might be loaded just partially in some cases

# 093 beta 0

093 beta 0 (2023-02-16)

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

091 beta IV (2022-06-30)
* [macOS](https://github.com/rybafish/rybafish/releases/download/091betaIV/RybaFish_MacOS_091betaIV.zip) now available, runs on Intel/ARM.
* Alt+Up/Down - to move highlighted point between KPIs. ~~Only regular KPIs supported for now~~ Regular+Multiline KPIs supported.
* and Gantt as well
* beta versions will be checking for newly published betas, can be controlled by [updatesCheckBeta](/config#updatesCheckBeta): True/False.
* SQL console syntax highlighter performance boost approx. 2 times
* Configurable connectionsFile, screensFolder, customKPIsFolder, contextSQLsFolder [settings](/config#customKPIsFolder).
* simple [SQL scripts organizer](/sqlconsole#sqlbrowser), menu->SQL or F11
* SQL Console toolbar
* finally, documentation on [sql console](/sqlconsole)

091 beta III (2022-05-29)
* "McAfee Endpoint Security Alert" RybaFish detected as a malware for no reason, beta III should fix this issue.

091 beta II (2022-05-06)
* Alt+N to switch tabs
* multiline KPIs have 'others' property: single entry to include everything else
* profiler to track expensive calls, useProfiler: True.

091 beta I (2022-04-24)
* [variables](variables) support
* simple connections manager, save encrypted passwords
* DB interface introduced: can implement alternative connection protocols now
* automatic updates checker, set updatesCheckInterval: 0 to disable
* Screen DPI awareness (DPIAwareness: False to disable)

# Previous Release
[<b>0.9 Paltus</b>](https://github.com/rybafish/rybafish/releases/download/09paltus/RybaFish_09Paltus.7z) (2022-02-17)

## Paltus Changelog

0.9 beta XI (2022-01-26)
* legendTenantName and legendServiceName configuration options
* explain plan for sql plan cache entry now works in console
* manual scales in KPIs table are blue. If you post an empty value manual scale --> autoscale itself!
* gantt render performance **boost**: can be disabled by ganttOldImplementation: True
* gantt gradient feature: in KPI definitin gradient: True + gradientTo: '#F88' ([details](/customKPIgantt)),
* config option _chartWidth_ for cases when the default 1 is not thick enough.
* it is possible now to set Y range other than from 0 to something. To achieve this put, for example, 2000-5000 in Y-Scale.

0.9 beta 9 (2021-12-23) 
* bugfix affecting multiple resultsets
* last available beta is now reported in the About dialog

9 beta 8 (2021-12-21), <span style="color:blue">withdrawn</span>.
* [gantt](/customKPIgantt) bars can have titles: little text labels right inside the bar
* there is no 32k limit anymore (bug [#181](https://github.com/rybafish/rybafish/issues/181))

0.9 beta 7 (2021-11-24)
* avg value is now reported in KPIs table
* basic [alerting](/soundAlerts) functionality
* hosts table enriched with service name and tenant information
* numerous bugfixes…

0.9 beta 5 (2021-09-30), <span style="color:blue">withdrawn</span>.
* ABAP-style results copy: right mouse click in results
* Colorize KPIs option: Actions menu -> Colorize
* sql console parser fix: first statement was not recognized correctly in beta4.
* tenant name and revision reported in the window title

0.9 beta 4 (2021-09-14), <span style="color:blue">withdrawn</span>.
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

0.9 beta (2021-08-15)
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
