# Custom KPIs with gantt subtype
Since v 0.52 RybaFish Charts supports custom KPI metrics with subtype gantt.

This means if there is a process with the start and stop times - it can be displayed. For example (expensiv)e statements, delta merges, etc. Can also be business specific if the sql available: data load times, transformation stages, whatever.

file: sql/gantt/01_exp_st.yaml
```
kpis: [
    {'type': 'service',
        subtype: 'gantt',
        name: 'exp_st',
        sqlname: 'none',
        color: '#ACF',
        style: 'bar',
        width: 8
        shift: 2
        y_range: [60, 100],
        label: 'Expensive Statements',
        description: 'Expensive Statements'}
    ]

sql: >
    select top 250
    host,
    port,
    start,
    stop,
    entity,
    'mem, gb:' || to_varchar(used_memory/1024/1024/1024) details
    from
    m_expensive_statements
    order by start desc
```

Gantt KPIs defined one per yaml file.

## YAML file structure
### kpis
Mandatory field with list of KPI descriptions. In case of gantt - just one KPI allowed.

### type
Can only have one of two values: 'service' or 'host'.
When sql provides service-level metric - port must be one of the returned columns. 

### subtype
Must be 'gantt', no other subtypes available yet.

### name
KPI name: will be used internally, must be unique.

### color
KPI style color in form of #RGB. #F00 - red, #0FF - cyan, etc.

### style
There are two styles available: bar and candle.

### width
Bar width.

### shift
Y-shift in case of overlapping events for the same entity.

### y_range
Pair of values defining the Y range (percentage) for the chart to be drawn, useful in case of several gantt charts.

### label
KPI Name in KPI table.

### description
Free form KPI description for the KPI table.

### sql
SQL statement providing host, START, STOP, entity and description. Note: according to YAML formatting rules the sql statement has to start with '>' character and must be idented.

START and STOP columns are timestamp format.

entitiy: this column will be used to group events.

description: any additional information to be displayed when the entry is clicked on.
