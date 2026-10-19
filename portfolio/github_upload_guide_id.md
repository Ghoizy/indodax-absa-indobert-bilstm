# Cara upload project ini ke GitHub

1. Ekstrak ZIP paket portfolio (jangan upload ZIP sebagai satu file ke GitHub).
2. Buka GitHub -> **New repository**. Nama yang disarankan: `indodax-absa-indobert-bilstm`.
3. Set **Public** jika sudah yakin semua materi aman dipublikasikan. Jangan centang *Add README* karena paket sudah memiliki README.
4. Buka terminal (PowerShell / Git Bash) di dalam folder hasil ekstraksi yang berisi `README.md`.
5. Jalankan:

```bash
git init
git add .
git commit -m "Add Indodax ABSA research portfolio"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/indodax-absa-indobert-bilstm.git
git push -u origin main
```

Ganti `YOUR_USERNAME` dengan username GitHub kamu. Jika Git sudah terpasang dan terminal telah login, perintah ini akan membuat project tampil di repository GitHub.

**Cek sebelum publish:** notebook tampil lengkap, chart di README terbaca, link docs tidak error, file mentah dan checkpoint tidak terunggah, serta status repository benar-benar Public jika hendak dibagikan.

**LinkedIn:** sesudah repo Public, edit teks di `portfolio/linkedin_post_en.md`, masukkan link GitHub asli, lalu buat **post biasa** (bukan harus Featured). Untuk rekam jejak jangka panjang, tambahkan juga di profil bagian **Projects** dengan konten dari `portfolio/linkedin_project_description_en.md`.
