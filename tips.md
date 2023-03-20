---
title: RybaFish Tips and ticks
---

## Tips and Tricks

* Did you know? You can switch tabs by clicking on indicators (right bottom corner of the window).
* since 091 beta II it's possible to switch tabs by Alt+1, Alt+2...
* by the way, there is a [documentation](/doc) chapter, currently mostly the SQL console covered

### Charts
* Ctrl + mouse wheel makes zoom-in/zoom-out while in chart area
* F5 and Ctrl+R triggers reload request
* You can use relative number in hours instead of timestamp in "from:" field, example : "-12" to keep just last twelve hours
* Pressing the Enter key while in "from:" or "to:" fields will submit reload request with the new time
* Alt+click in KPIs table will enable the KPI but will not perform request: useful to select several KPIs and do single request
* Ctrl+click in KPIs table requst this kpi for the same service (same port) from all nodes
* Ctrl+Shift in KPIs table request this kpi from all nodes, all services
* Click on the chart line will highlight it and display the exact time and value
   * You can move highlighted point with Alt+Left/Right, (v09)
   * Alt+Up/Down to switch to neighbour KPI (v091)
* Second click on the same chart line calculates the delta between values: check the status bar
* Sinle click on the chart area will redraw the chart without refresh
* Pay attention to status bar, all requests that are expected to be long (network) put some message in the status bar
* Shift + mouse wheel scrolls the area
* You can use just date in 2020-12-28 format to get 2020-12-28 00:00:00
* When you put date like 2020-12-28 in "to" field - you will get  2020-12-28 23:59:59
* When a gantt or multiline KPI selected, context menu allows to copy details of the selected KPI
* Right mouse click in the chart area shows some potentiously useful options, try it!
  * for example you can copy the exact timestamp in sql ready format
  * even more: if yo already have timestamp in the clipboard you can compse beween predicate (v09)
* using right mouse click in the KPIs table you can adjust the KPIs color
 

### SQL Console

* when you start statement as "select top NNN" result limit will be automaticaly adjusted for this execution, no configuration change requred
* ctrl+up/ctrl+down moves current line
* ctrl+d duplicates current line or selection
* ctrl+u lowercases the string
* there is .log file containing some additional details which may be useful in certain cases. Also crash callstacks stored there.
* f12 switches the console/result/log scales. When repeated - returns the previous layout: useful for managing long statements.
* Shift + mouse wheel scrolls the result set table horizontally
* Ctrl + space calls autocomplete dialog (to be released with v09)
  * typing  in autocomplete dialog will filter values
* ctrl+F shows basic search dialog
  * F3 repeats the last search (to be released with v09)
* when the column resized to 0 width it will be skipped in result copy (v09)
* with 091 beta IV there is a SQL Browser available, give it a try! Menu -> SQL (F11)
