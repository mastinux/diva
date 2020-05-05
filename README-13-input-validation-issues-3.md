## Input Validation Issues - Part 3

Codice Vulnerabile:

> app/src/main/jni/divajni.c

```
#define CODESIZEMAX 20

...

char code[CODESIZEMAX];

strcpy(code, pcode);
```

Exploit:

- `DDDDDDDDDDDDDDDDDDDD`
