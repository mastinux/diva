## Input Validation Issues - Part 1

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/SQLInjectionActivity.java

```
cr = mDB.rawQuery("SELECT * FROM sqliuser WHERE user = '" + srchtxt.getText().toString() + "'", null);
```

Exploit:

- `a or 'a'='a`
