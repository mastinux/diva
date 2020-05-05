## Input Validation Issues - Part 2

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/InputValidation2URISchemeActivity.java

```
wview.loadUrl(uriText.getText().toString());
```

Exploit:

- `file:///selinux_version`
