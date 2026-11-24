# CanalSweep PWA

Files: index.html, manifest.json, service-worker.js, icon-192.png, icon-512.png

## Test on your computer
Service workers need http://localhost or https. Do not double-click index.html.
1. Open a terminal in this folder.
2. Run: python3 -m http.server 8000
3. Open http://localhost:8000 in Chrome.
4. DevTools > Application > Manifest / Service Workers to check them.

## Publish with GitHub Pages (free, HTTPS)
1. Create a GitHub repository (for example canalsweep).
2. Upload all five files to the repository root.
3. Settings > Pages > Source: Deploy from a branch > main > / (root) > Save.
4. After a minute your app is at https://YOUR-NAME.github.io/canalsweep/

## Install on the phone
Open the link in Chrome on Android, then menu > Install app (or Add to Home screen).

## When you change a file
Edit the file, then change CACHE in service-worker.js (v1 to v2) so phones update.

## Water pH (what is in this version)
The app shows a pH value, a colour scale, and a rating for people: Normal range, Slightly out of range, Out of range, Dangerous. The limits are settings you can change (Calculation settings).
- WHO gives no health-based value for pH. 6.5 to 8.5 is the range usually used as optimum for drinking water.
- Very low or very high pH can irritate skin and eyes.
- pH alone does not make canal water safe. Do not drink canal water untreated.
In the demo the pH comes from a slider. On the real boat it comes from a pH probe:
1. Use an analog pH probe module on an ESP32 analog pin. Average many readings, because they are noisy.
2. Calibrate with buffer solutions (for example pH 4 and pH 7) before each field day, and keep the probe wet between uses.
3. Send the value to Firebase and show it in the app instead of the slider.
Check the ESP32 ADC range and the probe module datasheet before wiring.

## Microplastics (what is in this version)
The microplastics card is a simulation of a filter sample that a camera scans. It counts particles by shape (fibre, fragment, film, bead) and size (1-5 mm, under 1 mm) and shows particles per litre.
- Microplastics are plastic particles smaller than 5 mm.
- A boat camera can only see the larger particles on a filtered sample. Very small ones need a microscope or lab analysis, and a lab must confirm the material is plastic.
- WHO (2019) found insufficient evidence of a health risk at current levels. The levels in the app (Low / Moderate / High) only compare your own samples. Change the limits in Calculation settings.
- Sampling methods differ a lot between studies, so only compare samples taken the same way (same volume, same filter).
