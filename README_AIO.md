# 🎵 TikTok Session Manager - All-in-One Solution

**Login & Grab Session dalam 1 Aplikasi!** 
Solusi paling mudah untuk Android users - No extension needed!

---

## 🚀 Quick Start (1 Menit)

### Method 1: Hosting Online (Recommended)

**Netlify Drop (PALING MUDAH):**

1. Download semua file
2. Zip file: `app.html`, `webview.html`
3. Buka: https://app.netlify.com/drop
4. Drag & drop zip file
5. Dapat URL instant! 🎉

**GitHub Pages:**

```bash
# Upload ke GitHub
git init
git add .
git commit -m "TikTok Session Manager"
git remote add origin https://github.com/username/tiktok-manager.git
git push -u origin main

# Enable Pages di Settings → Pages
# Akses: https://username.github.io/tiktok-manager
```

### Method 2: Local Testing

**Termux:**
```bash
cd ~/storage/downloads/tiktok-manager
python -m http.server 8000

# Akses: http://localhost:8000/app.html
```

**PC/Laptop:**
```bash
python3 -m http.server 8000
# atau
npx serve
```

---

## 📱 2 Versi Aplikasi

### 1️⃣ **app.html** - Full Featured App

**Fitur:**
- ✅ 3 Tab: Browser Login, Manual Login, My Accounts
- ✅ Built-in TikTok iframe
- ✅ Auto-detect login status
- ✅ Save unlimited accounts
- ✅ Export all sessions
- ✅ Beautiful UI with animations

**Best for:**
- Multiple accounts management
- Regular users
- Beginners

**Cara Pakai:**
1. Buka `app.html`
2. Tab "Browser Login" → "Open TikTok"
3. Login di iframe
4. Klik "Grab Session"
5. Done! ✅

### 2️⃣ **webview.html** - Simple Webview

**Fitur:**
- ✅ Full-screen TikTok webview
- ✅ Floating grab button
- ✅ Quick copy & save
- ✅ Lightweight & fast
- ✅ Auto cookie extraction

**Best for:**
- Quick one-time grabs
- Power users
- Fast workflow

**Cara Pakai:**
1. Buka `webview.html`
2. Login TikTok (full screen)
3. Klik floating button (🎯)
4. Done! ✅

---

## 🎯 Comparison

| Feature | app.html | webview.html |
|---------|----------|--------------|
| UI Complexity | ⭐⭐⭐⭐ | ⭐⭐ |
| Speed | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Features | Full | Basic |
| Account Management | ✅ | ❌ |
| Manual Login | ✅ | ❌ |
| Export | ✅ | ❌ |
| Beginner Friendly | ✅ | Moderate |

**Rekomendasi:**
- **New users:** Start with `app.html`
- **Quick grab:** Use `webview.html`
- **Multiple accounts:** Use `app.html`

---

## 📖 Step-by-Step Tutorial

### Tutorial 1: Using app.html

**Browser Login Method:**

1. **Open App**
   ```
   https://your-url.netlify.app/app.html
   ```

2. **Click "Open TikTok"**
   - Iframe TikTok akan muncul
   - Halaman login TikTok terbuka

3. **Login**
   - Masukkan username/email & password
   - Atau scan QR code
   - Tunggu sampai login berhasil

4. **Grab Session**
   - Klik tombol "🎯 Grab Session Now"
   - Session otomatis ke-extract
   - Hasil muncul di bawah

5. **Save**
   - Session otomatis tersimpan
   - Cek di tab "My Accounts"

**Manual Login Method:**

1. Tab "Manual Login"
2. Masukkan username & password
3. Klik "Login & Grab Session"
4. API akan login langsung ke TikTok
5. Session otomatis tersimpan

**View Saved Accounts:**

1. Tab "My Accounts"
2. Lihat semua akun tersimpan
3. Copy session per-akun
4. Export all ke TXT
5. Delete akun yang tidak perlu

### Tutorial 2: Using webview.html

1. **Open**
   ```
   https://your-url.netlify.app/webview.html
   ```

2. **Login**
   - Full-screen TikTok
   - Login seperti biasa
   - No restrictions!

3. **Grab**
   - Klik floating button (🎯) di kanan bawah
   - Atau klik "Grab" di top bar

4. **Result**
   - Modal muncul dengan session data
   - Copy atau Save

5. **Done!**
   - Session tersimpan di localStorage
   - Bisa grab lagi untuk akun lain

---

## 🔧 Troubleshooting

### ❌ "Cannot access cookies"

**Solusi:**

1. **Enable Developer Options di Chrome:**
   ```
   chrome://flags
   Search: "SameSite"
   Disable semua yang related
   ```

2. **Use Manual Method:**
   - App.html → Tab "Manual Login"
   - Masukkan credentials langsung

