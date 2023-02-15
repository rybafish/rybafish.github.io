Single KPI selected in the example below:

![demo screen](http://rybafish.github.io/multilineKPI.png)

The "component" column used to split values into several lines on the chart.
It is not really docummented, but come on, it is quite straight-forward.

There is a separate page documenting [variables](/variables).

```
kpis: [
    {type: 'service',
        subtype: 'multiline',
        name: 'allocator',
        group: 'mem',
        sUnit: 'Byte',
        dUnit: 'MB',
        color: '#084',
        multicolor: True,
        stacked: True,
        sqlname: 'component_size',
        splitby: 'component',
        orderby: 'max',
        desc: True,
        legendCount: 6,
        others: False,
        label: 'Component Memory Used',
        description: 'Component Memory Used'}
]

sql: >
    select
        server_timestamp time,
        host,
        port,
        component,
        sum(exclusive_size_in_use) component_size
    from _sys_statistics.host_heap_allocators
    group by
        host,
        port,
        server_timestamp,
        component
    order by server_timestamp desc, component_size desc
```
### others
When True - all the rest data will be summed into a single line named "Others".

Possible orderby values: "avg", "max", "deviation" and "name".
