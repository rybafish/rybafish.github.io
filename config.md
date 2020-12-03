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

#### keepalive
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
