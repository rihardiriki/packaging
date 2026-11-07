# PM – Permintaan Packaging

PWA (Progressive Web App) untuk membuat permintaan material packing per SPK. Bisa di-install di HP/PC dan tetap jalan offline.

## Isi folder

| File | Fungsi |
|---|---|
| `index.html` | Aplikasi utama |
| `manifest.json` | Konfigurasi install (nama, ikon, warna) |
| `sw.js` | Service worker (cache & offline) |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` | Ikon aplikasi |
| `logo.svg`, `logo-mark.svg`, `logo-mark-transparan.png`, `logo-horizontal.png`, `logo-horizontal.svg`, `favicon-32.png` | Logo (SVG & PNG): ikon, tanpa latar, dan versi horizontal dengan teks |
| `.github/workflows/pages.yml` | Deploy otomatis ke GitHub Pages |

## Upload ke GitHub

```bash
cd pm-packaging-pwa
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USERNAME/pm-packaging-pwa.git
git push -u origin main
```

Atau lewat web: buat repo baru → **Add file → Upload files** → seret semua isi folder (termasuk folder `.github`).

## Aktifkan GitHub Pages

1. Buka repo → **Settings → Pages**
2. Pada **Source**, pilih **GitHub Actions**
3. Tunggu proses di tab **Actions** selesai
4. Aplikasi tersedia di `https://USERNAME.github.io/pm-packaging-pwa/`

## Install di HP

- **Android (Chrome):** buka link → menu ⋮ → **Install app / Tambahkan ke layar utama**
- **iPhone (Safari):** buka link → tombol Share → **Add to Home Screen**

## Update aplikasi

Setelah mengubah `index.html`, naikkan `VERSION` di `sw.js` (mis. `v1` → `v2`) lalu push, supaya cache di HP pengguna ikut diperbarui.

> Service worker hanya berjalan di HTTPS (GitHub Pages sudah HTTPS) atau `localhost`.
