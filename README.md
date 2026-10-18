# Soccer Sub Manager — installable app

This folder is the complete app. Put it on any website with HTTPS and coaches can install it on their tablet's home screen. It then opens full screen and works offline at the field.

## What's in the folder

| File | What it does |
| --- | --- |
| `index.html` | The app itself |
| `manifest.webmanifest` | App name, icon and colors the tablet uses when installing |
| `sw.js` | Offline support. Saves the app on the tablet so it opens without a connection |
| `icons/` | Home-screen, app and browser icons |

## 1. Put it online (one time)

The app has to be served over **https://** — tablets won't install it from a file or a plain `http://` address. Any static web host works. The quickest:

1. Go to **app.netlify.com/drop** and sign up for a free account (signing in keeps the site permanently and lets you update it).
2. Drag this whole folder onto the page.
3. Netlify gives you an address like `https://something.netlify.app`. You can rename it in Site settings, or connect your own domain later.

GitHub Pages and Cloudflare Pages work the same way if you prefer them.

## 2. Install it on a tablet

**iPad (Safari)**
1. Open the address in Safari.
2. Tap the **Share** button (square with an arrow).
3. Tap **Add to Home Screen**, then **Add**.

**Android tablet (Chrome)**
1. Open the address in Chrome.
2. Tap **Install App** in the yellow banner, or the browser menu → **Install app**.

Open the app once while online after installing so everything is saved for offline use. The app also shows these instructions in a banner until it's installed.

## 3. Publish an update

1. Change the app (`index.html`).
2. In `sw.js`, raise `VERSION` (for example `1.0.0` → `1.0.1`). In `index.html`, raise `APP_VERSION` to match.
3. Upload the folder again (on Netlify: your site → **Deploys** → drag the folder in).

Next time coaches open the app with a connection they'll see **"A new version is ready — Update Now"**. Teams, history and any game in progress are kept.

## Where coach data lives

Teams, game history and the game in progress stay on each tablet, in the app's own storage. Nothing is sent to your website. Coaches should use **Back Up All Teams** on the Team screen now and then, since deleting the app or clearing Safari data removes its storage.
