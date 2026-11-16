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
- Tier data kartu: Utama (terkunci): nama, waktu belajar, jumlah soal, subtes. PTN dan prodi impian ada di grup Utama tapi bisa disembunyikan. Sekunder: streak, perkembangan, badge, level, dan EXP dalam satu toggle (di samping nama), nama sekolah. Tersier: hari aktif, tingkat kesulitan (digabung ke bar Data latihan soal (dulu Subtes yang dipelajari): bar = jumlah soal per subtes, warna = mudah, sedang, sulit), jumlah soal benar. Angkatan dihapus. Catatan PRD: PTN impian masih di grup Utama walau bisa disembunyikan. Apakah perlu ada data yang dikunci atau tidak, diputuskan nanti setelah masukan studytwt.
- Gaya kartu (pilih langsung di bawah preview, 4 pilihan): Ringkasan (default, waktu belajar, soal, streak, perkembangan mastery, subtes), Mastery (mastery per subtes dengan bar sebelum dan sesudah, plus data latihan soal: akurasi per tingkat kesulitan), Materi (data belajar materi: materi terlama, waktu per subtes), Custom. Memilih preset mengembalikan isi data ke bawaan. Toggle privasi PTN impian dan nama sekolah tersedia di semua gaya dan tidak ikut direset. Template lama (Jejak latihan, Highlight) disembunyikan, kodenya masih ada.
- Kartu share default: portrait 3:4 (360x480, ekspor 1080x1440) layout rapor ala referensi Alternatifa: waktu belajar dengan target, kubus soal dan akurasi, waktu per subtes, tingkat kesulitan beserta akurasi per level.
- Mastery: bagian bar yang naik minggu ini digambar hijau di ujung bar. Penanda subtes lemah (mastery di bawah 20%, merah) sempat dibuat lalu dibatalkan: ada kasus mastery memang rendah dan tidak naik, kartu jadi terlihat negatif.
- Custom: semua data bisa dipilih, termasuk grup Utama (nama, waktu belajar, jumlah soal, subtes, PTN impian), Sekunder, dan Tersier (data baru: mastery per subtes, materi yang dipelajari, soal per hari). Fokus opsional: satu atau beberapa subtes, atau satu materi dalam satu subtes. Angka kartu ikut dihitung ulang untuk fokus itu, tanpa banding minggu lalu dan soal per hari karena datanya belum ada per materi. Ukuran kartu: Otomatis (tinggi mengikuti isi), 3:4, 4:5, 9:16. Asumsi: kata "tingkatan" dari product owner diartikan tier data (Utama, Sekunder, Tersier), bukan tingkat kesulitan soal.
- Kartu tidak pernah kepotong: teks dirapatkan otomatis, dan kalau masih penuh kartu dipanjangkan sedikit dari 3:4.
- Data per materi (24 materi minggu ini, per hari, per sesi) adalah data contoh yang konsisten dengan total subtes. Di produk nyata perlu dihitung dari log belajar.
- Nama di kartu bisa diganti (maks 20 karakter, kosong berarti nama asli) lewat kolom di Atur isi kartu, berlaku di semua gaya. Hanya mengubah tampilan kartu dan halaman publik. Header kartu: kiri nama (foto opsional) dengan nama sekolah di bawahnya; kanan badge dengan Level & EXP di bawahnya. Badge dan Level & EXP toggle terpisah.
- Link share anonim: `gradient.academy/s/<8 karakter acak>`, dibuat baru setiap studio dibuka, tidak memuat username atau nama, jadi sama aman untuk nama asli maupun custom. Halaman publik memakai nama di kartu. Isi link dibekukan (snapshot) saat user membagikan (WhatsApp, X, Instagram, Salin tautan, Lainnya, Lihat halaman publik). Kalau kartu diubah setelah itu, link baru dibuat otomatis dan link lama tetap menampilkan versi lama. Halaman publik memakai snapshot dan menampilkan tanggal dibagikan. Keputusan: link aktif selamanya, tidak ada fitur atau tampilan untuk menarik atau menghapus link (edge case, ditunda). Simulasi UI: di produk nyata perlu penyimpanan snapshot per link.
- Studio share: periode, 4 gaya kartu, 3 rasio, toggle data, caption, link, privasi, share ke X
- Kustomisasi ringan (opsi B dari masukan studytwt): 3 tema kartu (Ungu default, Hitam putih, Terang), toggle foto profil di Tersier (default mati), catatan singkat maksimal 100 karakter (sekitar dua baris di kartu). Isi kartu otomatis dirapatkan kalau catatan atau avatar bikin kartu penuh.
- Panel kontrol prototype dan form masukan

