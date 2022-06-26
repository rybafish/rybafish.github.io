# SQL Console Help

### Table of contents
* [Basics](#basics)
    * [Executing statements](#execute)
      * [Main Execute](#execute) statements button
      * [Error highlighting](#errorhighlighting)
      * [Execute several](#executemany) statements at once
    * [Execute without parsing](#executenoparsing)
    * [Execute leaving results](#executeresults)
    * [Beautify](#beautify) code
    * [SQL Browser](#sqlbrowser)
 * [Advanced](#advanced)

## Basics<a name="basics"></a>

To open an SQL Console you need to be already connected to the database, then: File &rarr; New SQL Console or `Alt+S`.

Bye default SQL Console uses basic syntax highlighting, plus, being under heavy influence of Notepad++ there are some minor highlighting features like brakets highlighting and words highlighting.

Most of the functionality is really straighforward and actully can be used without reading the documentation, but, anyways.

Very basics of SQL console are available in the toolbar:

![toolbar](https://www.rybafish.net/img/sql_01_toolbar.png)

Let's go through buttons and see how this works. 

The main point having SQL console is executiong SQL statements, that is why RybaFish has three different ways doing this.

<a name="execute"></a>
### Main Execute Statements Button

![F8](https://www.rybafish.net/img/F8_icon.png) `F8`

To execute a statement you need to place cursor somewhere inside and press ![F8](https://www.rybafish.net/img/F8_icon.png) or `F8`. RybaFish will _try_ to parse the statement and if succesfull - highlight and execute it.

To make this work, statements need to be separated by the semicolon: `;` character. This makes it possible to work with several statements in the same console and execute them when required. Let's say we work with the following SQLs:
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
When the cursor is on the first line (anywere before semicolon) you can hit ![F8](https://www.rybafish.net/img/F8_icon.png) (`F8`) and and execute it:

![statement execution](https://www.rybafish.net/img/sql_03_statement.png)

If you move cursor to the line #5 and press the execute button again, the _second_ statement will be highlighted and executed:

![statement execution](https://www.rybafish.net/img/sql_02_statement.png)

Once again, you don't need to select the statements, just put cursor somewhere inside the statement.

<a name="errorhighlighting" />
### Error highlighting

In case of syntax error during the processing of the statement the reported line/position will be highlighted with red background:

![Error highlighting](https://www.rybafish.net/img/sql_05_error.png)

Here the source object does not have the HOSTNAME column and it is reported in console log and highlighted in the SQL text.

<a name="executemany" />
### Execute several statements
Sometimes it is requred to execute several statements at once. For example, you have a list of steps to be executed as a single action. In this case it will be requred so select statements manually and hit the same Execute button.

What actually happens in this case - RybaFish still does parsing of the SQLs and execute them in a queue:

![statements execution](https://www.rybafish.net/img/sql_04_statements.png)

Corrsesponding number of result set tabs will be populated, in this case two of them: Results and Results2

<a name="executenoparsing"></a>
### Execute without parsing
![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) `Alt+F8` **Execute without parsing**

As mentioned, the *Execute* button relies on SQL parsing, which may fail. In some cases, for instance SQLScript CREATE PROCEDURE statements or similar semantically complex constructions parsing may highlight incomplete statement which cannot be executed. This is where *Execute without parsing* requred: you just select the statement manually and hit ![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) or `Alt+F8`, that's it: RybaFish will send to the database whatever was selected without any intermediate processing. Currently known parsing issue is nested begin ... end blocks in SQLScript procedures, we have an [open issue](https://github.com/rybafish/rybafish/issues/248) on that.

<a name="executeresults" />
### Execute Creating a New Result Set
![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8`.

Sometimes it might be required to keep the results of the previous execution and repeat the same query. In most cases this is required when you need to compare the results of two executions but lazy saving previous result. This is where ![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8` will help saving some elictricity for you. You can use this function several times, every next execution will populate a new Results tab.

The moment you use regular **Execute** all the previous Results will be cleared (it is [planned](https://github.com/rybafish/rybafish/issues/665) to have a warning in this regards).

<a name="beautify" />
### Beautify or Autoformat
![beautify](https://www.rybafish.net/img/format.png) `Ctrl+Shift+O` 

RybaFish console contains simple autoformatting function that can be useful to make sql statement readable. To use this function you need to select the statement first.

![sqlBrowser](https://www.rybafish.net/img/sqlbrowser.png) `F11` SQL Browser<a name="sqlbrowser" />

Every DBA has a collection of crafted SQL statements used on a daily basis. RybaaFish gives an option to organize the stuff in folders and files to be consumed in SQL Console. By default RyebaFish `scripts` folder is used for that but it can be changed by setting the `scriptsFolder` setting in config.yaml.

![sqlBrowser](https://www.rybafish.net/img/sql_06_browser.png)

From this dialog you can insert the statement to current cursor position or open in new SQL console. Give it a try.

## Advanced
Not yet, but we will cover:
* autocommit (disabled by default)
* autorefresh
* alerts
