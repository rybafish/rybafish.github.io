---
title: Console results highlighting
---

# Overview
It is sometimes beneficial to emphasize specific values in the result set. A good example is the "statement_hash" values. Certain statements may reoccur during system monitoring/analysis, but remembering values like "de4d08b0863b6076896dc1334e2592f4" can be challenging.

Wouldn't it be helpful to have the ability to highlight particular values for this purpose? Well, now it's possible.

All you need to do is create a file with the following (or similar) content:

```
d6fd6678833f9a2e25e7b53239c50e9a: Statistics service wrapper call
de4d08b0863b6076896dc1334e2592f4: TREXviaDBSL
```

On mouse hover the comment text will be displayed as a hint.

By default, RybaFish includes this file located in "highlights/statement_hash/standard.html"

Here's an example of how the result might appear:

![image](https://github.com/rybafish/rybafish.github.io/assets/53466066/531f7ff2-f00d-43af-aab5-610c52c75330)

Feel free to enhance it or create an additional; the filename is not critical. However, the folder name must correspond to the column where the values are checked, and it's not case-sensitive.

## color:
You can adjust highlighting color by including the following line in the yaml:

```
color: '#fee'
```
The default highlighting color is #dfe.

## Availability

Available since 096 beta II.

Currently this feature only works in [experimental](/config#experimental) mode.