## Keputusan yang ditunda (untuk PRD, setelah masukan studytwt)
- Apakah ada data yang dikunci, dan apakah PTN impian pindah ke Sekunder.
- Isi caption bawaan: hashtag merek, kalimat penutup otomatis.
- Fitur tarik atau hapus link yang sudah dibagikan.
- Data contoh yang harus dihitung sungguhan: delta mastery, skill naik, banding minggu lalu, soal per subtes, nama sekolah.

## Scope MVP (V1)
- Hanya 1 template: Ringkasan. Tidak ada pilihan gaya kartu.
- Perkembangan mastery jadi satu section tunggal (blok Data latihan soal dan toggle-nya, serta toggle Tingkat kesulitan, dihapus). Isinya semua materi yang dipelajari di periode itu, urut dari yang paling naik, tanpa batas tetap: baris sebanyak yang muat di poster (dihitung otomatis), sisanya jadi "+N materi lain dipelajari". Antar baris ada garis lurus sebagai pembatas. Semua tingkat menampilkan seluruh daftar (7 subtes, 14 chapter, 24 sub-chapter): yang dikerjakan di periode itu di atas, sisanya tampil 0 soal dan tetap, supaya kartu selalu penuh di setiap periode, tingkat, ukuran, dan persona. Kalau daftar terpotong atau minimal 5 baris, jarak antar baris dibagi rata sampai bawah. Opsi Tingkat mastery: Subtes, Chapter (sub-chapter dikelompokkan, mastery = rata-rata tertimbang jumlah soal), Sub-chapter (bawaan). Pemetaan chapter masih contoh. Header hanya jumlah yang naik (misal "5 subtes naik"). Opsi Jumlah mastery ditampilkan: Penuh (bawaan, sebanyak yang muat sampai bawah poster) atau angka 1 sampai semua; kalau tidak muat di 3:4, ukuran otomatis pindah ke 9:16 (Story) dan kembali ke 3:4 kalau jumlahnya dikurangi; kalau di 9:16 pun tidak muat, kartu dipanjangkan. Memilih ukuran (3:4 atau 9:16) mengembalikan jumlah ke Penuh, dan blok mastery merentang sampai bawah poster dengan baris tetap rapat di atas. Opsi Ukuran: 3:4 (Feed) dan 9:16 (Story, muat lebih banyak baris). Tiap baris: subtes, nama materi, jumlah soal, bar mastery (warna subtes = sebelumnya, hijau = naik), dari ke persen, dan perubahan (atau "tetap"). Header: "X dari Y materi naik".
- Studio berisi kartu Ringkasan plus kustomisasi: periode, tema, nama di kartu, toggle data Utama, Sekunder, Tersier (semua bisa dimatikan), catatan, caption.
- Template lain (Mastery Subtes, Mastery, Materi, Custom dengan fokus, Jejak latihan, Highlight) disimpan di kode untuk versi berikutnya.

## Ditinjau lagi di akhir
- Masukan kkaocarpenter: tambah persentase soal dikerjakan, jangan cuma lama waktu belajar. Maksud persisnya belum jelas (kartu sudah punya jumlah soal dan persen benar). Kalau maksudnya persen terhadap target soal harian, butuh data target yang belum ada.
- Masukan njanjanja26: mapel sulit ditandai merah lalu tampil kalau ada peningkatan. Dibatalkan sementara karena risiko kartu terlihat negatif untuk mastery rendah tanpa peningkatan.

## Catatan teknis
- Ekspor PNG 1080px memakai SVG foreignObject dengan font Nunito/Urbanist yang ditanam (html2canvas jadi cadangan).
- Semua data contoh. Link profil publik dan privasi link hanya simulasi UI.
