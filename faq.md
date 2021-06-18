## Chart
### Why such colours selected, can I change them?
Colors and line styles provided by the database. It is not possible to change them, at least for now.

### Why same KPIs have same colour for the different tenants/hosts?
First, see the previous question. Second, it is actually a good thing: CPU is always red and memory is always green.

### Where the data coming from?
m_load_history_service and m_load_history_host system views.
Since v0.8 it is possible to switch to _sys_statistics.host... views which cover 42 days.

### Why some KPIs has fraction and some don't?
Everything is actually an integer in m_load_history... but some values are recalculated for the display ('normalized'). If reclaculated maximum is < 10 - RybaFish puts the decimal point on it. 

### Why the chart jumps to the end of the period?
If "to:" is empty,  the most recent data selected and displayed. If you want to avoid chart re-positioning - just put some date as the end of the period and position will not change on refresh.

## SQL Console

### How the statement execution time measured?
It is client-side measurement. Therefore it includes: prepare, execute and fetch. Highly depends on the network and the result size.

### Is it possible to enable auto-commit?
At the moment - no. You need to do explicit "commit" if you need to persist your changes.

### What status bar indicator colors mean?
* Gray - connecred, waiting.
* Blue - synchronous call is running: usually connection or keep-alive execution.
* Green - asynchronous call is running. You can click on the indicator to see current runtime.
* White - rendering the result.
* Red - error or disconnected.
