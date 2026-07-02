ISABEL & PAUL — SAVE THE DATE  ·  deploy folder
================================================

This folder is a self-contained website. Everything the page needs is (or should be) in here.

FILES
  index.html         The save-the-date page (rename kept as index.html so it serves at the root).
  og-preview.png     Link-preview image (shown when you paste the link in WhatsApp/iMessage/email).
  firebase.json      Firebase Hosting config (serves this folder).
  .firebaserc        Firebase project id (edit before deploying).
  README.txt         This file.

BEFORE YOU DEPLOY  (1 minute)
  1. Add the font: drop the Parfumerie Script font file into THIS folder, named
        ParfumerieScript.otf   (or .woff2 / .ttf — the page looks for any of those).
     If you skip this, the "&" just falls back to the Pinyon script — the page still works.
  2. (Optional) Link previews: after you know your live URL, open index.html and near the top set
        <meta property="og:url" content="https://YOUR-LIVE-URL/">
     and change og:image to the absolute URL:
        <meta property="og:image" content="https://YOUR-LIVE-URL/og-preview.png">
     Relative paths usually work, but absolute URLs are the most reliable for previews.


==================================================================
OPTION A — FIREBASE HOSTING   (recommended; you already use Firebase)
==================================================================
You do NOT need to buy a domain. Firebase gives you a free https address like
    https://your-site-name.web.app        (and .firebaseapp.com)
which is perfect for a save-the-date.

IMPORTANT: create a NEW, dedicated Firebase project for this — do NOT deploy into the
obj-0p (Lumina) project. Keep the wedding page completely separate from the app.

Steps (in a terminal, from inside this "site" folder):
  1. npm install -g firebase-tools        (once, if you don't have it)
  2. firebase login
  3. Create a project: https://console.firebase.google.com  ->  Add project
     (e.g. "isabel-paul-wedding"). Copy its Project ID.
  4. Put that Project ID into .firebaserc (replace REPLACE-WITH-YOUR-FIREBASE-PROJECT-ID).
  5. firebase deploy --only hosting
  -> It prints your live URL: https://<project-id>.web.app

Custom domain (optional, e.g. isabelandpaul.com):
  Firebase Console -> Hosting -> Add custom domain -> follow the DNS steps.


==================================================================
OPTION B — GITHUB PAGES   (also free, also no domain needed)
==================================================================
GitHub gives you a free https address like
    https://your-username.github.io/isabel-paul/     (no domain purchase needed)

Steps:
  1. Create a new repo on github.com, e.g. "isabel-paul".
  2. Upload the CONTENTS of this folder (index.html, og-preview.png, the font file)
     to the repo (drag-and-drop in the browser is fine). firebase.json/.firebaserc/README
     are harmless to include or you can leave them out.
  3. Repo -> Settings -> Pages -> Source: "Deploy from a branch" -> branch main / root -> Save.
  4. Wait ~1 min; your URL appears at the top of the Pages settings.

Custom domain (optional): Settings -> Pages -> Custom domain.


==================================================================
OPTION C — EVEN SIMPLER (drag-and-drop, no CLI)
==================================================================
  Cloudflare Pages  (dash.cloudflare.com -> Workers & Pages -> Create -> Pages -> Upload)
  or Netlify Drop   (app.netlify.com/drop)
  Just drag this whole folder onto the page; you get a live URL instantly.


TIPS
  * Test the link on a PHONE before sending — most guests open on mobile.
  * "Hidden": an unguessable URL is plenty for a save-the-date; you don't need a login.
  * To update later: change index.html and re-deploy / re-upload.
