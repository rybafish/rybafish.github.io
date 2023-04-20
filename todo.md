## TODO
### In progress
* Linux build
* SQLite support (available in 093 beta 0)
* CSV import (available in 093 beta 0)

### Short Term
* extract server processing time for sql console executions (pyhdb mod)
* proper ddl/commits handling in sql console (partialy done)
* ~~SSL support,~~ 092betaI (2022-10-02)

## Long Term
* Logs cleanup
* Slack notifications
* ~~MacOS build~~ - done in 091 betas
* Linux build (we almost there)
* ~~"Save the connection details" option~~ done in 091 betas
* ~~Save the encripted passwords~~ - done in 091 betas
* Single-point event markers (star, round, arrow, etc)
* Asynchronous network calls for charts

## Changelog

This is outdated changelog, check the new one on [/changelog](/changelog).

#### 0.9 Sig (17.07.2021)
* ssl support (091)
* change KPI color UI
* macOS build
* Linux build (on request)
* SQL scripts organizer
* connections manager
* screen DPI awareness

#### 0.8 Plotva (17.07.2021)
* switch to statistis server telemetry feature (ess)
* result set autorefresh feature (experimental)
* major upgrade of the python/qt technology stack
* minor interface improvements here and there

#### 0.7 poehali GL (12.04.2021)
* full gas sql console support, give it a try! <-
* resurrected import of nameserver_history.trc
* layout feature: same sql tabs open after the restart

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
* Copy current timestamp feature: right mouse click on the chart
* Configurable keep-alive requests: keepalive option in config.yaml
* Fixed some exceptions (bogus date format, etc)

#### 01. alpha (2019-07-15)
* Initial release

#### 00. initial (2019-05-02)
* The first code line put to test if Qt will be any good for charts.
