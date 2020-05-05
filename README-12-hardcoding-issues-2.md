## Hardcoding Issues - Part 2

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/DivaJni.java

```
private static final String soName =  "divajni";
```

> app/src/main/java/jakhar/aseem/diva/Hardcode2Activity.java

```
djni = new DivaJni();

...

if (djni.access(hckey.getText().toString()) != 0) {
	Toast.makeText(this, "Access granted! See you on the other side :)", Toast.LENGTH_SHORT).show();
}
else {
	Toast.makeText(this, "Access denied! See you in hell :D", Toast.LENGTH_SHORT).show();
}
```

Exploit:

- disponendo della sola .apk

	- estrai contenuto .apk

	- `$ strings libs/divajni.so`

	- provo le stringhe che ottengo per accedere (`olsdfgad;lh`)

- disponendo del codice sorgente

	- in `app/src/main/jni/divajni.c` trovo `#define VENDORKEY   "olsdfgad;lh"`

