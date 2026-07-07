# Turning The Chronoscope into an Android app

## What I built just now

The game is now a proper **PWA** (Progressive Web App):

- `manifest.json` — tells Android/Chrome this is an installable app, with
  a name, icon, and "standalone" mode (no browser address bar)
- `service-worker.js` — caches the game shell so it works offline after
  the first load
- `icons/` — a home-screen icon in the game's brass/parchment style
- `chronoscope.html` — updated to link the manifest and register the
  service worker

**What this gets you today:** open the page in Chrome on Android, tap the
menu → "Add to Home Screen" (or Chrome may prompt automatically), and it
installs as a real app icon that opens full-screen, no browser chrome,
and keeps working without a connection. This is genuinely how a lot of
simple Android games and utilities ship.

**What this doesn't get you:** a `.apk` file, or a listing on the Play
Store. For that, the files need to be hosted somewhere on the web first
— Android can't install a PWA straight from a folder on your computer.

## Why I can't build the actual .apk here

A real Android package needs the Android SDK and Gradle build tools,
which aren't available in the environment I run in — I don't have a way
to compile one for you directly, and I didn't want to just claim I did.

## The easiest real path: PWABuilder (free, no coding)

1. **Host the files somewhere public.** The simplest free option is
   GitHub Pages:
   - Create a new GitHub repo, upload everything in the zip I gave you
     (`chronoscope.html`, `manifest.json`, `service-worker.js`, `icons/`)
   - In the repo Settings → Pages, enable Pages from the main branch
   - You'll get a URL like `https://yourname.github.io/chronoscope/chronoscope.html`
2. Go to **pwabuilder.com**, paste that URL in, and let it scan the site
3. Click the **Android** package option — it generates a signed `.apk`
   (or `.aab` for Play Store submission) you can download directly
4. Install the `.apk` on any Android phone (enable "install unknown apps"
   for your browser/file manager first), or upload the `.aab` to Google
   Play Console if you want to publish it properly

This is the same pipeline real companies use for lightweight
"wrapped web app" Android releases — it's not a shortcut or a hack.

## If you'd rather I generate a native project instead

I can also write out a minimal Android Studio project (a WebView wrapping
this HTML file, as a proper Kotlin/Gradle project) that you'd compile
yourself in Android Studio. It's more setup on your end than PWABuilder,
but gives you full source control over the native shell. Let me know if
you'd like that instead — it's a different set of files than what's in
the zip above.
