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

#### keepalive
`keepalive: 1200`

Enables chart to send keep alive dummy queries to avoid disconnection due to inactivity.

#### keepalive
`keepalive-cons: 1800`

Enables sql console to send keep alive dummy queries to avoid disconnection due to inactivity.

#### experimental
`experimental: True`

Boolean. Enables experimental functionality.

### Experimental stuff
#### memoryGB
`memoryGB: True`

Boolean. Force memory KPIs to be displayed in GB instead of default MB.

#### fontScale
`fontScale: 1.25`

Decimal. Default scaling factor for the "Adjust Fonts" action.

### SQL Console related (also experimental, v.05 requred, not released yet)
#### maxResultSize
`resultSize: 1000`

Number of rows fetched for the result set

#### nullString
`nullString: '?'`

SQL NULL value representation for table output

#### nullStringCSV
`nullStringCSV: ''`

SQL NULL value representation for CSV or Copy
