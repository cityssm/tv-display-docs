# Installation Tips

**Work in progress**

All of these tips are optional, however most are used on the installations around the city.


## Have Chromium (or whatever browser you use) clear the browser cache on exit.

This can greatly reduce the chance of showing content that is out of date,
and scripts that have been updated.


## If network connectivity is ever questionable, run a local web server.

Most content types are flexible enough to display remote content.
Having a local server with a local configuration file
will better let the display recover in the event of a network disruption.


## Need to manage the display remotely?  Install `openssh-server` and `x11vnc`.


## Want fancy fonts?  Install `typecatcher`.

![Typecatcher](typecatcher.png)

```bash
$ sudo apt-get install typecatcher
```

Typecatcher is an application that makes it easy to install Google Fonts
on your Raspberry Pi or Linux Mint display.

Once installed, the fonts can then be used on your display by setting the
`fontFamily` property in the display's config file.
