SAI ANU FURNITURE — SECURE ADMIN SETUP STARTER

IMPORTANT: This folder provides the secure Firebase Authentication + Firestore/Storage rules starter. It is NOT yet a live, configured backend. Do not publish it and assume login works until you complete the Firebase setup below and deploy the rules.

1) Create a Firebase project at https://console.firebase.google.com/
2) Add a Web App and copy its Firebase config into firebase-config.js (copy firebase-config.example.js first). The web config is not a password; never put service-account keys in this website.
3) In Firebase Authentication, enable Email/Password. Create your owner account using your chosen email and a NEW unique password. The password shared in chat should be changed and must not be reused.
4) Sign in once, then copy the owner's Firebase Authentication UID from Authentication > Users.
5) Replace REPLACE_WITH_OWNER_UID in firestore.rules and storage.rules with that exact UID. Deploy both rules using Firebase CLI or the Firebase console.
6) Host the secure-admin folder on HTTPS. Open admin-login.html. The dashboard checks Firebase login and only allows the owner UID.
7) Test with a second non-admin account: it must be denied access. Never leave Firestore/Storage in test mode.

FILES
- admin-login.html / admin.js: Firebase email/password login and owner-only gate.
- firebase-config.example.js: template; copy to firebase-config.js and add your project's web config.
- firestore.rules / storage.rules: owner-only admin data and product/customer-upload storage rules.

LIMITATION
This starter secures the separate admin entry and database/storage rules. It does not yet connect every form/product widget in the preview customer site to Firestore. That integration and deployment are required before customer orders, service photos, and admin product changes sync live. GitHub Pages can host the static pages, but Firebase must provide authentication, database, and file storage.
