### Why such colours selected, can I change them?
Colurs and line styles provided by the database. It is not possible to change them at least for now.

### Why same KPIs have same colour for the different tenants/hosts?
This approach has a long tradidion, it was alsways like this in HANA Studio. But this is a good thing: CPU us always red and memory is always green.

### Where the data coming from?
m_load_history_service and m_load_history_host monitors.

### Why some KPIs has fraction and some dont?
Everything is actually an integer in m_load_history... views but some values are recalculated for the display ('normalized'). If reclaculated maximum is < 10 - we put the decimal point. It is also shall be possible to enforce decimal point for some metrics, but not yet.

### Why the chart jumps to the end of the period?
If the end of period is empty,  the most recent data selected. If you want to avoid this just put some date as the end of the period and position will not change on refresh.

