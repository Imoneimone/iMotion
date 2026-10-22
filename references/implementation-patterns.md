# Implementation Patterns: arsitektur motion dengan kode

## Pilih teknologi sesuai tugas

- **DOM/CSS/GSAP:** teks, UI, bentuk, layer visual, dan timeline dengan banyak elemen; gunakan bila struktur DOM membantu aksesibilitas atau styling.
- **Web Animations API:** animasi properti DOM yang ringan tanpa dependency; cocok untuk gerak komponen sederhana.
- **SVG:** ikon, path, stroke reveal, mask, diagram, dan bentuk vektor tajam.
- **Canvas 2D:** banyak partikel, frame-by-frame, procedural drawing, atau layer yang lebih efisien digambar sebagai satu surface.
- **WebGL/Three.js:** kedalaman, kamera, material, atau scene 3D yang benar-benar penting pada konsep.
- **Renderer/frame framework proyek:** ikuti tool existing bila ekspor video atau render terkontrol diperlukan.

Inspeksi dependency, scripts, dan struktur terlebih dahulu. Jangan menambah stack baru jika teknologi saat ini mampu menyelesaikan tugas.

## Pisahkan tanggung jawab

Pisahkan (sesuai skala proyek):

1. konfigurasi durasi, ukuran, FPS, palet, dan parameter;
2. data scene/beat dan state visual;
3. komponen/rig gambar;
4. timeline dan marker event;
5. audio cue;
6. preview, debug, dan export.

Gunakan nama objek dan parameter yang menjelaskan fungsinya, misalnya `heroRoot`, `impactHold`, `recoilDistance`, bukan `thing2` atau angka tersebar. Hindari abstraksi berlebihan pada prototipe kecil.

## Timeline deterministik

Untuk seek/scrub dan render berulang, visual harus bergantung pada waktu timeline:

- Gunakan timeline library atau fungsi `stateAt(t)` sebagai sumber state.
- Jangan membaca wall-clock untuk posisi animasi yang harus dapat diulang.
- Hindari `x += velocity * delta` sebagai satu-satunya state; seek ke waktu arbitrer harus menghasilkan posisi yang sama.
- Untuk variasi procedural, gunakan seed stabil dan fungsi deterministik.
- Pusatkan konstanta timing dan marker; hindari magic numbers tersebar.
- Saat berbasis frame, nyatakan FPS dan konversi dengan `frame = round(seconds * FPS)`. Gunakan kebijakan pembulatan konsisten.
- Pastikan seek tidak mengulang sound effect, callback efek samping, atau state transien secara tidak sengaja.

Tidak semua UI perlu determinisme video, tetapi fungsi yang bisa di-seek mempermudah debugging dan preview.

## Rig, pivot, dan koordinat

- Tentukan sistem koordinat, unit, origin scene, dan ukuran target.
- Tetapkan anchor/pivot untuk karakter, prop, kamera, dan label sebelum tween.
- Kelompokkan objek di bawah parent/root bila mereka harus ikut gerak kamera/dunia yang sama.
- Pisahkan layer latar, subjek, foreground, teks, dan efek untuk mengendalikan kedalaman visual.
- Rig karakter hanya sejauh gerak memerlukannya; jaga siluet dan relasi antarbagiannya.
- Gunakan state bernama untuk rangkaian aksi kompleks agar transisi dan recovery jelas.

## Canvas dan render loop

Pada Canvas, hitung gambar dari timestamp timeline yang eksplisit. Pisahkan update state dari draw. Batasi objek aktif, reuse buffer bila sesuai, dan bersihkan canvas secara konsisten. Jangan memperbarui visual berdasarkan jumlah frame yang kebetulan telah berjalan jika pengguna perlu seek.

## Robustness, aksesibilitas, dan performa

- Hormati `prefers-reduced-motion` untuk animasi interface yang berulang atau dapat mengganggu.
- Sediakan jeda/stop bila gerak berlangsung lama atau dikontrol pengguna.
- Bersihkan ticker, RAF loop, event listener, timer, dan audio node saat komponen berhenti/unmount.
- Hindari layout thrashing; untuk animasi DOM utamakan `transform`/`opacity` bila tepat.
- Tunggu font dan aset selesai dimuat sebelum mengambil screenshot atau render.
- Sediakan fallback untuk kegagalan font/aset eksternal; jelaskan kebutuhan jaringan bila memakai CDN.
- Profilkan sebelum optimasi besar; jangan menambah efek mahal tanpa kebutuhan visual.
