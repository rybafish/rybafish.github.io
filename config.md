Note: for custom KPIs documentation go to the [customKPI](customKPI) page.

## Configuration options description

### Main Stuff

#### fontSize
`fontSize: 8`

Integer. Font size for the chart labels.

#### DPIAwareness (since 091 beta I)
`DPIAwareness: True`

Scale graphics and fonts according to system display settings. Enabled by default.

#### locale
`locale: 'fr_FR'`

By default system locale used for number formatting: decimal and thousands separators. This can be changed by enforsing different locale. Examples: en_US, fr_FR, etc.

#### color-bg
`color-bg: '#FFF'`

Changes the chart background to the specified value. Useful for dark XP-like color schemes.

#### memoryGB
`memoryGB: True`

Boolean. Force memory KPIs to be displayed in GB instead of default MB.

#### keepalive
`keepalive: 1200`

Enables chart to send keep alive dummy queries to avoid disconnection due to inactivity.

#### saveLayout
`saveLayout: True`

Saves the window layout: position, size, etc. Information saved in layout.yaml - delete it in case of problems.

#### saveKPIs
`saveKPIs: True`

Saves enabled KPIs. KPIs saved per host/port pair. Information saved in layout.yaml - delete it in case of problems.
This feature requres saveLayout to be enabled.

### saveOpenTabs
`saveOpenTabs: True`

When enabled - open consoles will be re-opened after the restart, even if not saved. Backups will be saved in "bkp" folder.
This feature requres saveLayout to be enabled.

#### loglevel
`loglevel: 3`

Log level, maximum is 5 it will dump every executed SQL statement

#### legendTimeScale
`legendTimeScale: False`

Controls the time scale hint on the chart legend. Set it to False to disable, enabled by default, available in v.07

#### legendTenantName, legendServiceName
`legendTenantName: False`
`legendServiceName: False`

Enables legend to include service name and tenant name, useful in multi-tenant monitoring from SystemDB. Disabled by default, available since v09

#### skipTenant (v0.9)
`skipTenant: True`

Skip the tenant name check for the initial connection. Usually not requred as this is very quick and works even on old non-MDC installations.

#### ganttOldImplementation (v 0.9)
`ganttOldImplementation: True`
Boolean. Eenable to switch to old gantt render algorithm (potentially slow, see .log file for measurements)

#### autorefreshThreshold (v 0.9)
`autorefreshThreshold: 30`
Integer threshold in seconds. If refresh takes longer than this value - autorefresh will be disabled. Default is 0 (no threshold).

#### chartWidth (v 0.9)
`chartWidth: 2`
Chart line width. In most of the cases the default (1) is fine, but sometimes (for example when colorize enabled) value 2 makes chart more readable.

#### experimental
`experimental: True`

Boolean. Enables experimental functionality.

#### fontScale
`fontScale: 1.25`

Decimal. Default scaling factor for the "Adjust Fonts" action.

### SQL Console related
#### console-fontSize
`console-fontSize: 10`

Console editor font scale

#### highlightLOBs
`highlightLOBs: True`

Sets light gray backgtound for LOB fields just to be aware

#### keepalive-cons
`keepalive-cons: 1800`

Enables sql console to send keep alive dummy queries to avoid disconnection due to inactivity.

<a name="lowercasecolumns" />

#### lowercase-columns
`lowercase-columns: False`

Lowercase column names when possible. We seriously think about the environment, lets save some ink when we can, uppercase is bad for environment.

#### maxResultSize
`resultSize: 1000`

Number of rows fetched for the result set

#### nullString
`nullString: '?'`

SQL NULL value representation for table output

#### nullStringCSV
`nullStringCSV: ''`

SQL NULL value representation for CSV or Copy

#### noWordHighlighting, noBracketsHighlighting
`noWordHighlighting: True`
`noBracketsHighlighting: True`

Set this to True to disable words/brackets highlighting. By default words are highlighted on selection.

#### longdate
`longdate: True`

Enables data_format_version2: extended data types including longdate - timestamps with microsecond precision.

