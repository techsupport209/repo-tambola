# Tambola (live, multiplayer)

Browser game for up to 60 players. Every player opens the same link on their own phone or laptop, joins with a name, and sees each number as the host calls it. State is shared through a free Firebase Realtime Database. There is no server and no build step.

## One-time setup (about 2 minutes)

1. Go to https://console.firebase.google.com and click **Add project** (name it anything, you can turn Analytics off).
2. In the left menu open **Build → Realtime Database → Create Database**. Pick any location and choose **Start in test mode**.
3. Copy the database URL shown at the top of the Data tab, for example `https://my-tambola-default-rtdb.firebaseio.com`.
4. (Already done for this repo.) The database URL is set in `index.html` at `window.TAMBOLA_FIREBASE_URL`.
5. In the GitHub repo go to **Settings → Pages**, choose **Deploy from a branch → main → / (root)** and save.
6. Open https://techsupport209.github.io/tambola/ .

## Playing
- **Host:** open the page, tap **Host login**, and enter a PIN. The first PIN entered becomes the host PIN for that game. Then use the Host tab to call numbers and award prizes.
- **Players:** open the same link, type a name, tap **Join game**. A ticket is assigned automatically. When a ticket qualifies for a prize, tap **Tell the host**.
- **Separate games:** add `#anyname` to the link (for example `.../tambola/#friday`) to run an independent game.

## Notes
- Test-mode rules are open to anyone who knows your database URL, and Firebase test mode expires after 30 days, so you will need to extend the rules then. The host PIN only stops other players from using the host controls in this page. It is not strong security, so use this for friendly games.
- Free Firebase plan limits are far above a 60-player game.
