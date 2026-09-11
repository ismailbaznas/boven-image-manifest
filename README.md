# 🗄️ Boven Image — Disaster Recovery Manifest

Repositori ini menyimpan salinan lengkap metadata & URL arsip visual **Boven Image (Media Vault)** sebagai perlindungan independen dari ketergantungan database (*Database-Agnostic Disaster Recovery*).

---

## 📊 Status Arsip Terkini

- **Terakhir Disinkronkan:** `2026-09-11T16:30:31.359Z`
- **Total Media Foto:** **1102 media**
- **Total Organisasi:** **6 folder**
- **Total Program Kegiatan:** **25 program**
- **Storage Fisik Foto:** Google Blogger CDN (`lh3.googleusercontent.com`) — Blog ID `3348673630650024103`

---

## 📁 Struktur Data

- `data/media.json`: Seluruh rekaman media, ID (`boven-digoel-[N]`), URL foto asli (`s0`), SHA-256 hash, dan metadata.
- `data/organizations.json`: Daftar organisasi & konfigurasi sampul.
- `data/programs.json`: Hierarki program per organisasi.
- `data/summary.json`: Ringkasan statistik & timestamp sync.
- `sql/backup.sql`: Skrip SQL standar siap pakai untuk restore ke PostgreSQL, Supabase baru, SQLite, atau platform database lainnya.

---

## 🔄 Panduan Pemulihan (Disaster Recovery)

Jika database utama bermasalah:
1. **Restore ke PostgreSQL / Supabase Baru:**
   Jalankan file `sql/backup.sql` pada SQL editor database baru.
2. **Restore via JSON API:**
   Gunakan file `data/media.json` untuk mengimpor ulang seluruh katalog ke sistem baru tanpa perlu mengunggah ulang foto ke Blogger.

*Otomatis disinkronkan oleh Media Vault Engine.*