3. **Use Console Extraction:**
   - Webview → Inspect (F12)
   - Console → `document.cookie`
   - Copy hasilnya
   - Paste di modal manual

### ❌ "Iframe blocked by CORS"

**Solusi:**

- **Method 1:** Host di HTTPS (bukan HTTP)
- **Method 2:** Use `webview.html` instead
- **Method 3:** Open TikTok in new tab, manual grab

### ❌ "Login page not loading"

**Solusi:**

1. Check internet connection
2. Clear browser cache
3. Try different browser
4. Reload iframe (🔄 button)

### ❌ "Session not found"

**Solusi:**

- Make sure you're logged in
- Wait 5 seconds after login
- Try grabbing again
- Use manual method

---

## 💡 Pro Tips

### 1. Multi-Account Management

```javascript
// Export format untuk bot automation
accounts.forEach(acc => {
  console.log(`${acc.username}:${acc.sessionid}`);
});
```

### 2. Auto-Login Script

```javascript
// Simpan ini di bookmark untuk auto-fill
javascript:(function(){
  document.querySelector('input[name="username"]').value='YOUR_USER';
  document.querySelector('input[name="password"]').value='YOUR_PASS';
  document.querySelector('button[type="submit"]').click();
})();
```

### 3. Bulk Import

```javascript
// Import multiple accounts dari list
const list = `
user1:pass1
user2:pass2
user3:pass3
`;

list.split('\n').forEach(line => {
  const [user, pass] = line.split(':');
  // Process each account
});
```

### 4. Session Validation

```javascript
// Check if session still valid
async function validateSession(sessionid) {
  const response = await fetch('https://www.tiktok.com/api/user/detail/', {
    headers: {
      'Cookie': `sessionid=${sessionid}`
    }
  });
  return response.ok;
}
```

### 5. Auto-Export Schedule

```javascript
// Auto export setiap 7 hari
setInterval(() => {
  exportAllAccounts();
}, 7 * 24 * 60 * 60 * 1000);
```

---

## 🔒 Security Best Practices

### ✅ DO:

- Store sessions encrypted
- Use HTTPS hosting only
- Logout after grabbing
- Clear browser data regularly
- Export to secure location
- Use strong passwords

### ❌ DON'T:

- Share sessionid publicly
- Upload sessions to public repos
- Use on public WiFi
- Save in cloud without encryption
- Share account access
- Keep expired sessions

---

## 📊 Features Comparison

| Feature | Desktop Extension | Mobile PWA | This App |
|---------|-------------------|------------|----------|
| No Install | ❌ | ✅ | ✅ |
| Direct Login | ❌ | ❌ | ✅ |
| Cross-Platform | ❌ | ✅ | ✅ |
| Account Manager | ✅ | ⭐⭐ | ✅ |
| Auto-Grab | ✅ | ❌ | ✅ |
| Offline Support | ✅ | ✅ | ❌ |
| Easy Deploy | ❌ | Moderate | ✅ |

---

## 🚀 Advanced Usage

### Deploy to Multiple Platforms

**Vercel:**
```bash
npm i -g vercel
vercel deploy
```

**Firebase:**
```bash
firebase init hosting
firebase deploy
```

**GitHub Pages:**
```bash
# Already covered above
```

### Custom Domain

1. Deploy to Netlify/Vercel
2. Add custom domain in dashboard
3. Update DNS records
4. Access: `tiktok.yourdomain.com`

### Add Authentication

```javascript
// Add password protection
const SECRET = 'your-password';
const password = prompt('Enter password:');
if (password !== SECRET) {
  alert('Access denied!');
  window.location = 'about:blank';
}
```

---

## 📱 Mobile-Specific Tips

### Chrome Android

1. **Enable Desktop Site:**
   - Menu → Desktop site ✓
   - Better compatibility

2. **Install as App:**
   - Menu → Add to Home screen
   - Opens like native app

3. **Full Screen Mode:**
   - Scroll down = auto hide address bar
   - More screen space

### Firefox Android

1. **Request Desktop Site** for better iframe support
2. **Reader Mode** disabled for app functionality

### Samsung Internet

1. Works out of the box
2. Better privacy features
3. Biometric login support

---

## 🆘 Support

**Need Help?**

- **Telegram:** @rsmediazero
- **GitHub Issues:** Open issue dengan screenshot
- **Discord:** Coming soon

**Report Bugs:**
- Include browser version
- Android version
- Screenshot of error
- Steps to reproduce

---

## 📄 License

MIT License - Free to use, modify, and distribute

---

## 🎉 Credits

- **Developer:** rsmediazero
- **Telegram:** @rsmediazero
- **GitHub:** github.com/rsmediazero

**Special Thanks:**
- TikTok API community
- Open source contributors
- Beta testers

---

**Made with ❤️ for the automation community**

🎵 Happy Grabbing! 🚀