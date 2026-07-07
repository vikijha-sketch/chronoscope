# Real photos in The Chronoscope

## What's automatic now

7 of the 14 rounds now pull a real, verified public-domain or Creative
Commons photo **directly from Wikimedia Commons** at runtime — no
download needed, no `images` folder required for these:

- 1440 — Gutenberg's press
- 1776 — Declaration of Independence (Trumbull painting)
- 1903 — Wright Flyer, first flight
- 1912 — RMS Titanic
- 1928 — Fleming's penicillin mould (CC BY-SA 4.0 — attribution link is shown under the photo automatically)
- 1931 — Empire State Building
- 1989 — Fall of the Berlin Wall

I found each of these filenames by hand and confirmed they exist on
Commons, so they should load reliably. If Wikimedia ever renames or
removes one, the game automatically falls back to that round's drawn
engraving — nothing breaks.

## What still needs a manual drop-in

For 7 rounds I couldn't confidently verify an exact, correctly-licensed
Commons filename, so rather than guess and risk a broken image, these
still use the local `images/` folder approach from before — just drop a
file with the matching name next to `chronoscope.html`:

```
images/
  ├── 1789-storming-bastille.jpg
  ├── 1876-telephone.jpg
  ├── 1936-bbc-television.jpg
  ├── 1986-chernobyl.jpg
  ├── 1991-world-wide-web.jpg
  └── 2007-first-iphone.jpg
```

(Note: 1789 actually points at a Commons file called "Prise de la
Bastille" as a best guess — I'm fairly but not fully confident that
exact filename is correct, so keep an eye on it and add a local file too
if it doesn't show up.)

Good places to look: Wikimedia Commons (check the license box on each
file page for "Public domain" or a Creative Commons license), or
nasa.gov for anything space-related. For the iPhone specifically, be a
bit more careful — most professional product photos of it are
copyrighted; look for a Commons-licensed photo taken by a Commons
contributor rather than an official Apple press photo.

Any round without a matching file just shows its engraving — the game
never shows a broken image icon.
