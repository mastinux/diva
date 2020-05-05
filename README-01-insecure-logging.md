## Insecure Logging

Codice vulnerabile:

> app/src/main/java/jakhar/aseem/diva/LogActivity.java

```
Log.e("diva-log", "Error while processing transaction with credit card: " + cctxt.getText().toString());
```

Exploit:

`$ adb logcat | grep diva`

```
05-03 19:17:39.034  4298  4298 E diva-log: Error while processing transaction with credit card: 1234567890123456
```
