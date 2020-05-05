## Hardcoding Issues – Part 1

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/HardcodeActivity.java

```
if (hckey.getText().toString().equals("vendorsecretkey")) {
	Toast.makeText(this, "Access granted! See you on the other side :)", Toast.LENGTH_SHORT).show();
}
else {
	Toast.makeText(this, "Access denied! See you in hell :D", Toast.LENGTH_SHORT).show();
}
```

Exploit:

- `vendorsecretkey`
