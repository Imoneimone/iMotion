# Beat Sheet: dari brief ke timeline

Beat sheet adalah spesifikasi kerja sebelum coding. Ia mengurangi perubahan arah saat implementasi dan memudahkan pemeriksaan durasi/continuity.

## Brief visual satu kalimat

Isi ringkas:

- **Subjek:** siapa/apa yang bergerak?
- **Tujuan atau klaim:** apa yang ingin penonton pahami/rasakan?
- **Pemicu/konflik:** apa yang mengubah keadaan?
- **Payoff:** perubahan, reveal, reaksi, atau pose akhir apa yang menjadi hasil?
- **Batasan:** platform, aspek rasio, durasi, brand, konten, aksesibilitas, audio, teknologi.

## Templat beat

Salin kolom-kolom berikut ke markdown, JSON, atau data timeline proyek:

```text
Beat ID / nama:
Rentang waktu (detik) / frame:
Tujuan beat:
State awal → state akhir:
Aksi subjek dan pemicu:
Fokus penonton:
Framing / kamera / screen direction:
Gerak makro:
Gerak meso/mikro (jika perlu):
Timing / hold / easing:
Transisi masuk / keluar:
Audio cue / marker:
Catatan continuity dan risiko:
```

## Aturan membagi beat

- Buat beat baru saat tujuan visual berubah, ada pemicu baru, fokus berpindah, atau state naratif berubah—bukan hanya karena kalimat naskah berikutnya.
- Satu beat idealnya memiliki satu aksi dominan. Aksi pendukung harus memperjelas atau bereaksi terhadap aksi utama.
- Gabungkan informasi yang dapat dijelaskan oleh satu perubahan visual; pisahkan bila butuh fokus, staging, atau timing yang berbeda.
- Tulis keadaan sebelum dan sesudah aksi agar tween punya target yang jelas.
- Tentukan apa yang penonton lihat terlebih dahulu dan elemen apa yang harus tetap terlihat.
- Tandai elemen yang harus kontinuitas: desain karakter, tangan/prop, arah gerak, posisi layar, sumber cahaya, dan state akhir shot.

## Anggaran waktu

1. Tetapkan total durasi dan frame rate bila output berbasis frame.
2. Bagi waktu untuk orientasi, build/anticipation, aksi utama, hold/reaction, settle, dan end card/loop sesuai kebutuhan. Jangan mengalokasikan semua waktu ke gerakan aktif.
3. Pastikan jumlah durasi beat sama dengan total runtime, termasuk jeda dan transition overlap.
4. Pada timeline overlap, bedakan durasi klip dari waktu layar. Gunakan marker yang mudah dibaca.
5. Konversi secara eksplisit: `frame = round(waktu_detik × FPS)`; `waktu_detik = frame / FPS`. Bulatkan secara konsisten dan periksa total setelah pembulatan.
6. Jika runtime/kecepatan belum pasti, gunakan proporsi dan verifikasi setelah animasi dipreview.

## Contoh mini (abstrak)

```text
A — establish (0.0–0.7 s): karakter dan prop berada di frame; kamera medium-wide.
B — anticipation (0.7–1.2 s): karakter condong; pandangan mengarah ke prop; hold singkat.
C — action/contact (1.2–1.7 s): karakter menarik prop; impact terjadi pada marker 1.55 s.
D — reaction (1.7–2.2 s): prop mengikuti, karakter recoil; kamera tetap menjaga siluet.
E — settle/payoff (2.2–3.0 s): gerak kecil berhenti; ekspresi akhir ditahan agar terbaca.
```

Contoh ini hanya menjelaskan format; ganti jumlah beat dan durasi berdasarkan brief.

## Gerbang review sebelum coding

- Apakah aksi dapat dijelaskan dengan kata kerja konkret?
- Apakah state awal dan akhir dapat dibuat dalam sistem koordinat proyek?
- Apakah ada durasi untuk membaca hasil atau ekspresi?
- Apakah setiap transisi mempertahankan continuity yang diperlukan?
- Apakah suara, kamera, teks, dan objek punya marker jika perlu sinkronisasi?
- Apakah ada beat yang sebenarnya hanya mengulang informasi tanpa perubahan visual?
