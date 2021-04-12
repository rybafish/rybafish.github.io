## TODO
### Short Term
* Save the interface layout (including selected KPIs?) feature: done in v0.7
* Save unsaved changes in SQL consoles (Notepad++ like behaviour): done in v0.7
* LONGDATE support - to enable microseconds in SQL Console: done in v0.7
* extended procedures suppurt: done in v0.7

## Long Term
* Major Output/Logs cleanup
* MacOS and Linux builds (help needed!)
* "Save the connection details" option
* Save the encripted passwords
* Single-point event markers (star, round, arrow, etc)
* resurrect import of the nameserver_history.trc files: done in 0.7.
* Asynchronous network calls for charts
* server processing time support for sql console

## Changelog
#### 0.7 poehali GL (12.04.2021)
* full sql console support
* resurrected import of nameserver_history.trc
* layout feature: same sql tabs open after restart

#### 0.6 EVH (10.10.2020)
* [gantt KPIs](/customKPIgantt) type support
* chart legend now available
* minor improvements and fixes

#### 0.5 poehali (12.04.2020)
* sql console (experimental mode only)
* custom KPIs available as standard feature
* bug and crash fixes
* minor interface improvements

#### 0.45 (23.09.2019)
* built-in screenshot feature
* chart performance improvements
* custom KPIs support (experimental mode)

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

#### 00. initial (2019-05-02)
* First code line put to test if Qt will be any good for charts.
