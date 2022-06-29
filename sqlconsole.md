# SQL Console Help

### Table of contents
* [Basics](#basics)
* [Console Toolbar](#toolbar)
    * [Executing Statements](#execute)
      * [Main Execute](#execute) Statements Button
      * [Errors Highlighting](#errorhighlighting)
      * [Execute Several](#executemany) Statements At Once
    * [Execute Without Parsing](#executenoparsing)
    * [Execute Leaving Results](#executeresults)
    * [Beautify](#beautify) code
    * [SQL Browser](#sqlbrowser)
    * [(re)Connect](#connect)
    * [Disconnect](#disconnect)
    * [Schedule Automatic Refresh](#refresh)
    * [ABAP Copy](#abap)
 * [Result Set](#resultset) Manipulations
   * [Copy Column](#column) Names
   * [Take a Screenshot](#screen)
   * [Insert Column Names](#insertcolumnnames)
   * [Generate Filter Condition](#generatefilter)
   * [Highlight Value](#highlightvalue)
   * [Highlight Changes](#highlightchanges)
   * Those two option duplicate toolbar functionality
      * [ABAP-style Copy](#abap)
      * [Schedule Automatic Refresh](#refresh)
 * [Advanced](#advanced)
 * [Editor Hotkeys](#)

## Basics<a name="basics"></a>

RybaFish Charts designed as a single-database client so it is not possible to open connection to two different databases. Single configuration used for charts and consoles. If you really need to open two different console connections - the only way is to start two RybaFish instances.

To open an SQL Console you need to be already connected to the database, then: File &rarr; New SQL Console or `Alt+S`.

SQL Console uses basic syntax highlighting for SQL keywords, comments and literals. Developed under heavy influence of Notepad++ editor there are additional highlighting features like brakets highlighting and words highlighting.

Important note: SQL Console does not have autocommit flag set. That meants any data-changing statemennts will not be visible for other transactions until explicit `commit` executed. There is [a request](https://github.com/rybafish/rybafish/issues/668) to make this configurable.

Each tab in RybaFish has it's own 'indicator' in the status bar: small solid color square indicating the status of the console: is it connected, is it running, etc. We will be paying cttention to the indication during this documentation and you might start paying attention to it too. There is a [short reference](/indicator) on this topic.

Frankly no special training required to start using the console, but to get the full power of it you might need to go quickly throught this document. So, let's jump right into it!

<a name="toolbar" />
## Console Toolbar
Very basics functions of the console are available in the toolbar:

![toolbar](https://www.rybafish.net/img/sql_01_toolbar.png)

The toolbar can be enabled/disabled by menu Actions &rarr; SQL Console Toolbar, which is equivalent to [sqlConsoleToolbar](https://www.rybafish.net/config#sqlConsoleToolbar) setting.

Let's go through the buttons one by one and see what they do. 

<a name="execute"></a>
### Main Execute Statements Button

![F8](https://www.rybafish.net/img/F8_icon.png) `F8`

The main point having SQL console is executiong SQL statements, that is why RybaFish has three different ways doing this. To execute a statement you need to place cursor somewhere inside and press ![F8](https://www.rybafish.net/img/F8_icon.png) or `F8`. RybaFish will _try_ to parse the statement and, if succesfull, - highlight and execute it.

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

If you move the cursor to the line #5 and press the Execute button again, the _second_ statement will be highlighted and executed:

![statement execution](https://www.rybafish.net/img/sql_02_statement.png)

Once again, you don't need to select the statement, just put the cursor somewhere inside.

<a name="errorhighlighting" />
### Errors highlighting

In case of syntax error during the processing of the statement the reported line/position will be highlighted with red background:

![Error highlighting](https://www.rybafish.net/img/sql_05_error.png)

Here the source object does not have the HOSTNAME column and it is reported in console log and highlighted in the SQL text.

Also, if you pay attention to line numbers - numbering adjusted to the statement itself. This makes it way much easier to see what line is reported because the database has no idea what is the statement position inside your console and only able to report position inside the statement.

As soon as you make any change in the console - numbering will reset to the normal mode. This behaviour can be desabled by setting [blockLineNumbers](https://www.rybafish.net/config#blockLineNumbers) to False.

<a name="executemany" />
### Execute several statements
Sometimes it is required to execute several statements at once. For example, you have a list of steps to be executed togather. In this case it will be requred so select statements manually and hit the same Execute button.

What actually happens in this case - RybaFish still does parsing of the SQLs based on the semicolon character, and execute them in a queue:

![statements execution](https://www.rybafish.net/img/sql_04_statements.png)

Corrsesponding number of result set tabs will be populated, in this case two of them: Results and Results2

<a name="executenoparsing"></a>
### Execute without parsing
![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) `Alt+F8` **Execute without parsing**

As mentioned, the *Execute* button relies on SQL parsing, which may fail. In some cases, for instance SQLScript CREATE PROCEDURE statements or similar semantically complex constructions parsing may highlight incomplete statement which cannot be executed. This is where *Execute without parsing* requred: you just select the statement manually and hit ![Alt+F8](https://www.rybafish.net/img/F8alt_icon.png) or `Alt+F8`, that's it: RybaFish will send to the database whatever was selected without any intermediate processing. Currently known parsing issue is nested begin ... end blocks in SQLScript procedures, there is an [open issue](https://github.com/rybafish/rybafish/issues/248) on that.

<a name="executeresults" />
### Execute Creating a New Result Set
![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8`.

Sometimes it might be required to keep the results of the previous execution and repeat the same query. In most cases this is required when you need to compare the results of two executions but lazy saving previous result. This is where ![Ctrl+F8](https://www.rybafish.net/img/F8ctrl_icon.png) `Ctrl+F8` will help saving some elictricity for you. You can use this function several times, every next execution will populate a new Results tab.

The moment you use regular **Execute** all the previous Results will be cleared (it is [planned](https://github.com/rybafish/rybafish/issues/665) to have a warning in this regards).

<a name="beautify" />
### Beautify (autoformat)
![beautify](https://www.rybafish.net/img/format.png) `Ctrl+Shift+O` 

RybaFish console has a simple autoformatting function that can be useful to make SQL statement readable. To use this function you need to select the statement first.

<a name="sqlbrowser" />
## SQL Browser
![sqlBrowser](https://www.rybafish.net/img/sqlbrowser.png) `F11`

Every DBA has it's own collection of crafted over the years SQL statements. RybaFish gives an option to organize the stuff in a built-in library which is quickly available from the tool itself. The approach is very straight-forward: you keep all the SQLs in flat files on local or network drive and point RybaFish to the root folder of this collection. By default RybaFish uses `scripts` folder for that, but this can be changed by setting the [scriptsFolder](https://www.rybafish.net/config#scriptsFolder) setting in config.yaml.

![sqlBrowser](https://www.rybafish.net/img/sql_06_browser.png)

From this dialog you can insert the statement in current cursor position or open it in a new SQL console. Both actions will not use clipboard.

If the file starts from a single-line comment (started from `--`) this comment will be displayed. As extracting comments from all the files might take some time, to avoid freezing of the dialog - a background thread used. Comments will appear in the dialog as soon as background thread finishes. This thread runs only for the first dialog opening and following executions use cached values. If it is requred to reload the library without restart of RybaFish - there is a `Reload` button available.

<a name="connect" />

## (re)Connect

![connect](https://www.rybafish.net/img/connect.png)

This button connects console to the database when disconnected and re-connects when connected. If you try to execute an SQL in disconnected console - RybaFish will notify you and propose connecting, so this button is not the most often used one.

<a name="disconnect" />

## Disconnect

![disconnect](https://www.rybafish.net/img/disconnect.png)

This button disconnects the console from the database. Might be useful when you want to make sure you close the session and release all the transaction-related things, for example. Not the most often used button either (because the **Execute** is).

<a name="abort" />
## Generate Cancel Sesson SQL
![sqlBrowser](https://www.rybafish.net/img/abort.png)

RybaFish does not have built in abortion mechanism due to several reasons, but there is a button to help you preparing the ALTER statement for this. When pressed it generates cancel session statement related to the current console:

`alter system cancel session '304021'`

The statement generated in the log area of console. It is not executed, you need to copy it and execute  in the other console manually. Other console used because the current one is most likely busy doing something, otherwise, why do you want to cancel it?

By the way, in some cases "cancel session" is not good enough and you might want to use "disconnect session" instead.

<a name="refresh" />
## Schedule Automatic Refresh
![refresh](https://www.rybafish.net/img/refresh.png)

Sometimes it might be required to have the result set updated by itself. For example you are waiting for some event or monitoring particular value. This is where the automatic refresh might be useful. To get use of it you need to execute the statemen first and then press ![refresh](https://www.rybafish.net/img/refresh.png). RybaFish will request the refresh interval:

![Refresh](https://www.rybafish.net/img/sql_08_refresh.png)

This feature shows it's real power when combined with the [alerting](/soundAlerts) functionality: RybaFish can play a sound when certain conditions met.

Logging for this console will be suppressed until the auto-refresh stopped. To stop it you can press the button again (un-press it) or execute any sql in the same console: this will also disable the auto-refresh mode.

There is a limitation: this option can only be used for a single result set queries.

<a name="abap" />
## ABAP Copy
![ABAP Copy](https://www.rybafish.net/img/abapcopy.png)

This is a toggle-button that enables ABAP-style results copy which might be useful to extract the results to be pasted in text form. The output looks like this:

```
----------------------------------------------
|TIME                   |HOST      |PORT |CPU|
|--------------------------------------------|
|2022-06-27 11:20:18.727|atgvmls967|30007|  0|
|2022-06-27 11:20:18.727|atgvmls967|30003|  1|
|2022-06-27 11:20:08.7  |atgvmls967|30003|  1|
|2022-06-27 11:20:08.7  |atgvmls967|30007|  0|
|2022-06-27 11:19:58.672|atgvmls967|30007|  0|
----------------------------------------------
```
Make sure you use monospace font for that, like Courier or Consolas.

## Context Menu
By the way, there is a context menu which is available on right mouse click in the area of SQL Console:

![Context Menu](https://www.rybafish.net/img/sql_07_contextmenu.png)

This menu contains mostly the same functions that are available in toolbar except the Explain Plan.

<a name="resultset" />

# Result Set Manipulations

Result set related options are available in the context menu when the mouse is over a Results tab:

![Context Menu Results](https://www.rybafish.net/img/sql_09_contextresults.png)

<a name="column"/>
## Copy Column(s)

You can select one or several columns and use this option. Column names will be copied into clipboard, comma-separated. If you are using this feature to create a column list to be listed in SQL statement, consider using [Insert Column Names](#insertcolumnnames) option instead to avoid clipboard manipulations.

<a name="screen"/>
## Take a Screenshot

Very stright-forward: it puts a screen-shot of the visible area of the result set into clipboard to be used in presentation or email.

<a name="insertcolumnnames" />
## Insert Column Names

This option puts comma-separated list of column names into current position of the cursor in SQL console. Clipboard is not used during this operation. It might be useful while composing SQL statement based on something like select * from ...

By default column names are upper-cased, I prefer lower-case when possible, there is a setting [lowercase-columns](https://www.rybafish.net/config#lowercase-columns) for that. When required (special characters, different case letters, etc), column names will be double-quoted according to SQL standard.

<a name="generatefilter" />
## Generate Filter Condition

When you do free-style investigation it is often required to focus on particular subset of the result. Let's execute the same query:

![Example Query](https://www.rybafish.net/img/sql_10_query.png)

There is data on two ports 30003 and 30007 available but let's say we are only interested in port number 30003. That means we need to add `where port = 30003` to this statement but instead typing the full where clause we will only type 'where ' and right-mouse-click on any cell containing the required value (port 30003) and select **Generate Filter Condition** option. The rest of condition `port = 30003` will be insetred at cursor position.

What is nice about this option - it keeps the clopboart intact and you can combine several columns. If you select time and port cells before using it - the generated condition will be something like
```sql
time = '2022-06-29 09:01:26.517' and port = 30003
```
Literals or timestamp columns will be quoted, сonjunction ("and") used to combine values.

You still need to type 'where' manually. 

<a name="highlighvalue" />
## Highlight Value

This feature also helps tracking particular value in the result set but without modification of the query. Let's take the same example and use right-mouse-click &rarr; Highlight Value on the same 30003 port. Rows with this value will be highlighted:

![Example Query](https://www.rybafish.net/img/sql_11_query_hl.png)

## Highlight Changes
<a name="highlightchanges" />

This feature is very similar to the previous one but it highlights changes in certain column. In my practice this is most often useful to highlight timestamp changes. Let's take the same example but now right-mouse-click on the 'time' column and use **Highlight Changes** from the context menu:   

![Example Query](https://www.rybafish.net/img/sql_12_query_hl.png)

As you can see, rows highlighting changes with time value changes.

<a name="advanced"/>
# Advanced
Not yet, but we will cover:
* autocommit (disabled by default)
* autorefresh
* explain plan
* alerts
