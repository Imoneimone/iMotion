---
name: imotion
description: Build, refine, and debug motion graphics and animation directly in code as an AI coding agent. Use for browser motion design, kinetic typography, explainers, 2D/cartoon/slapstick animation, camera choreography, deterministic timelines, synchronized sound, animation code review, and render/preview QA. Implements visual artifacts in code.
license: MIT
metadata:
  version: "1.1.0"
  language: id
---

# iMotion

Gunakan iMotion untuk merancang, mengodekan, menyinkronkan, dan memeriksa motion graphics atau animasi. Hasil utamanya adalah implementasi yang dapat dijalankan dan ditinjau oleh coding agent.

## Alur kerja

1. **Inspeksi proyek.** Baca struktur, framework, package scripts, aset, pola kode, dan cara menjalankan. Pertahankan stack yang sudah ada. Jangan mengganti konfigurasi besar tanpa alasan.
2. **Tafsirkan brief menjadi aksi.** Tentukan tujuan penonton, subjek, perubahan, dan rasa akhir. Tetapkan format/aspect ratio, durasi, platform, aksesibilitas, kebutuhan audio, dan batasan yang diberikan. Ajukan pertanyaan hanya untuk keputusan penting yang belum dapat diasumsikan.
3. **Rancang beat sheet.** Pecah durasi menjadi beat dengan aksi terlihat, state awal/akhir, fokus, framing/kamera, timing, transisi, dan cue suara bila perlu. Muat `references/beat-sheet.md` dan `references/motion-grammar.md`.
4. **Tentukan bahasa visual.** Pilih palet, tipografi, bentuk, tekstur, pencahayaan, bahasa kamera, dan signature motion dari brief/brand. Muat `references/style-system.md`. Hindari menyalin detail khas dari contoh referensi.
5. **Pilih arsitektur implementasi.** Pilih DOM/CSS/GSAP, SVG, Canvas, WebGL, atau renderer yang sudah digunakan proyek. Muat `references/implementation-patterns.md`; baca `references/output-profiles.md` bila target output menentukan perilaku khusus.
6. **Implementasikan bertahap.** Bangun beat inti, jalankan, periksa, lalu kembangkan. Gunakan timeline dan parameter bernama. Buat state deterministik terhadap waktu bila scrub, seek, capture, atau frame-by-frame rendering diperlukan.
7. **Tambahkan suara bila diminta.** Hubungkan cue audio dengan event visual menggunakan timeline/marker. Muat `references/sound-design.md`. Jangan menambahkan suara dekoratif pada semua gerak.
8. **Preview dan revisi.** Tonton gerak penuh dan inspeksi frame kunci. Muat `references/verification.md`. Betulkan keterbacaan aksi, kontinuitas, komposisi, timing, dan clipping sebelum memoles detail kecil.
9. **Serahkan hasil.** Sebut file yang diubah, cara menjalankan/preview, batasan, serta aspek yang belum diverifikasi. Jangan mengklaim render atau ekspor berhasil sebelum diuji.

## Pilih modul sesuai tugas

- Aksi, tempo, transisi, kamera, atau teks bergerak: `references/motion-grammar.md`.
- Breakdown adegan sebelum coding: `references/beat-sheet.md`.
- Transformasi, komedi fisik, atau karakter 2D: `references/slapstick-kinematics.md`.
- Arah art, konsistensi brand, dan pencegahan hasil terasa seperti slide: `references/style-system.md`.
- Pilihan API, arsitektur timeline, determinisme, dan performa: `references/implementation-patterns.md`.
- Durasi, format, loop, audio, atau ekspor tertentu: `references/output-profiles.md`.
- Musik, narasi, foley, impact, atau sinkronisasi: `references/sound-design.md`.
- Preview, frame capture, debugging visual, dan render QA: `references/verification.md`.

## Prinsip yang selalu berlaku

- Satu beat mempunyai maksud visual yang dapat dijelaskan; satu aksi dominan biasanya lebih terbaca daripada banyak aksi simultan.
- Gerak punya pemicu, arah, respons, dan penyelesaian. Gunakan anticipation, impact, recoil, follow-through, dan settle sesuai kebutuhan, bukan sebagai checklist wajib untuk setiap animasi.
- Bedakan timing (durasi) dari spacing (perubahan jarak antarwaktu). Pilih easing berdasarkan material dan maksud.
- Jaga siluet, fokus, screen direction, kontinuitas prop, serta pose awal/akhir.
- Kamera harus mengikuti, mengungkap, menekankan, atau membingkai ulang. Hindari pergantian shot yang terasa seperti slide otomatis.
- Buat gaya dari brief/brand; starter adalah struktur, bukan keputusan gaya.
- Detail mikro harus mendukung aksi makro. Hindari angka fisika palsu; pakai parameter artistik yang dapat dituning.
- Jaga aksesibilitas, performa, dan keterbacaan; jangan mengorbankannya demi efek dekoratif.

## Gerbang kualitas

Pastikan proyek berjalan; aksi utama dipahami tanpa penjelasan; tempo memiliki kontras; fokus dan teks terbaca pada format target; transisi punya motivasi; state/loop konsisten; audio sejajar bila digunakan; dan hasil benar-benar dipreview. Jika tool atau akses tidak memungkinkan inspeksi tertentu, nyatakan batasannya.
