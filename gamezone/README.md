GameZone README

This folder hosts small web-playable demos and (optionally) an Android APK for mobile distribution.

How to add your APK

1. Place your signed APK file in this folder and name it `mygame.apk`.
   - Path: `/gamezone/mygame.apk`
2. Serve the project with a static server (e.g., `python3 -m http.server 8000` from the project root).
3. Open `http://localhost:8000/gamezone/` and the "Download APK" button will be enabled if the file exists.

Notes

- The site uses a simple `fetch(..., { method: 'HEAD' })` check to detect APK availability. Some static servers may not allow HEAD requests — in that case the check may fail; you can still download the file by navigating directly to `/gamezone/mygame.apk`.
- For production distribution, consider uploading the APK to Google Play or an app distribution platform and linking to the store listing instead of hosting the APK directly.
- To add more mobile games, copy this card markup in `index.html` and point the download link to another APK file name.

Adding an icon (recommended)

- You can add an icon file for your mobile game so it appears in the GameZone listing. Place one of the following filenames in the same folder:
   - `mygame-icon.png` (preferred)
   - `mygame.png`
   - `icon.png`

- Recommended sizes: 512x512 (high-res) or 192x192 (web). Use PNG with a square aspect ratio and transparent background if possible.

- After adding the icon, reload `http://localhost:8000/gamezone/` and the site will detect and display it automatically.

Troubleshooting

- If the site cannot detect the file, your static server may not support HEAD requests. You can still verify the file by opening `http://localhost:8000/gamezone/mygame-icon.png` (or the filename you used) directly in the browser.
- For production distribution, consider using Google Play or an app hosting platform and point the download button at the store URL instead of hosting the APK directly.
