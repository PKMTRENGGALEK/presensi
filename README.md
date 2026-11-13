# Presensi JKA — APK Android (Capacitor)

Wrapper Android untuk website Presensi PT Jaya Kusuma Arum.

**Logo resmi** sudah dimasukkan ke `resources/`.

## Cara pakai

### 1. Ganti URL domain
Edit `capacitor.config.json`:

```json
"url": "https://domain-anda.com/presensi/pegawai/",
"allowNavigation": [
  "https://domain-anda.com/*"
]
```

Atau isi langsung saat Run workflow di GitHub Actions.

### 2. Upload ke GitHub
```bash
unzip presensi-apk-github.zip
cd jka-apk-final   # atau nama folder hasil extract
git init
git add .
git commit -m "Presensi JKA APK wrapper"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

### 3. Build APK
1. Buka repo → tab **Actions**
2. Pilih **Build Android APK**
3. Klik **Run workflow**
4. (Opsional) isi URL server
5. Tunggu selesai → download artifact **Presensi-JKA-APK**

### 4. Install di HP
- Izinkan "Install dari sumber tidak dikenal"
- Buka file `.apk` → Install

## Catatan penting

| Item | Keterangan |
|------|------------|
| Update website | **Otomatis** ikut berubah di APK (karena load dari server) |
| Logo / Splash | Hanya berubah kalau build ulang APK |
| GPS & Notifikasi | Permission sudah ditambahkan |
| Domain | **Wajib HTTPS** |

## Struktur
```
├── package.json
├── capacitor.config.json   ← ganti URL di sini
├── resources/
│   ├── icon.png            ← logo resmi JKA
│   └── splash.png
├── www/index.html
└── .github/workflows/build-apk.yml
```
