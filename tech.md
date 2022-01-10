# Technologies
PyQt used as UI library.

PyHDB - opensource SAP HANA driver maintained by SAP used to connect to SAP HANA DB.

# Features
Asyncroniouts calls to the DB from SQL console - implemented using QThread

## PyHDB mod
It is nice and quite good library provided by SAP. Yet for the needs of RybaFish Charts there were several modifications done:

- support for long SQL strings
- support of multiple result sets for procedures
- support of extended data types, mainly to have microseconds support in timestamps
- close resultset feature to actually close the cursor and release versions on the DB
- fixed 32000 rows fetch limit in fetch_many

# Chart
The chart is basically a scroll area. All the charts created just using lines.

# SQL Console
Created based on QPlainTextEdit. Syntax highlighting done with help of QSyntaxHighlighter. Word and brackets highlighting are custom implemantation using QLayout.setAdditionalFormats.

Features:
- tabkey for block identation
- ctrl+arrow to move line up/down
- ctrl+d to duplicate block
- ctrl+u/U lowercase/uppercase the selection
- line numbers: custom implementation
- brackets highlighting: implemented manually
- selected word will be highlighetd through the whole document: useful for variables, column names, etc.
