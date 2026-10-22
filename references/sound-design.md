# Sound Design: audio yang terikat pada aksi

## Spotting dan cue sheet

Baca animasi dan tandai event yang memerlukan suara: ambience ruang, gesekan/material, gerak, kontak/impact, ekspresi, transformasi, transisi, dan settle. Tidak semua gerakan perlu cue. Sisakan ruang untuk musik, narasi, dan hening.

Gunakan cue sheet berikut:

```text
Marker/waktu:
Pemicu visual:
Peran suara: ambience / foley / motion / impact / music / voice
Material/timbre:
Onset dan durasi:
Jarak/intensitas:
Layer yang perlu ducking:
Catatan loop/seek:
```

Spotting sebaiknya terikat pada perubahan visual yang bermakna. Hindari mendesain bunyi hanya berdasarkan nama gerakan.

## Fungsi lapisan

- **Ambience:** memberi konteks ruang; biasanya stabil dan tidak mendominasi.
- **Foley/material:** menjelaskan sentuhan dan tekstur seperti kain, kayu, logam, kertas, cairan, atau granular.
- **Motion cue:** whoosh, riser, sweep, atau tonal accent untuk arah/energi.
- **Impact:** menandai kontak atau perubahan mendadak; onsetnya harus cocok dengan event.
- **Music:** membawa struktur, mood, dan ritme; gunakan beat hanya saat membantu timing.
- **Voice:** bawa pesan utama; jaga kejelasan dan ruang frekuensi.

Pilih sedikit layer yang berbeda fungsi. Hindari menumpuk beberapa bunyi yang semuanya mencoba menandai impact yang sama.

## Kinematika audio

Hubungkan suara dengan tahap aksi:

- anticipation: gesekan, tarikan, breath, atau silence yang sengaja;
- action: material/motion sound yang mengikuti arah atau laju;
- contact: transient pada titik sentuh;
- recoil/follow-through: suara sekunder atau resonansi;
- settle: tail, rattling yang mereda, atau hening.

Onomatope dapat menjadi catatan kreatif, tetapi cue implementasi juga perlu menyebut material, envelope, durasi, jarak, dan intensitas.

## Sinkronisasi dan implementasi

Gunakan marker timeline atau timecode yang sama dengan visual. Jika memakai sample-accurate audio, sinkronkan terhadap clock audio sesuai API. Hindari memicu sound effect dari callback yang akan berjalan ulang ketika seek. Sediakan fungsi reset/seek audio untuk preview bila dibutuhkan.

Untuk timeline frame-based, konversi marker audio dan visual dengan timebase yang sama. Rekam layar browser bukan jaminan sinkronisasi presisi. Bila pipeline tidak dapat merender audio, sediakan cue sheet atau informasi implementasi yang jujur.

## Mix dan pemeriksaan

- Utamakan voice/aksi utama; turunkan musik atau ambience saat perlu.
- Kontrol peak dan hindari clipping; sesuaikan jarak dan reverb dengan ruang visual.
- Periksa awal/akhir, transisi, loop, klik/pop, silence tak sengaja, dan cue yang terlalu ramai.
- Dengarkan dengan headphone dan speaker biasa jika memungkinkan.
- Gunakan file audio yang pengguna sediakan atau yang hak pakainya jelas; simpan catatan lisensi pada project bila diperlukan.
