## Access Control Issues - Part 1

Codice Vulnerabile:

> app/src/main/java/jakhar/aseem/diva/AccessControl1Activity.java

```
<activity
    android:name=".APICredsActivity"
    android:label="@string/apic_label" >
    <intent-filter>
        <action android:name="jakhar.aseem.diva.action.VIEW_CREDS" />

        <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
</activity>
```

For instance, by declaring an intent filter for an activity, you make it possible for other apps to directly start your activity with a certain kind of intent. Likewise, if you do not declare any intent filters for an activity, then it can be started only with an explicit intent.

`<action>` Declares the intent action accepted, in the name attribute. The value must be the literal string value of an action, not the class constant.

`<category>` Declares the intent category accepted, in the name attribute. The value must be the literal string value of an action, not the class constant. 

Quando un intent filter è usato con un component dell'aplicazione come un'activity, il component è esposto pubblicamente.
È possibile invocare l'activity da qualsiasi applicazione.

Exploit:

- `$ adb shell am start -n jakhar.aseem.diva/.APICredsActivity -a jakhar.aseem.diva.action.VIEW_CREDS`
