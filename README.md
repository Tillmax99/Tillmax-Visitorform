# TILLMAX Booth Enquiry Form

Static site (`index.html`). Visitors scan a QR code, fill the form, the lead is saved to Firestore, then WhatsApp opens with the message ready.

## 1. Firebase
1. Firebase console > open (or create) a project > Build > Firestore Database > Create database.
2. Firestore > Rules > paste `firestore.rules` > Publish.
3. Project settings > Your apps > add a Web app (</>) > copy the config.
4. Paste it into `firebaseConfig` near the top of the script in `index.html`.
   (The web config is not secret; the rules are what protect your data.)

Leads appear in Firestore under `booth_leads` (name, contact, requirements, booth, createdAt).

## 2. GitHub
```
git init
git add .
git commit -m "Booth enquiry form"
git branch -M main
git remote add origin https://github.com/<you>/booth-form.git
git push -u origin main
```

## 3. Deploy (auto-deploys on every push)
Vercel: Add New > Project > import the GitHub repo > Framework: Other > Deploy.
Your live URL (e.g. https://booth-form.vercel.app) is what the QR code must point to.

## 4. QR code
Generate a QR for the live URL. Optional: `?booth=Colombo%20Expo` records which booth the lead came from.
