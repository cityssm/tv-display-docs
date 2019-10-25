# Troubleshooting

This document is a work is progress as more content types are developed
and as more displays are installed.


### Some of my content is being skipped or not displaying.

- **Are you loading the right configuration file?**  Check the configuration file path in the
  `config` parameter for errors.

- If your content is being served up from a remote server, **check your network connection**.
  To avoid showing a grey screen of nothingness, some content types will automatically when they can't load completely.

- If your configuration is local, but some content is being served up from a remote server,
  ensure the remote server sets the
  [Access-Control-Allow-Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Headers) and
  [Access-Control-Allow-Origin](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin)
  HTTP headers properly.

- **Check that the content type is available** on the server you're trying to load it from.
  If you're loading local and remote content in the same configuration,
  the content available on each server may be different.

- Look for errors under the Network tab in the browser's developer tools.




### Some of my content doesn't display correctly or doesn't fit on my screen.

When new content types are developed, they are written to work on their target displays.
The display isn't meant to be navigated through by every possible device/browser combination.

For best display results:

- Use a current, feature rich web browser for your display, like Google Chrome (Chromium on Linux) or Mozilla Firefox.

- Use a 1080p television display, or a widescreen monitor with 1920 x 1080 resolution.
