Starting 09 beta 2 RybaFish supports "variables" in custom KPIs.

Variables are placeholders that will be replaced by the actual values before actual usage. Variables defined in the custom KPI yaml file, for example:

`
variables: 'y1: 10, y2: 50, threshold: 30, user: %'
`

All variables listed in a single string in JSON-like format. This particular line defines four variables: y1, y2, threshhold and user.

Variables can be used in the **same** file for dynamic values substitution. Usage example:

```
...

description: 'Expensive Statements > $threshold s'}
```

When used in the KPI definition variables must be prefixed with $ character. Considering the definition above, actual usage will be translated to:
```
...

description: 'Expensive Statements > 30 s'}
```

Currently only following KPI definition areas considered:

* kpis.y_range
* kpis.label
* kpis.description
* sql
