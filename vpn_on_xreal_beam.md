# Install VPN on Xreal Beam

When you install vpn apps and try to enable them it doesnt allow you to click ok, this guide is a workaround using adb to click the ok button it for you.

###XREAL BEAM update 1.4.1 


With the new update on xreal beam you can install third party apps

First install quickshortcutmaker(https://www.xda-developers.com/quickshortcutmaker/) or the one by rushikesh on playstore, and navigate to the settings apps, open settings and enable adb.

Make sure you have adb installed on your pc.
Now open vpn app and try to start the vpn, now plug in xreal beam to pc, and when the dialog to turn on vpn shows up run these commands in terminal

'adb shell uiautomator dump /sdcard/Download/view.xml'

'adb pull /sdcard/Download/view.xml'

this will generate an xml file of the ui, and save it to your pc, from that open the xml file and search for 'OK', then check for the bounds tag


<node index="1" text="‎‏‎‎‎‎‎‏‎‏‏‏‎‎‎‎‎‎‏‎‎‏‎‎‎‎‏‏‏‏‏‏‎‏‎‎‏‎‎‏‎‏‏‏‎‎‏‏‏‎‎‏‎‏‏‏‎‏‎‎‎‏‎‏‎‎‏‎‎‏‏‎‎‏‎‎‏‎‏‏‏‏‎‏‏‎‏‎‎‎‏‎‏‏‏‎OK‎‏‎‎‏‎" resource-id="android:id/button1" class="android.widget.Button" package="com.android.vpndialogs" content-desc="" checkable="false" checked="false" clickable="true" enabled="true" focusable="true" focused="false" scrollable="false" long-clickable="false" password="false" selected="false" bounds="[1257,618][1353,699]"/>

x=((1353-1257)//2)+1257 
y=((699-618)//2)+618

finally run this command to make adb select ok for you, after that the vpn will work
'./adb shell input tap 1305 658'

remember to turn off adb for security after this




