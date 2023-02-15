# Indicators
Rybafish statusbar (most bottom line of the application window) has so-called indicators. Each indicator corresponds to the RybaFish tab:

![Indicators](https://www.rybafish.net/img/ind_00_example.png)

In this case four tabs are open. Those indicators reflect status of RybaFish tabs: chart and SQL consoles.

By the way, by clicking on the indicator itself you can change the active tab.

This page describes available statuses and their meaning.

#### ![Idle](https://www.rybafish.net/img/ind_01_idle.png) idle

The console is connected and doing nothing.

#### ![Sync](https://www.rybafish.net/img/ind_02_sync.png) sync

The console is doing some king of sync-reauest. This means whole application UI is locked until the request finishes. In most cases you will see this one for the first tab (charts) because chart calls are 100% synchronous.

SQL consoles do most of database requests in synchronous mode with some exceptions. For instance, keep-alive requests sent in synchronous mode because normally they are very fast and you will not notice them if the connection is fine.

### ![Running](https://www.rybafish.net/img/ind_03_running.png) running

This one set by SQL consoles during database request: database execution and results transfer to client do not block application.

### ![Error](https://www.rybafish.net/img/ind_04_error.png) error

Set upon database exceptions, most likely syntax error in the SQL query.

### ![Render](https://www.rybafish.net/img/ind_05_render.png) render

In case of huge result set returned to client (over 100&nbsp;000 cells) it might take some time to render it: during this time the console will have this indicator.

During this time whole application UI is locked, so no interraction possible. 

### ![Disconnected](https://www.rybafish.net/img/ind_06_disconnected.png) disconnected

This ine changed in 092 and became dark gray instead of this redish.
It means the console is not connected to the database.

### ![Alert](https://www.rybafish.net/img/ind_07_alert.png) alert

Set when the console detected an alert, see the [alerting functionality](/soundAlerts) page on this topic.

### ![Autorefresh](https://www.rybafish.net/img/ind_08_refresh.png) autorefresh

Set when the console switched into [auto-refresh](/sqlconsole#refresh) mode and no query is running at the moment. As soon as query will be triggered - indication will switch to 'Running' (![Running](https://www.rybafish.net/img/ind_03_running.png)).
