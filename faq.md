### Why the chart jumps to the end of the period?
### Why such colours selected, can I change them?
### Why same KPIs have same colour for the different tenants/hosts?
### Where the data coming from?
### Why some KPIs has fraction and some dont?
Everything is actually an integer in m_load_history_ views but some values are recalculated for the display ('normalized'). If reclaculated maximum is < 10 - wa save the decimal point. It is also shall be possible to enforce decimal point for some metrics, but not yet.
