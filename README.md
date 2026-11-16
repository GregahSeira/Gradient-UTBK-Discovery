# Gradient UTBK: Share Progress Belajar (discovery prototype)

Prototype satu file (`index.html`) untuk menguji fitur "bagikan progress belajar" dari profil ke anak studytwt.

## Cara jalanin
- Buka `index.html` di browser (butuh internet untuk Tailwind v4 browser build, font Google, dan cdnjs).
- Atau pakai link artifact yang dipublish.

## Sumber UI
- Markup dan class Tailwind v4 disalin dari file UI Gradient UTBK (Profil Ringkasan/Achievement/Habit, Latihan Soal).
- SVG asli (ikon nav, flame, coin EXP, badge level, trophy, bell, dll) diekstrak dari file itu dan ditanam di `const A`.
- Warna subtest asli: PU `#fec924`, PPU `#84cc16`, PBM `#e56aca`, PK `#20e3b2`, LBI `#ff6a5c`, LBE `#00c3ff`, PM `#d026b3`.
- Token yang ditandai `/* est */` di blok `@theme` adalah perkiraan karena `styles-*.css` asli tidak ikut terkirim. Ganti nilainya di satu tempat itu.

## Aset yang belum ada (pakai placeholder)
- `kampus-art.png` (banner profil), `universitas-indonesia.png` (logo kampus)
- Ikon subtest (`pu-icon`, `pk-icon`, ...), ikon stat Habit (`stat-questions`, `stat-materials`)
- SVG badge achievement (`streak-7`, `tryout-1`, `tri-nalar`, dst), avatar dan border S3

## Aset baru (eksploratif, bukan dari UI asli)
- Tombol "Bagikan progress" di tab profil, kartu ajakan di Habit, ikon share di badge Achievement, halaman hasil sesi
- Studio share: periode, 4 gaya kartu, 3 rasio, toggle data, caption, link, privasi, share ke X
- Panel kontrol prototype dan form masukan

## Catatan teknis
- Ekspor PNG 1080px memakai SVG foreignObject dengan font Nunito/Urbanist yang ditanam (html2canvas jadi cadangan).
- Semua data contoh. Link profil publik dan privasi link hanya simulasi UI.
