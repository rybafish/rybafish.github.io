# SQL Console Help

## Basics
Very basics of SQL console are available in the toolbar:

![toolbar](https://www.rybafish.net/sql_01_toolbar.png)

Let's go through buttons and see how this works. 

The main point having SQL console is executiong SQL statements, that is why RybaFish has three different wais doing this.

1. ![F8](https://www.rybafish.net/img/F8_icon.png) `F8`- Main *Execute* button.

2. ![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) `Alt+F8`- Main *Execute without parsing*.

3. ![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8`- *Execute creating a new result set*.



## Title 2
also not sure

```SQL
select 
    time, 
    host, 
    port,
    cpu, 
    memory_used,
    memory_allocation_limit
from m_load_history_service
order by time desc;
```

## Support
If you have suggestions or see bugs, please report using github page.
