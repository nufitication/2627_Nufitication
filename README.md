# 2627Nufitication

Website resmi **Nufitication** (SMPIT Nurul Fikri): gabungan website informasi bertema Wonka dan aplikasi pendaftaran online, dalam satu halaman.

| Bagian | Isi |
|---|---|
| Beranda | Golden Ticket + hitung mundur, Tentang, Jadwal, Cabang Lomba (biaya & kuota langsung dari sistem), Alur & Persyaratan, Bazar UMKM, FAQ, Kontak & Sponsor, Galeri |
| Formulir | Pendaftaran lomba, pendaftaran tenant bazar, cek status, perbaikan berkas |
| Mesin | Google Apps Script (`API_URL` di `index.html`), sama dengan aplikasi sebelumnya |

## Cara pasang (GitHub Pages)

1. Buat repository baru bernama **2627Nufitication** di akun `nufitication` (Public).
2. **Add file → Upload files**, unggah: `index.html`, `404.html`, `.nojekyll`, `README.md`.
   (`.nojekyll` tersembunyi di Mac/Windows: tampilkan file tersembunyi dulu, atau buat lewat **Add file → Create new file** bernama `.nojekyll` dan biarkan kosong.)
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch `main`, folder `/ (root)` → Save.
4. Tunggu 1–2 menit. Alamatnya: **https://nufitication.github.io/2627Nufitication/**

## Setelah online

1. **Apps Script → Pengaturan Aplikasi → LINK_PUBLIK** diisi `https://nufitication.github.io/2627Nufitication/` supaya link cek status dan perbaikan berkas di email mengarah ke website baru.
2. **WordPress** (`smpit.nurulfikri.sch.id/nufitication`): ganti isi halaman dengan pengalih berikut (blok *HTML Khusus*):

   ```html
   <meta http-equiv="refresh" content="0;url=https://nufitication.github.io/2627Nufitication/">
   <script>location.replace('https://nufitication.github.io/2627Nufitication/');</script>
   <p style="text-align:center;padding:40px">Mengalihkan ke <a href="https://nufitication.github.io/2627Nufitication/">website Nufitication</a>…</p>
   ```

3. **Repo lama `nufitication2026`** (opsional): ganti `index.html`-nya dengan pengalih yang sama, supaya link lama yang sudah tersebar tetap berfungsi.

## Tautan khusus

| Alamat | Fungsi |
|---|---|
| `…/2627Nufitication/#daftar` | Langsung membuka formulir pendaftaran lomba |
| `…/2627Nufitication/#bazar` | Langsung ke info Bazar UMKM |
| `…/2627Nufitication/#status` | Langsung ke Cek Status |
| `…/2627Nufitication/#competitions-section` | Langsung ke daftar cabang lomba |

## Catatan

- Gambar, video, dan musik latar masih diambil dari media WordPress (`smpit.nurulfikri.sch.id/wp-content/uploads/…`). Jangan hapus file tersebut dari Media WordPress.
- Musik latar sementara memakai soundtrack Wonka; ganti URL di tag `<audio id="bg-music">` bila sudah ada musik bebas lisensi.
- Data lomba (biaya, kuota, juknis, deskripsi) diatur dari dashboard panitia (menu Cabang Lomba). Kartu lomba bawaan di HTML hanya tampil sebentar sebelum data dimuat.
- Maskot kartu lomba dicocokkan dari nama lomba (`LOMBA_TEMA` di `index.html`). Lomba baru yang namanya tidak cocok memakai gambar Golden Ticket.
- Dashboard panitia tetap di Apps Script (tautan *Login Panitia* di footer).
