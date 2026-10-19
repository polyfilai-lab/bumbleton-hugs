# Bumbleton Hugs

The page that opens when someone taps their phone to the bear. An NFC chip
sewn into the plush stores this site's address; tapping opens it, and the
recipient taps **Tap to open your hug** to play the bear's 15-second
Valentine's message with sound.

This is a standalone consumer site. It has no connection to any other
system.

## Files

- `index.html` is the whole page: plain HTML, CSS and a few lines of
  JavaScript. No build step.
- `404.html` catches mistyped links and points back to the message.
- `favicon.svg` is the heart icon.

The video, its poster frame and the share image are served from a CDN
(the URLs are in `index.html`). To swap in a new video, replace the `src`
on the `<video>` tag and the `poster` / `og:image` URLs.

## Hosting

Served by GitHub Pages from the `main` branch root. Turn it on once in
**Settings > Pages > Build and deployment > Deploy from a branch > main / (root)**.

## Programming the NFC chip

Write a single **URI record** containing the site's address (for example
`https://<owner>.github.io/bumbleton-hugs/`) to an NTAG213 / NTAG215 chip
with any NFC writing app (e.g. NFC Tools), then lock the tag so it can't
be overwritten. iPhones (XS and later) and NFC-enabled Android phones open
the link with no app needed.
