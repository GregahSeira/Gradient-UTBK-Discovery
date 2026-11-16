# Gradient UTBK: Share Progress Belajar (discovery prototype)

Prototype satu file (`index.html`) untuk menguji fitur "bagikan progress belajar" dari profil ke anak studytwt.

## Cara jalanin
- Buka `index.html` di browser (butuh internet untuk Tailwind v4 browser build, font Google, dan cdnjs).
- Atau pakai link artifact yang dipublish.

## Sumber UI (ground truth: Figma)
- Profile & Friends V2 (file `IEYWGSPYVdS13NfXn2iXIR`): profil Ringkasan, Achievement, Habit, popup waktu per subtes, profil teman (Sinta), rail Mengikuti/Saran/Temukan teman.
- Gamification x Mastery Desktop (file `dC0WqQqXdfKpW3XwkruZ0s`): sistem Bagikan (modal "Bagikan streak-mu", kartu Story 9:16, halaman publik), Rapot sesi.
- Token dari variabel Figma: surface-primary `#171421`, surface-secondary `#2a253a`, surface-brand `#5f2bce`, off-purple `#451aa2`, midnight 600/700/800 `#534a70/#3e3754/#2a253a`, brand-300 `#b285f0`, border kartu `#221e2f`.
- Ikon nav, flame, coin EXP, level diambil dari export UI Gradient.

## Aset asli dari Figma (tertanam di `const IMG`)
- File `UTBK 2026 - Assets` (`I06TbUfEcpowPyWkI7Sbdf`): 37 badge rendered (streak, try out, jam fokus, master/khatam per subtes, tri nalar sampai mythic, diamond subtes).
- File Profile V2: banner profil, avatar (Chisu, Sinta, Raka, Nadia), art gedung kampus, logo ITB.
- Masih placeholder: ikon tile stat Habit (soal/materi), ikon ringkasan Achievement.

## Aset baru (eksploratif, bukan dari UI asli)
- Kartu "Progress belajar" (hari ini dan minggu ini) di tab Ringkasan, masing-masing dengan tombol Bagikan
- Tombol "Bagikan progress" di tab profil, kartu ajakan di Habit, ikon share di badge Achievement, halaman hasil sesi
- Data point kartu: banner kampus impian di atas, waktu belajar dengan banding minggu lalu (atau rata-rata harian), streak, hari aktif, soal dan akurasi, perkembangan mastery (materi yang naik beserta dari dan ke berapa persen), waktu per subtes dan soal per subtes. Tingkat kesulitan, badge, dan level jadi opsional.
- Tier data kartu: Utama (terkunci): nama, waktu belajar, jumlah soal, subtes. PTN dan prodi impian ada di grup Utama tapi bisa disembunyikan. Sekunder: streak, perkembangan, badge dan level dan EXP (di samping nama), nama sekolah. Tersier: hari aktif, tingkat kesulitan, jumlah soal benar. Angkatan dihapus.
- Gaya kartu (pilih langsung di bawah preview): Ringkas (default), Mastery naik (bar sebelum dan sesudah per subtes, skill yang naik), Jejak latihan (akurasi per tingkat kesulitan, soal per hari, naik tingkat soal), Custom (layout Ringkas dengan toggle data bebas). Memilih preset mengembalikan isi data ke bawaan, toggle data lengkap hanya muncul di Custom. Toggle privasi PTN impian dan nama sekolah tersedia di semua gaya dan pilihannya tidak ikut direset saat pindah preset. Highlight (satu kalimat per capaian) disembunyikan dari pilihan, kodenya masih ada.
- Kartu share default: portrait 3:4 (360x480, ekspor 1080x1440) layout rapor ala referensi Alternatifa: waktu belajar dengan target, kubus soal dan akurasi, waktu per subtes, tingkat kesulitan beserta akurasi per level.
- Nama di kartu bisa diganti (maks 20 karakter, kosong berarti nama asli) lewat kolom di Atur isi kartu, berlaku di semua gaya. Hanya mengubah tampilan kartu, link profil tetap ke akun asli (perlu diputuskan di PRD kalau mau link anonim). Header kartu: baris 1 nama (foto opsional) dan badge, baris 2 level, EXP, nama sekolah.
- Studio share: periode, 4 gaya kartu, 3 rasio, toggle data, caption, link, privasi, share ke X
- Kustomisasi ringan (opsi B dari masukan studytwt): 3 tema kartu (Ungu default, Hitam putih, Terang), toggle foto profil di Tersier (default mati), catatan singkat maksimal 100 karakter (sekitar dua baris di kartu). Isi kartu otomatis dirapatkan kalau catatan atau avatar bikin kartu penuh.
- Panel kontrol prototype dan form masukan

## Catatan teknis
- Ekspor PNG 1080px memakai SVG foreignObject dengan font Nunito/Urbanist yang ditanam (html2canvas jadi cadangan).
- Semua data contoh. Link profil publik dan privasi link hanya simulasi UI.
