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
- Tombol "Bagikan progress" di tab profil, kartu ajakan di Habit, ikon share di badge Achievement, halaman hasil sesi
- Studio share: periode, 4 gaya kartu, 3 rasio, toggle data, caption, link, privasi, share ke X
- Panel kontrol prototype dan form masukan

## Catatan teknis
- Ekspor PNG 1080px memakai SVG foreignObject dengan font Nunito/Urbanist yang ditanam (html2canvas jadi cadangan).
- Semua data contoh. Link profil publik dan privasi link hanya simulasi UI.
