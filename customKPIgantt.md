# Custom KPIs with gantt subtype
Since v 0.52 Ryba Fish Charts supports custom KPI metrics with subtype gantt.

This means if there is some process with the start and end times - in can be displayed. For example expensive statements, delta merges, etc.

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

### type
Must be 'gantt', no other subtypes available yet.

### name
KPI internal name: it will be used internally by the ryba fish, must be unique.

### color
KPI style color in form of #RGB. #F00 - red, #0FF - cyan, etc.

### style
There are two styles available: bar and candle.

### width
Bar width.

### label
KPI Name in KPI table.

### description
Free form KPI description for the KPI table.

### sql
SQL statement providing host, START, STOP, entity and description. Note: according to YAML formatting rules the sql statement has to start with '>' character and must be idented.

START and STOP columns are timestamp formats.

entitiy: this column will be used to group processes.

description: any additional information to be displayed when the entry is clicked on.
