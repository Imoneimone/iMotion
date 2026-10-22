# Verification: preview dan QA motion

## Preview browser

1. Temukan perintah run/dev dari package scripts atau dokumentasi proyek.
2. Jalankan proyek dan buka ukuran/aspect ratio target.
3. Tonton animasi penuh dengan audio jika tersedia; jangan hanya menilai dari frame pertama.
4. Ambil frame pada start, akhir anticipation, contact/impact, puncak, reaksi/settle, transisi, dan akhir.
5. Jika timeline dapat di-seek, seek berulang ke waktu yang sama dan pastikan state konsisten.
6. Uji pause, restart, resize, reduced motion, dan input pengguna sesuai deliverable.

## Inspeksi visual

Periksa:

- Aksi utama terbaca pada ukuran target dan dalam waktu singkat.
- Fokus jelas; hierarki perhatian tidak bertabrakan.
- Siluet, wajah, teks, dan objek payoff tidak tertutup atau terpotong.
- Pivot, jalur, contact point, dan screen direction masuk akal.
- State antarbeat konsisten; tidak ada objek teleport, berubah identitas, atau muncul/hilang tanpa alasan.
- Timing memiliki kontras; hold, recoil, dan settle tidak terasa terlalu pendek/panjang.
- Kamera membantu aksi; tidak ada drift, zoom, atau cut yang tidak disengaja.
- Warna/kontras dan tipografi terbaca; tidak ada font/layout shift setelah aset dimuat.
- Efek, partikel, blur, dan detail tidak mengalahkan subjek.
- Loop tidak menunjukkan pop/jump pada batas awal-akhir.

## Debugging timeline

- Tambahkan mode debug/scrub sementara bila dibutuhkan; jangan biarkan panel debug muncul pada output final tanpa diminta.
- Log marker dan state penting saat seek, tetapi jangan menambah side effect dalam render function.
- Uji batas beat dan frame tepat sebelum/sesudah impact atau cut.
- Jika ada ketidaksesuaian, isolasi satu variabel: timing, pivot, easing, kamera, atau layering. Ubah masalah yang paling besar terlebih dahulu.

## Video/render export

Periksa metadata aktual bila tool tersedia: dimensi, aspect ratio, FPS, durasi, codec/container, track audio, dan frame akhir. Tonton seluruh file hasil. Metadata saja tidak cukup untuk menyatakan visual/audio benar.

Jika tool render tidak tersedia, berikan cara preview yang tersedia dan jelaskan apa yang belum diverifikasi. Jangan menyatakan export berhasil berdasarkan kode sumber saja.

## Gerbang review final

- Apakah penonton tahu harus melihat ke mana?
- Apakah pemicu dan akibat jelas?
- Apakah pose kunci terbaca tanpa penjelasan?
- Apakah beat memiliki fungsi berbeda dan payoff yang layak ditahan?
- Apakah audio mendukung event tanpa menumpuk?
- Apakah hasil benar-benar dijalankan, dipreview, dan/atau dirender?
