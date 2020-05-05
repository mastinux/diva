## Insecure Data Storage - Part 3

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/InsecureDataStorage3Activity.java

```
File ddir =  new File(getApplicationInfo().dataDir);

...

File uinfo = File.createTempFile("uinfo", "tmp", ddir);
uinfo.setReadable(true);
uinfo.setWritable(true);
FileWriter fw = new FileWriter(uinfo);
fw.write(usr.getText().toString() + ":" + pwd.getText().toString() + "\n");
fw.close();
```

Exploit:


- `$ adb shell cat /data/data/jakhar.aseem.diva/uinfo1408388359tmp`

```
john:lock
```

