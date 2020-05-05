## Insecure Data Storage - Part 2

Codice Vulnerabile

> app/src/main/java/jakhar/aseem/diva/InsecureDataStorage2Activity.java

```
private SQLiteDatabase mDB;

...

mDB = openOrCreateDatabase("ids2", MODE_PRIVATE, null);
mDB.execSQL("CREATE TABLE IF NOT EXISTS myuser(user VARCHAR, password VARCHAR);");

...

mDB.execSQL("INSERT INTO myuser VALUES ('"+ usr.getText().toString() +"', '"+ pwd.getText().toString() +"');");
```

Exploit:

- `$ adb shell cat /data/user/0/jakhar.aseem.diva/databases/ids2`

