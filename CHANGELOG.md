# Changelog

## 1.1.0 — 2026-11-10

### Fixed — sealing did nothing, and the screenshot was of the 404 page

**The app never loaded the kit that seals.** `docs/app.html` loaded `web-kit.js` and called
`CryptoKit.sealString(...)` — a library that was in no `<script>` tag and in no file in the
repository. The click handler threw `ReferenceError: CryptoKit is not defined` before the promise
chain began, so the status sat on *Sealing…* forever and no sealed text ever appeared. That is
exactly what a user saw: sealing starts, nothing comes out.

- `crypto-kit.js` is vendored into `docs/` and loaded before the app's own script.
- The app now says so out loud when the kit is missing, and when the browser refuses to encrypt on
  a `file://` page (Web Crypto needs https or localhost) instead of hanging on a spinner.

**You could not send the result, or open one you were sent.**

- **Download `.txt`** — the sealed text is a file as well as a paste. Same bytes.
- **Open a file** — the Open tab takes the `.txt` you were sent, not only a paste.
- The status line says what to do next: *send this text and the passphrase by two different routes.*

**The screenshot was the 404 page.** `docs/shot.png` was a picture of *"404 — That page is not
here."*, used as the README image and the landing hero. It is now a real capture of the app with a
note sealed, taken from the running page.

**The page now says what the tool is for** in the first line: a message you can send that cannot be
read twice — for a password, a handover, a last word — and the four steps, including what the
person receiving it does.
