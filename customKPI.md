# Custom KPIs
Since v 0.45 Ryba Fish Charts supports custom KPI metrics.

Since v 0.6 [gantt KPIs](/customKPIgantt) suported.

**Currently the feature is only available when the experimental mode is enabled: check your config.yaml file**

This means you can define custom SQL statement providing time, host, optionally service port and some numeric values do be displayed on the chart along with the standard ones. For instance you can extract additional data from statistics service tables to display.

Such statement needs to be defined with some additional KPI details like units of measure, color, name, etc. Let's see an example for memory information based on host_service_memory statistics service table:

file: sql/01_service_memory.yaml
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

YAML files with custom KPI definitions must be stored in sql folder. When sub-folders created corresponding KPI groups will be created in KPIs table.

One YAML file can have several custom KPIs but all coming from the same sql statement. All KPIs have to have the same type (host or service, see below).

## YAML file structure
### kpis
Mandatory field with list of KPI descriptions.

### type
Can only have one of two values: 'service' or 'host'.
When sql provides service-level metric - port must be one of the returned columns. 

### name
KPI internal name: it will be used internally by the ryba fish, must be unique.

### group
KPI Group used for Y-Scale. Useful pre-defined values are mem for all memory metrics, thr - for threads. Zero means no grouping used.

### sUnit/dUnit
Sample unit and display unit. The only pre-defined values are Bytes/MB usually used for memory metrics. See examples in m_load_history_info.

### sqlname
Name of the corresponding column in sql statement.

### color
KPI style color in form of #RGB. #F00 - red, #0FF - cyan, etc.

### style
By default all kpis displayed using solid lines. Available style options are: solid, dashed, dotted, dotline.

### label
KPI Name in KPI table.

### description
Free form KPI description for the KPI table.

### sql
SQL statement providing host, time optionally port and one or more integer kpi values. The time column has to have timestamp sql type. 

Note: according to YAML formatting rules the sql statement has to start with '>' character and must be idented. Only spaces allowed as indentation character, do not use \t to avoid yaml parsing issues.
