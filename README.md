# 🎬 Meron na ba ako? - Cinematic Web Experience

This is a customized, interactive, dual-path cinematic web project. It features background audio synchronization, dynamic CSS animations, hidden menus, and a strict "lockdown" security system for incorrect password attempts.

## ✨ Features
* **Dual-Path Storytelling:** A "Normal" path and a highly classified "Secret" path.
* **Cinematic Audio Sync:** Lyrics are timed perfectly to the millisecond with background music.
* **Security Lockdown System:** Incorrect passwords trigger a 1-hour or 5-hour localized "ban" using `localStorage`, complete with a terrifying red timer screen.
* **Secret Admin Backdoor:** A hidden bypass to instantly remove the ban.
* **Obfuscated Source Code:** Passwords and secret lyrics are hidden using Base64 encoding so visitors cannot read them by inspecting the GitHub code.

---

## 🚀 How to Setup & Host (Free via GitHub Pages)

1. **Upload your files:** Ensure these 3 files are in your repository:
   * `index.html` (The main code)
   * `ikawlang.mp3` (The normal background music)
   * `kalapastangan.mp3` (The secret cinematic music)
2. **Turn on GitHub Pages:**
   * Go to your repository **Settings** -> **Pages**.
   * Under "Build and deployment", set the source to **Deploy from a branch**.
   * Select your main branch (e.g., `main` or `daipakami`) and click **Save**.
3. **Wait 2 minutes**, and your site will be live!

---

## 🔐 How to Hide Text & Change Passwords (Base64)

Because GitHub Pages hosts "frontend" code, anyone can right-click and view your source code. To hide the secret names and lyrics, this project uses **Base64 Encoding** to scramble the text.

### How to Scramble (Encode) new text:
You can do this right in your browser!
1. Open a new tab in Chrome, right-click anywhere, and click **Inspect** (or press `F12`).
2. Click the **Console** tab at the top.
3. Type `btoa("your secret text")` and press **Enter**.
   * *Example:* `btoa("kath")` outputs `"a2F0aA=="`
4. Copy the scrambled code.

### Where to change the passwords in `index.html`:
Scroll down to the JavaScript section near the bottom of the file.

**For the first login prompt:**
Find `function checkName()`. Replace the scrambled code with your new lowercase encoded password.
```javascript
// Example: "kath"
if (btoa(userInput) === "a2F0aA==") {
