# Installation Tips

**Work in progress**

All of these tips are optional, however most are used on the installations
around the city.

## Have your web browser clear the browser cache on exit.

This can greatly reduce the chance of showing content that is out of date,
and scripts that have been updated.

**In Firefox:**

-   Open up the Preferences screen.
-   Select "Privacy & Security".
-   Scroll down to the "Cookies and Site Data" section.
-   Make sure "Delete cookies and site data when Firefox is closed" is checked.

**In Chromium:**

-   Open up the Settings screen.

-   The left-hand menu may or may not be displayed.  If not, open it.

-   Under "Advanced", select "Privacy and security".

-   Click "Site Settings".

-   Click "Cookies and site data".

-   The setting name varies greatly by Chromium version.
    It could be one of the following.

    -   Most recently, make sure "Clear cookies and site data when you quit Chromium" is on.
    -   In older versions, make sure "Keep local data only until you quit the browser" is on.

## If network connectivity is ever questionable, run a local web server.

Most content types are flexible enough to display remote content.
Having a local server with a local configuration file
will better let the display recover in the event of a network disruption.

## Need to manage the display remotely?  Install `openssh-server` and `x11vnc`.

Running an SSH server on the display machine can greatly help with
remote administration.  You can use SSH to update configuration files,
run operating system and software updates, and restart the machine.

Once an SSH server is installed, you can connect to the display machine using
Windows PowerShell (or any other SSH client).

```powershell
>  ssh -l [userName] [ipAddress]
```

Where `[userName]` is replaced with the user name, and `[ipAddress]` is replaced
with the display's IP address.

### Some of the more handy commands

**Restart the machine**

```bash
sudo reboot
```

**Update the tv-display software**

```bash
cd /var/www/html/tv-display
sudo git pull origin master
```

_Note that the path to the tv-display software may vary by your installation.
It is recommended that you restart the display machine after updating._

**Update the operating system and other software**

_Note that depending on what updates are included,
you may lose your connection to the machine.
It is recommended to run these commands using `screen`._

```bash
screen
sudo apt-get update
sudo apt-get upgrade
```

If you lose connection, restore your SSH connection, then reconnect to the
`screen` using:

```bash
screen -raAd
```

To kill the screen when you are done, press <kbd>Ctrl</kbd> <kbd>A</kbd>, then <kbd>k</kbd>.

_It is recommended that you restart the display machine after updating._

**Start the VNC Server**

```bash
sudo x11vnc -safer -once -nopw -auth guess -display :0 -noxdamage
```

## Want fancy fonts?  Install `typecatcher`.

![Typecatcher](typecatcher.png)

```bash
sudo apt-get install typecatcher
```

Typecatcher is an application that makes it easy to install Google Fonts
on your Raspberry Pi or Linux Mint display.

Once installed, the fonts can then be used on your display by setting the
`fontFamily` property in the display's config file.
