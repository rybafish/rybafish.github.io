---
title: RybaFish FAQ
---

## Chart
### Is BTP/HANA Cloud supported?
Kind of. With default settings login will terminated with the some error ID, and if you check the details...

```
select * from sys.authentication_error_details where correlation_id = '...'
```

will contain details like: "No password set for the user ...".

This happens because the default authentication method in HANA Cloud restricted to pbkdf2, which currently not supported by PyHDB driver in RybaFish.

But you can enable old-style authentication by updating the config:

```
alter system alter configuration ('global.ini', 'system') set ('authentication', 'password_hash_methods') = 'pbkdf2,sha256' with reconfigure;
```

**And update the user password** in order to generate old-style sha256 password hash on HANA side. This is to be done after the configuration change.

With those settings RynaFish should run fine in HANA Cloud, pbkdf2 [in progress]([url](https://github.com/rybafish/rybafish/issues/931)).

### Why such colours selected, can I change them?
Colors and line styles provided by the database. You can manually change the color by right-mouse-click in the KPIs table.

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
Before 0.96 beta I it was client-side measurement. Including: prepare, execute and fetch. Highly depends on the network and the result size.

Since 0.96 beta I two values provided for each execution, client-side, and server side.

### Is it possible to enable auto-commit?
At the moment - no. You need to do explicit "commit" if you need to persist your changes.
Let me know if you need this auto-commit feature, it can be implemened short term (if eeded).

### What status bar indicator colors mean?
There is a [separate page](/indicator) on that, but in a nutshell:
* Light ray: connected, waiting.
* Dark gray: disconnected.
* Blue: synchronous call is running: usually connection or keep-alive execution.
* Bright green: asynchronous call is running. You can click on the indicator to see current runtime.
* Light green: the console is in auto-refresh mode.
* White: rendering the result.
* Red: error.