#### raduga
```
raduga: ['#20b2aa', '#32cd32', '#7f007f', '#ff0000', '#ff8c00', '#7fff00', '#00fa9a', '#8a2be2', 
        '#dc143c', '#0000ff', '#da70d6', '#d8bfd8', '#ff00ff', '#1e90ff', '#db7093', '#ffff54', 
        '#ff1493', '#7b68ee', '#ffa07a', '#008000', '#3cb371', '#b8860b', '#4682b4', '#000080', 
        '#9acd32', '#afeeee', '#7fffd4', '#ffdead', '#2f4f4f', '#556b2f', '#a0522d', '#483d8b']
```
        
This list defines colors to be used with colorize option (see below).

#### colorize (v 0.9)
`colorize: False`

Use colors defined by "raduga" list instead of standard ones. Same can be achieved by menu Actions -> Colorize KPIs.

Potentially useful to distinguish same KPI for different nodes in scale-out env. When this option is enabled colours will be extracted one by one from the list in this order. In order to have consistent colours for the same KPIs you will need to enable KPIs in the same order.

### detachTimeout
`detachTimeout: 300`

Timeout for detaching resultsets containing LOB values. Default value is 300 seconds.

<a name="blockLineNumbers" />
### blockLineNumbers (v 0.9)
`blockLineNumbers: True`

In case of DB exceptions, like syntax errors, HANA will report the line number of the error. This line number is inside the execured SQL string and not line number of the console. With this option enabled the console line numbers will only be displayed for the highlighted SQL string, so the reported DB error string should correspond to the displayed line numbers. Can be disabled by setting it to False.

### updatesCheckInterval (v 0.91)
`updatesCheckInterval: 7`

Updates will be checked every 7 days (default). You can set it to 0 in order to disable check of updates.

<a name="updatesCheckBeta" />
### updatesCheckBeta: True
`updatesCheckBeta: True`

By default only major releases will be checked. You can set this parameter to True to also be notified about beta releases. Check period controlled by updatesCheckInterval.

### abap-length (v 0.91)
`abap-length: 32`

Number of characters limiting value length for ABAP style copy. The default value is 32.

### abap-length (v 0.91)
`copy-markdown: False`

You can set copy-markdown to False to switch to pure ascii table formatting instead of markdown.

### connectionsFile (v 0.91)
`connectionsFile: 'C:\Users\somepath\connections.yaml'`

Optional path to credentials/connections file. The setting might be useful when several RybaFish instances used on the same machine. The default behaviour is to have separate connections.yaml per RybaFish instance (copy).

### screensFolder (v 0.91)
`screensFolder: 'C:\Users\somepath\screens'`

Optional path for to save screenshots. Might be useful when several instances of RybaFish Charts used.

<a name="customKPIsFolder" />
### customKPIsFolder (v 0.91)
`customKPIsFolder: 'C:\Users\somepath\sql'`

Optional path to custom KPIs folder. Might be useful when several instances of RybaFish Charts used.

### contextSQLsFolder (v 0.91)
`contextSQLsFolder: 'C:\Users\somepath\ContextSQLs'`

Optional path to context SQLs folder. Might be useful when several instances of RybaFish Charts used.

<a name="scriptsFolder" />
### scriptsFolder (v 0.91)
`scriptsFolder: 'C:\Users\somepath\scripts'`

Optional path to sql scripts folder, thde default is local 'scripts'. Used in [SQL Browser](/sqlconsole#sqlbrowser): menu -> SQL or F11.

<a name="sqlConsoleToolbar" />
### sqlConsoleToolbar (v 0.91)
`sqlConsoleToolbar: True`

You can change it to False in config to manualy disable it. Similar can be acheive by menu -> Actions -> SQL Console Toolbar.

### threadSafeLogging (v 0.91)
`threadSafeLogging: False`

In case you observe slow-downs or freezing duging loggings, try to disable this parameter (False) to avoid mutex usage during logging. The default is True - this should make logging thread safe (only since 0.91 beta 5)


### import_timezone_offset (v 0.91)
`import_timezone_offset: 7200`  # CET summer time

By default import of nameserver_history.trc file will display data in you local time zone. In most cases it is much more useful to have data in system time zone, this is where this parameter can help: it needs to be set in seconds as offset from the UTC. To get this value from  the source system you can execute: `select distinct key, value from m_host_information where key in ('timezone_offset')`. It is delta in seconds from UTC.

Note: 0 and no value has very different meaning in this context: no value = your local timezone, 0 = UTC.
