# 📱 Nota Service HP – Aplikasi Manajemen Service HP

Aplikasi **Nota Service HP** adalah sistem manajemen service handphone berbasis web yang dikemas menjadi aplikasi Android native menggunakan **Capacitor**. Aplikasi ini memungkinkan toko service HP untuk membuat, menyimpan, dan mengelola nota penerimaan, hasil diagnosa, nota selesai, dan nota pengambilan secara digital. Fitur unggulan termasuk cetak ke printer thermal Bluetooth, kirim nota via WhatsApp (teks/gambar), dan riwayat service lengkap.

## ✨ Fitur Utama

- **Alur Service 4 Tahap** – Penerimaan → Diagnosa → Selesai → Ambil/Batal
- **Nota Digital** – Tampilan nota yang rapi dengan logo toko, detail pelanggan, kelengkapan, kondisi fisik, dan biaya
- **Cetak Thermal Bluetooth** – Dukungan printer thermal 58/75/80 mm via Bluetooth (Capacitor Bluetooth LE)
- **Kirim Nota via WhatsApp** – Kirim sebagai teks (template custom) atau gambar
- **Ekspor PDF** – Simpan nota sebagai file PDF
- **Manajemen Riwayat** – Cari, filter, lihat riwayat, statistik ringkasan
- **Backup & Restore** – Cadangkan data ke file JSON dan pulihkan kapan saja
- **Mode Gelap & Pengaturan Toko** – Customisasi nama toko, logo, warna, footer, syarat & ketentuan
- **Auto Follow-up WA** – Kirim notifikasi otomatis saat service selesai atau diambil
- **Offline First** – Data disimpan di IndexedDB, tetap berfungsi tanpa internet

## 🛠 Teknologi yang Digunakan

| Teknologi | Deskripsi |
|-----------|-----------|
| **HTML5 / CSS3 / JavaScript** | Antarmuka dan logika aplikasi |
| **Capacitor** | Wrapper untuk menjadikan aplikasi Android native |
| **IndexedDB** | Penyimpanan data lokal |
| **html2canvas + jsPDF** | Konversi nota ke gambar/PDF |
| **esc-pos-encoder** | Encoding data untuk printer thermal |
| **Web Bluetooth API / Capacitor Bluetooth LE** | Cetak ke printer thermal |
| **GitHub Actions** | CI/CD untuk build otomatis APK |

## 📦 Prasyarat untuk Build Lokal

Jika ingin membangun sendiri secara lokal, pastikan sudah terinstall:

- [Node.js](https://nodejs.org/) (versi 18 atau lebih baru)
- [Android Studio](https://developer.android.com/studio) (termasuk Android SDK, build tools)
- Java JDK 11

## 🚀 Build APK dengan GitHub Actions (Otomatis)

Repositori ini telah dilengkapi dengan workflow GitHub Actions yang akan membangun APK setiap kali ada push ke branch `main`.

1. **Fork atau clone repositori** ini.
2. **Push** ke branch `main`.
3. Buka tab **Actions** di repositori GitHub.
4. Pilih workflow **Build Android APK**.
5. Setelah selesai, unduh artefak `app-debug.zip` yang berisi file APK.

## 🖥️ Build Lokal (Opsional)

Jika ingin membangun sendiri di komputer:

```bash
# Clone repositori
git clone https://github.com/username/nota-service-hp.git
cd nota-service-hp

# Install dependensi
npm install

# Tambahkan platform Android
npx cap add android

# Sinkronkan file web ke proyek Android
npx cap sync

# Buka proyek di Android Studio
npx cap open android

# Di Android Studio, build APK (Build > Build Bundle(s) / APK(s) > Build APK(s))
