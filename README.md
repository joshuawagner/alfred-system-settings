# alfred-system-settings

> Launch/open system settings panes from within the awesome [Alfred](https://www.alfredapp.com) App (updated for Ventura)  
<br>
<p align="left">
  <img src="https://github.com/joshuawagner/alfred-system-settings/blob/main/media/20230516_145050-screenshot.gif" width="700"/>
</p>
<br>

### Installation
- download the [latest release](https://github.com/joshuawagner/alfred-system-settings/releases/latest)
- double-click the downloaded `.alfredworkflow` file
- customize triggers (optional)

## Usage
- invoke Alfred
- type any of the following:
  - `ss` {spacebar}
  - `system settings`
  - `system preferences`

<br>
<p align="left">
<img src="https://github.com/joshuawagner/alfred-system-settings/blob/main/media/20230516_141405-screenshot.jpg" width="700">
</p>
<br>

## Backstory
I wanted to create an AppleScript to navigate to the 'Login Items' preference pane in System Settings but the pane ids have changed in newer versions of Mac OS.
<br>
I had a hard time finding paneIDs for the various system preference panes and how to activate them so I thought I'd post my findings here.

------

This script [from here](https://www.macscripter.net/t/other-way-to-open-system-preference-pane/72502/6) gave me a list of settings panes.

```
applescript
tell application "System Settings"
	tell every pane
		its id
	end tell
end tell
```

I'm running Mac OS Ventura 13.3.1 and here's the (long) list it gave me:

```
"com.apple.Appearance-Settings.extension", "com.apple.settings.PrivacySecurity.extension", "com.apple.ExtensionsPreferences", "com.apple.Profiles-Settings.extension", "com.apple.Mouse-Settings.extension", "com.apple.systempreferences.GeneralSettings", "com.apple.SystemProfiler.AboutExtension", "com.apple.Software-Update-Settings.extension", "com.apple.settings.Storage", "com.apple.AirDrop-Handoff-Settings.extension", "com.apple.LoginItems-Settings.extension", "com.apple.Localization-Settings.extension", "com.apple.Date-Time-Settings.extension", "com.apple.Sharing-Settings.extension", "com.apple.Time-Machine-Settings.extension", "com.apple.Transfer-Reset-Settings.extension", "com.apple.Startup-Disk-Settings.extension", "com.apple.Desktop-Settings.extension", "com.apple.Users-Groups-Settings.extension", "com.apple.ScreenSaver-Settings.extension", "com.apple.Network-Settings.extension", "com.apple.Battery-Settings.extension*EnergySaverPreferences", "com.apple.wifi-settings-extension", "com.apple.Keyboard-Settings.extension", "com.apple.Passwords-Settings.extension", "com.apple.Sound-Settings.extension", "com.apple.Touch-ID-Settings.extension*TouchIDPasswordPrefs", "com.apple.Siri-Settings.extension", "com.apple.BluetoothSettings", "com.apple.Game-Center-Settings.extension", "com.apple.Notifications-Settings.extension", "com.apple.Lock-Screen-Settings.extension", "com.apple.Displays-Settings.extension", "com.apple.Print-Scan-Settings.extension", "com.apple.Screen-Time-Settings.extension", "com.apple.Trackpad-Settings.extension", "com.apple.Wallpaper-Settings.extension", "com.apple.Focus-Settings.extension", "com.apple.Internet-Accounts-Settings.extension", "com.apple.ControlCenter-Settings.extension", "com.apple.systempreferences.AppleIDSettings*AppleIDSettings", "com.apple.Accessibility-Settings.extension", "com.wacom.ProfessionalControlPanel"
```
<br>
Here is an example of the AppleScript that comprises each action in the workflow!

```
tell application "System Settings"
	activate
	set the current pane to pane id "com.apple.LoginItems-Settings.extension"
end tell
```


<br><br>
## Mentions:

<h1 align="left">
	<img width="594" src="https://cdn.rawgit.com/derimagia/awesome-alfred-workflows/master/media/header.gif" alt="awesome-alfred-workflows">
	<br>
</h1>

> https://github.com/alfred-workflows/awesome-alfred-workflows
