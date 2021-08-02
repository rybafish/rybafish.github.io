Sinve v0.9 RybaFish supports context SQLs.

This means you can define a custom sql that can be invoked from righ mouse click menu in results area.

![context sql example](http://rybafish.github.io/contextsql.png)

The list of proposed SQLs depends on the column name.

Definition example:
```
column: 'STATEMENT_HASH'

name: 'Get statement string'

sql: >
    select statement_string
    from m_sql_plan_cache
    where statement_hash = '$value'
```

## File structure

#### column
Column name 

### name
Name of the SQL. This text will be displayed in the context menu.

### sql
Statement itself.

* $value will be replaced by the cell value
* in case of strings/dates etc. you need to take care on quotation
* according to YAML formatting rules the multiline statement has to start with '>' character and must be idented. Only spaces allowed as indentation character, do not use tabs to avoid yaml parsing issues.
