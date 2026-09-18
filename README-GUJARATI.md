# ProfitNx CRM — Android App (APK) Setup

Aa project tamara live CRM (`https://pnxcrm.onrender.com`) ne native Android
app banavi ne aape chhe. Badha j functions/screens same j rahese, kem ke app
tamaru live CRM j andar load kare chhe — fakat browser address bar nathi dekhatu.

## Step 1: GitHub par repo banavo
1. https://github.com par jaao, "New repository" — naam aapo (jem ke `pnxcrm-app`).
2. Public rakho athva Private — banne chalse (Private rakhso to Actions minutes
   free tier ma limited hoy, pan aatla nana build mate koi vandho nahi).

## Step 2: Aa project push karo
Tamara computer par aa folder download karo, pachi terminal ma:

```
cd pnxcrm-app
git init
git add .
git commit -m "Initial ProfitNx CRM Android app"
git branch -M main
git remote add origin https://github.com/<TAMARU-USERNAME>/pnxcrm-app.git
git push -u origin main
```

## Step 3: APK automatic build thase
Push karta j GitHub Actions (`.github/workflows/build-apk.yml`) automatic
chalu thase. GitHub repo ma **Actions** tab par jaao → "Build ProfitNx CRM APK"
workflow par click karo → jyare green tick (✔) aave etle niche
**Artifacts** section ma `ProfitNx-CRM-debug-apk` zip file mali jase.
Ae zip download karo — andar `app-debug.apk` hase.

## Step 4: Mobile ma install karo
1. `app-debug.apk` file phone ma transfer karo (WhatsApp/Drive/USB — koi pan rite).
2. Phone Settings → Security → "Install unknown apps" ne apni file manager/browser
   mate ON karo (Android version pramane naam thodu alag hoy shake).
3. APK file par tap karine install karo.
4. App icon "ProfitNx CRM" name thi home screen par aavi jashe.

## Note
- Aa **debug build** che — testing/internal use mate barobar chhe. Google
  Play Store par publish karva mate signed **release build** joiye (keystore
  file banavvi pade) — ae alag step chhe, jyare joiye tyare kaho, hu setup kari aapish.
- App tamara live URL (`https://pnxcrm.onrender.com`) par depend chhe — etle
  jo Render service free-tier sleep thai jay to app kholta thodi var lagi
  shake (pehli request par server jage chhe). Paid plan par aa issue nathi.
- Camera/file upload, notifications mate permissions already manifest ma
  add karel chhe.
