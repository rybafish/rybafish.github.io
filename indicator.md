# Indicators
Rybafish statusbar (most bottom line of the application window) has so-called indicators. Each indicator corresponds to the RybaFish tab:

![Indicators](https://www.rybafish.net/img/ind_00_example.png)

In this case two tabs are open. Those indicators reflect status of RybaFish tabs: chart and SQL consoles.

By the way by clicking on the indicator itself you can change the active tab.

This reference (soon will be) describing available statuses and their meaning.

### idle
![Idle](https://www.rybafish.net/img/ind_01_idle.png)

The console is connected and doing nothing.

### sync
![Sync](https://www.rybafish.net/img/ind_02_sync.png)

The console is doing some king of sync-reauest. This means whole application UI is locked until the request finishes. In most cases you will see this one for the first tab (charts) because chart calls are 100% synchronous.

SQL consoles do most of database requests in synchronous mode with some exceptions. For instance, keep-alive requests sent in synchronous mode because normally they are very fast and you will not notice them if the connection is fine.

### running
![Running](https://www.rybafish.net/img/ind_03_running.png)

This one set by SQL consoles during database request: database execution and results transfer to client do not block application.

### error
![Error](https://www.rybafish.net/img/ind_04_error.png)

Set upon database exceptions, most likely syntax error in the SQL query.

### render
![Render](https://www.rybafish.net/img/ind_05_render.png)

In case of huge result set returned to client (over 100&nbsp;000 cells) it might take some time to render it: during this time the console will have this indicator.

During this time whole application UI is locked, so no interraction possible. 

### disconnected
![Disconnected](https://www.rybafish.net/img/ind_06_disconnected.png)

This one means the console is not connected to the database.

### alert
![Alert](https://www.rybafish.net/img/ind_07_alert.png)

Set if the console detected an alert, see the [alerting functionality](/alerts) page on this topic.

### autorefresh
![Autorefresh](https://www.rybafish.net/img/ind_08_refresh.png)

Set if the console switched into [auto-refresh](/sqlconsole#refresh) mode and no query is running at the moment. As soon as query will be triggered - indication will switch to 'Running' (![Running](https://www.rybafish.net/img/ind_03_running.png)).
