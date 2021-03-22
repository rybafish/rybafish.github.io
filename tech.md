# Technologies
PyQt used as UI library.

PyHDB - opensource SAP HANA driver maintained by SAP used to connect to SAP HANA DB

# Features
Asyncroniouts calls to the DB from SQL console - implemented using QThread

## PyHDB
It is nice and quite good library provided by SAP. Yet for the needs of RybaFish Charts there were several modifications done.

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
- ctrl+u/U lowercase/uppercase the selection
- line numbers implemanted manually, as there's no built in support in Qt
- brackets highlighting: implemented manually
- selected word will be highlighetd through the whole document: useful for variables, column names, etc.