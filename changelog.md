# Upcoming Release
0.9, planned date: October 2021

* ABAP-style results copy (right mouse click in results)

[<b>0.9 beta 4</b>](https://github.com/rybafish/rybafish/releases/download/09beta4/RybaFish_09beta4.7z) (2021-09-14)
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
