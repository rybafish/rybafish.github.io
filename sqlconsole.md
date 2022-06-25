# SQL Console Help

### Table of contents
* [Basics](#basics)
    * [Execute](#execute)
    * [Execute without parsing](#executenoparsing)
    * [Execute leaving results](#executeresults)


## Basics<a name="basics"></a>
Very basics of SQL console are available in the toolbar:

![toolbar](https://www.rybafish.net/img/sql_01_toolbar.png)

Let's go through buttons and see how this works. 

The main point having SQL console is executiong SQL statements, that is why RybaFish has three different wais doing this.

![F8](https://www.rybafish.net/img/F8_icon.png) `F8` Main *Execute* button.<a name="execute"></a>

To execute a statement you need to type it, place cursor somewhere inside and press ![F8](https://www.rybafish.net/img/F8_icon.png) (or F8). RybaFish will _try_ to parse the statement and if succesfull - highlight and execute it.

To make this work, statements separatedneed to be separated by semicolon: `;`. This makes it possible to work with several statements in the same console and execute them when required. Let's say we worj with the following sqls:
```sql
select now() from dummy;

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
When th ecursor is on the first line (anywere before semicolon) we can hit ![F8](https://www.rybafish.net/img/F8_icon.png) (`F8`) and and execute it:

![statement execution](https://www.rybafish.net/img/sql_03_statement.png)

If you move cursor to the line #5 and press the execute button again, the _second_ statement will be highlighted and executed:

![statement execution](https://www.rybafish.net/img/sql_02_statement.png)

Once again, you don't need to select the statements, just put cursor somewhere inside the statement.

For example, you have a list of steps to be executed as a single action. In this it will be requred so select statements manually and hit the same button.

What actually happens in this case - RybaFish still does parsing of the SQLs and execute them in a queue:

![statements execution](https://www.rybafish.net/img/sql_04_statements.png)

Corrsesponding number of result set tabs will be populated, in this case two of them: Results and Results2

![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) `Alt+F8` *Execute without parsing*.<a name="executenoparsing"></a>

As mentioned, the *Execute* button relies on SQL parsing, which may fail. In some cases, for instance SQLScript CREATE PROCEDURE statements or similar semantically complex constructions parsing may highlight part of the statement which cannot be executed. This is where *Execute without parsing* requred: you just select the statement manually and hit ![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) or `Alt+F8`, that's it: RybaFish will send to the database whatever was selected without any intermediate processing.

![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8` *Execute creating a new result set*.<a name="executeresults"></a>

Sometimes it might be required to keep the results of previous execution and repeat the same SQL in order to compare the results. This is where ![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8` can help to save some effort: this execution mode repeats previous query but does not clear the Results tab.


## Title 2
also not sure

```sql
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
