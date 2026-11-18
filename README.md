# Crux

A web app for your iPhone that tracks lifting, climbing, food, weight and steps. Gemini estimates calories and macros from a photo or a description, and a coach tab gives advice based on your goals and logs.

It installs to your home screen from Safari and opens full-screen like a normal app. All your data is saved on your phone, not on GitHub.

## Put it online with GitHub Pages

1. Unzip `crux-app.zip`. You'll get a `crux-app` folder with `index.html`, `app.js`, `styles.css`, `sw.js`, `manifest.webmanifest`, this README and an `icons` folder.
2. On github.com, click **+** (top right) > **New repository**. Name it `crux-app`, choose **Public**, leave "Add a README file" unticked, and click **Create repository**. (Free GitHub accounts can only publish Pages sites from public repositories. Nothing private is in these files.)
3. Click **uploading an existing file**. Open the `crux-app` folder, select everything inside it (including the `icons` folder) and drag it onto the page. Click **Commit changes**.
4. Go to **Settings** > **Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then click **Save**.
5. Wait a minute or two and refresh. The page shows "Your site is live at" with a link like `https://YOUR-USERNAME.github.io/crux-app/`.

## Install it on your iPhone

1. Open that link in **Safari** on your iPhone.
2. Tap the **Share** button, scroll down and tap **Add to Home Screen**, then **Add**.
3. Open Crux from the new home screen icon (not from Safari, which keeps separate storage) and fill in your details.
4. Get a free Gemini key at aistudio.google.com > **Get API key** > **Create API key**. Paste it into Crux's setup screen and tap **Test connection**.

## Updating

Upload changed files to the same repository (Add file > Upload files) and commit. The app picks up the new version the next time you open it with an internet connection. If you change any file, also bump `VERSION` at the top of `sw.js` so offline copies refresh.

## Good to know

- **Back up now and then.** Settings > Save backup exports a file you can keep in Files or iCloud Drive. Deleting the home screen icon deletes your logs.
- **Steps are entered by hand.** Web apps can't read Apple Health, so copy the number from the Health app. "Past days" on the Today tab lets you fill in days you missed.
- **Your Gemini key stays on your phone.** It's only sent to Google when Crux asks Gemini something.
- **Estimates are estimates.** Calorie burn can be off by 20% or more either way; use the trends.

## How the numbers work

- Resting energy (BMR): Mifflin-St Jeor from sex, age, height and your latest weigh-in.
- Everyday burn: BMR × 1.2 for a desk job (1.3 or 1.45 if you pick a more active day).
- Workouts: MET × body weight × hours (lifting 3.5 to 6, climbing 5 to 7.5).
- Steps: each step above 5,000 adds about 0.0005 kcal per kg of body weight.
- Targets: estimated burn plus a goal adjustment (−450 lose fat, −200 recomp, +250 build muscle), never below BMR. Protein 1.6 to 2.0 g per kg, fat 25% of calories, carbs the rest.
- Strength: estimated 1-rep max = weight × (1 + reps / 30).
