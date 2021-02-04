# Technologies
PyQt used as main visual library
PyHDB - opensource SAP HANA driver maintained by SAP used to connect to SAP HANA DB

# Features
Asyncroniouts calls to the DB from SQL console - implemented 

#PyHDB
It is nice and quite good working library with some limitations.

Extentions created:
- support for long SQL strings
- support of multiple result sets
- support of extended data types, mainly to have microseconds suppotr in timestamps
- close resultset featore to actually close the cursor and release versions on the DB

# Chart
The chart area is basically a scroll area. All the charts created just using lines.

# SQL Console
Created based on QPlainTextEdit. Syntax highlighting done with help of QSyntaxHighlighter.

Features:
- tabkey for block identation
- ctrl+arrow to move line up/down
- ctrl+d to duplicate block
- line numbers implemanted manually, as there's no built in support in Qt
