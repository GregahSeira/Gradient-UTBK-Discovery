# PRD V1: share progress belajar

V1 = satu kartu Ringkasan yang bisa dibagikan dari profil ke studytwt, isinya effort (waktu, soal) dan hasilnya (mastery naik per materi).

Isinya scope produk dan aturan data. Prototype: https://claude.ai/artifact/F3E5PENi3heTvgtLgR5nS2. Semua angka di prototype = data contoh.

## Masalah dan target

- [FAKTA] Anak studytwt rutin update progress harian dan mingguan di X, sering dari akun anonim. Sumber: sesi Desak Gradient UTBK, 16 Nov 2026.
- [FAKTA] Usulan terbanyak di sesi itu: privasi per item, tema, avatar, grafik jelas, opsi harian dan mingguan.
- [INFERENSI] Kartu siap share = akuisisi gratis tiap user posting, karena kartu bawa brand dan link Gradient.
- Job user = memamerkan effort yang sudah dilakukan beserta hasilnya, tanpa edit manual.

| Metrik sukses | Target |
|---|---|
| Share rate (klik channel / buka studio) | [ASUMSI] 30% |
| Kunjungan per link share | [ASUMSI] 3 |
| Signup dari link share | [ASUMSI] baseline dicek di Metabase dulu |

## Scope

| Masuk V1 | Tidak masuk V1 |
|---|---|
| 1 template Ringkasan | Template lain (Mastery Subtes, Materi, Custom) |
| Periode Hari ini, Minggu ini, Sesi (dari Rapot) | Periode 30 hari |
| Ukuran 3:4 Feed dan 9:16 Story, 3 tema | Background gambar, upload foto |
| Toggle data, nama custom, catatan 100 karakter | Streak grup |
| Link acak, isi beku, aktif selamanya | Tarik atau hapus link |
| Section Progress belajar di profil | Kartu 30 hari |

## Isi kartu

| Blok | Isi | Bisa disembunyikan |
|---|---|---|
| Header | Wordmark, pil "Progress hari ini/minggu ini/sesi ini", tanggal | Tidak |
| Profil | Nama, foto, sekolah, badge, Level & EXP | Nama tidak (bisa diganti), sisanya bisa |
| PTN impian | Banner PTN + prodi | Bisa |
| Waktu belajar | Durasi + "vs rerata harian/mingguan/per sesi (X)" + selisih | Tidak |
| Tile | Streak, Soal dikerjakan (benar dan persen) | Streak bisa, soal benar bisa |
| Perkembangan mastery | Materi, soal, durasi, bar, dari ke persen, perubahan | Tidak |
| Catatan | Teks user | Opsional |

Aturan Perkembangan mastery:
- Tingkat = Subtes, Chapter, atau Sub-chapter. Bawaan otomatis Sub-chapter kalau minimal 3 materi dikerjakan, kalau kurang pakai Subtes.
- Yang dikerjakan di atas, urut dari kenaikan terbesar. Yang tidak dikerjakan = baris pudar di bawah label "Belum dikerjakan".
- Jumlah baris bawaan = sebanyak yang muat. User bisa pilih jumlah, kartu pindah ke 9:16 kalau tidak muat.

Aturan rerata: harian = total 7 hari terakhir / 7 (minimal 3 hari aktif). Mingguan = rata-rata 4 minggu sebelumnya. Per sesi = rata-rata durasi sesi sebelumnya. Riwayat tidak cukup = "belum ada".

## Alur share

1. User klik Bagikan di profil, Habit, atau Rapot sesi.
2. Studio terbuka, user atur kartu (opsional) lewat panel ringkas: Periode, Ukuran, Mastery, Tema, Tampilkan, Nama, Catatan, Edit caption postingan.
3. User pilih WhatsApp, Instagram, X, Salin tautan, Lainnya, atau Simpan gambar.
4. Isi kartu dibekukan jadi snapshot di `gradient.academy/s/<8 karakter acak>`. Kartu diubah setelah itu = link baru, link lama tetap.

Section Progress belajar di profil: tab Hari ini dan 7 hari terakhir, 4 kotak (waktu belajar, rerata waktu, soal dikerjakan, rerata soal), link ke Habit, tombol Bagikan.

## Keputusan utama

| Keputusan | Kenapa | Alternatif ditolak | Kenapa ditolak |
|---|---|---|---|
| [REKOMENDASI] Waktu, soal, mastery dikunci | Tanpa itu kartu tidak punya cerita effort ke hasil | Semua data bisa dimatikan | Kartu bisa kosong |
| [REKOMENDASI] Link acak anonim | Akun anonim tidak bocor identitas | Link ke profil, caption tanpa link | Bocor identitas, atau hilang traffic balik |
| [REKOMENDASI] 1 template | Dari 4 template yang dieksplor, cuma Ringkasan yang lolos review PM | Ringkasan + 2 preset + Custom | Kompleks, membuat user dan tim bingung |
| [REKOMENDASI] Tanpa penanda "lemah" merah | [INFERENSI] Mastery rendah tanpa kenaikan membuat user batal share | Subtes di bawah 20% merah | Kartu terlihat negatif |

## Kebutuhan data

| Data | Status |
|---|---|
| Waktu belajar, soal, benar per periode | [ASUMSI] ada (sudah dipakai di Habit) |
| Mastery per sub-chapter, nilai awal dan akhir periode | [ASUMSI] perlu dibangun (snapshot harian) |
| Soal dan durasi per sub-chapter | [ASUMSI] perlu dicek |
| Struktur Subtes, Chapter, Sub-chapter | [ASUMSI] perlu konfirmasi ke akademik |
| Rerata waktu dan soal | Perlu dibangun |
| Nama sekolah | [ASUMSI] belum tentu ada di profil |
| Snapshot link (slug, isi kartu, tanggal) | Perlu dibangun |

## Risiko

| Risiko | P×I | Mitigasi |
|---|---|---|
| Data mastery per sub-chapter per periode belum ada | 4×5 = 20 | Cek ke Angga, fallback tingkat Subtes saja |
| User tidak share karena progress kecil | 3×4 = 12 | Sorot yang naik, pudarkan yang tidak dikerjakan |
| Nama atau catatan dipakai untuk kata kasar | 2×3 = 6 | Filter kata dasar |
| Ekspor gambar beda dengan preview di HP tertentu | 2×3 = 6 | Uji di 3 browser HP sebelum rilis |

## Ditunda

- Isi caption bawaan (hashtag merek, kalimat penutup).
- Masukan kkaocarpenter soal "persentase soal dikerjakan", maksudnya belum jelas.
- Masukan njanjanja26 soal subtes sulit ditandai merah.
- Tarik atau hapus link, streak grup, template lain.

Uji untuk usulan berikutnya: apakah ini membuat anak studytwt makin ingin memamerkan effort dan hasilnya hari ini? Kalau tidak, masuk backlog.
