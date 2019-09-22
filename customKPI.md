## Custom KPIs
Since v05 Ryba Fish Charts supports custom kpis metrics.

This means you can define custom SQL statement providing time, host, optionally service port and some numeric values do be displayed on the chart along with  the standard ones. For instance you can extract additional data from statistics service tables to display.

Such needs to be described with some KPI details like units of measure, color, name, etc. Let's see an example:

sql/01_service_memory.yaml
```
kpis: [
    {type: 'service',
        name: 'mem_used',
        group: 'mem',
        sUnit: 'Byte',
        dUnit: 'MB',
        sqlname: 'total_memory_used_size',
        color: '#0D0',
        label: 'Used Service Memory',
        description: 'Used Service Memory'},
    {type: 'service',
        name: 'mem_eol',
        group: 'mem',
        sUnit: 'Byte',
        dUnit: 'MB',
        sqlname: 'effective_allocation_limit',
        color: '#080',
        label: 'Service Allocation Limit',
        description: 'Service Allocation Limit'
    }
    ]

sql: >
    select 
        server_timestamp time,
        host, 
        port, 
        total_memory_used_size, 
        effective_allocation_limit
    from _sys_statistics.host_service_memory
```
## YAML file structure
### type
Can only have one of two values: 'service' or 'host'
When sql provides service-level metric - port must be one of the returned columns.

### name
KPI internal name: it will be used internally by the ryba fish, must be unique.

### group
KPI Group used for Y-Scale. Useful pre-defined values are mem for all memory metrics, thr - for threads. Zero means no grouping used.

### sUnit/dUnit
Sample unit and display unit. The only pre-defined values are Bytes/MB usually used for memory metrics.

### sqlname
Name of the corresponding column in sql statement.

### color
KPI style color in form of #RGB. #F00 - red, #0FF - cyan, etc.

### style
By default all kpis are solid lines. Style options are: solid, dashed, dotted, dotline.

### label
KPI Name in KPI table

### description
Free form KPI description for the KPI table
