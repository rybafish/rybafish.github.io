## TODO
### Short Term
* configurable KPI units of measure (for network, disks, etc.)
* Fix per sample metrics to consider sample rates
* Automate metrics scaling based on sample unit/display unit 
* Major Output/Logs cleanup
* Save the interface layout (including selected KPIs?) feature
* "Save the connection details" option

## Long Term
* Custom KPIs
* simple SQL console
* Single-point event markers (star, round, arrow, etc)
* resurrect import of nameserver trc files functionality (it existed before public release).
* Asynchronous network calls
* "copy image" option (or export as png)
* MacOS and Linux builds (help needed!)
* Codeclean-up and refactoring
* verify getHostKpis performance (type cast check)
* check type cast/kpi value issues (probably will crash whole app)
* make "Ignore exception" option?
* verify drawing speed + check scrolling/drawing issues
* standardize time scales (1 minute, 10 minutes etc)

## Changelog
#### 0.4 beta (01.09.2019)
* now full support of sample unit / display unit and "per sample" kpis (like Network In/Out)
* now zoom with ctrl+mouse scroll 
* can check for the last version in "About"
* some crashes fixed

#### 0.3 beta (12.08.2019)
* Auto Refresh Feature
* Y-Scale grid
* Fixed some bugs exceptions
  + Major Reconnect Clean Up
  + Old Revisions support (with no KPI style definitions, <= ~1.00.122.18)

#### 0.2 beta (2019-07-25)
* All KPI metrics available now, based on m_load_history_info
* Proper connection errors handling, reconnect functionality
* Connection dialog saves last connection details
* Clean up of reconnect procedure
* Single click triggers chart redraw, without data refresh
* Copy current timestamp feature: right mouse click on chart
* Configurable keep-alive requests: keepalive option in config.yaml in seconds
* Fixed some exceptions (bogus date format, etc)

#### 01. alpha (2019-07-15)
* Initial release
