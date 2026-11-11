# Seance — user guide

**Version 1.1.0 · PolyForm Noncommercial 1.0.0**

Seal a note with a passphrase, and open it later — or send the sealed text to someone who has the
passphrase.

## What it does

- **Seal**: a note plus a passphrase becomes a sealed text (base64) you can paste anywhere.
- **Open**: paste the sealed text, or open the `.txt` you were sent, plus the passphrase, and get the
  note back.
- Authenticated encryption, so **a wrong passphrase or altered text is rejected** rather than
  producing a plausible-looking wrong answer.
- Everything happens on your device; nothing is sent anywhere.

## How to use it well

1. Write the note, choose a strong passphrase, seal it.
2. **Send the text and the passphrase separately** — the text is useless alone, and that is the
   design. A sealed note and its passphrase in the same email is a lock with the key taped to it.
3. To open, paste the text or open the saved `.txt`, then enter the passphrase.

## Honest limits

- A passphrase-sealed note is **only as strong as the passphrase**. A short one is a short one no
  matter what the cipher is.
- "Opened once" is remembered **on this device** — it is a courtesy, not enforcement. A determined
  reader can clear storage or open the note elsewhere.
- It is **not a substitute for a vetted messaging app** for anything truly sensitive. It is a way to
  hand someone a note through a channel you do not trust, without trusting the channel.

## Licence

PolyForm Noncommercial 1.0.0. See [LICENSE](../LICENSE).
