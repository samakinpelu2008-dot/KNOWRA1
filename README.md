# Knowra - public site (PWA)

Files: index.html (everything inline), manifest.json, sw.js, assets/ (icons).
Upload ALL of them to the root of your GitHub Pages repo (or Vercel).

## Before publishing
1. Open index.html, find SITE_CONFIG near the top of the script:
   - supportEmail  -> your customer support email
   - studioUrl     -> your SYRIX Studio website link
2. Firebase console:
   - Authentication > Sign-in method > enable Email/Password
   - Authentication > Settings > Authorized domains > add your site domain
     (e.g. yourname.github.io)
   - Firestore Database > Rules > paste firestore.rules > Publish
   - No Storage needed. Articles AND books are saved in Firestore.
3. Make yourself admin (one time):
   - Open the site, create an account.
   - Firestore > users > your document > change role from "contributor" to "admin".
   - Then use the separate Admin Studio to approve submissions and publish.

## Notes
- Books: PDF/EPUB up to 5 MB, stored as chunks in Firestore.
- No Firestore index is needed (queries are simple).
- To release an update, bump VERSION in sw.js.
