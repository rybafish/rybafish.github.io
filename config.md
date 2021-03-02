Note: for custom KPIs documentation go to the [customKPI](customKPI) page.

## Configuration options description

### Main Stuff

#### fontSize
`fontSize: 8`

Integer. Font size for the chart labels.

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

#### saveLayout (v 0.7)
`saveLayout: True`

Saves the window layout: position, size, etc. Information saved in layout.yaml - delete it in case of problems.

#### saveKPIs (v 0.7)
`saveKPIs: True`

Saves enabled KPIs. KPIs saved per host/port pair. Information saved in layout.yaml - delete it in case of problems.
This feature requres saveLayout to be enabled.

### saveOpenTabs (v 0.7)
`saveOpenTabs: True`

When enabled - open consoles will be re-opened after the restart, even if not saved. Backups will be saved in "bkp" folder.
This feature requres saveLayout to be enabled.

#### loglevel
`loglevel: 3`

Log level, maximum is 5 it will dump every executed SQL statement

#### legendTimeScale
`legendTimeScale: False`

Controls the time scale hint on the chart legend. Set it to False to disable, enabled by default, available in v.07

#### experimental
`experimental: True`

Boolean. Enables experimental functionality.

### Experimental stuff
#### fontScale
`fontScale: 1.25`

Decimal. Default scaling factor for the "Adjust Fonts" action.

### SQL Console related (experimental mode only, v.51 requred)
#### console-fontSize
`console-fontSize: 10`

Console editor font scale

#### highlightLOBs
`highlightLOBs: True`

Sets light gray backgtound for LOB fields just to be aware

#### keepalive-cons
`keepalive-cons: 1800`

Enables sql console to send keep alive dummy queries to avoid disconnection due to inactivity.

`lowercase-columns: False`

Lowercase column names when possible. We seriously think about the environment, lets save some ink when possible. Uppercase is bad for environment.

#### maxResultSize
`resultSize: 1000`

Number of rows fetched for the result set

#### nullString
`nullString: '?'`

SQL NULL value representation for table output

#### nullStringCSV
`nullStringCSV: ''`

SQL NULL value representation for CSV or Copy

#### noWordHighlighting
`noWordHighlighting: True`

Set this to True to disable word highlighting. By default words are highlighted on selection.

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
        
The feature changes default colours to semi-random list of colors. Potentially useful to distinguish same KPI for different nodes in scale-out env. When this option is enabled colours will be extracted one by one from the list in this order. In order to have consistent colours for the same KPIs you will need to enable KPIs in the same order.

### detachTimeout
`detachTimeout: 300`

Timeout for detaching resultsets containing LOB values. Default value is 300 seconds.
