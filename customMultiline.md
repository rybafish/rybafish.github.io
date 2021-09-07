Not really docummented, but come on, it os obious:

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
