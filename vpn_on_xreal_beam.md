# how-todooo


With the new update on xreal beam you can install third part apps

First install quickshortcutmaker, and navigate to the settings apps, open settings and enable adb.

Make sure you have adb installed on your pc
Now plug in xreal beam to pc, open vpn app install on xreal beam and when the dialog to turn on vpn shows up run these commands in terminal

'adb shell uiautomator dump /sdcard/Download/view.xml'
'adb pull /sdcard/Download/view.xml'

this will generate a file on xreal beam of the ui, and save it to your pc, from that open the xml file and search for 'OK', then check for the bounds tag


<node index="1" text="‎‏‎‎‎‎‎‏‎‏‏‏‎‎‎‎‎‎‏‎‎‏‎‎‎‎‏‏‏‏‏‏‎‏‎‎‏‎‎‏‎‏‏‏‎‎‏‏‏‎‎‏‎‏‏‏‎‏‎‎‎‏‎‏‎‎‏‎‎‏‏‎‎‏‎‎‏‎‏‏‏‏‎‏‏‎‏‎‎‎‏‎‏‏‏‎OK‎‏‎‎‏‎" resource-id="android:id/button1" class="android.widget.Button" package="com.android.vpndialogs" content-desc="" checkable="false" checked="false" clickable="true" enabled="true" focusable="true" focused="false" scrollable="false" long-clickable="false" password="false" selected="false" bounds="[1257,618][1353,699]"/>
