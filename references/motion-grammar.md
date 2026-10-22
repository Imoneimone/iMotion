# Motion Grammar: bahasa gerak untuk coding agent

Gunakan modul ini untuk menerjemahkan maksud visual menjadi prinsip animasi dan keputusan implementasi. Ini adalah pilihan, bukan resep wajib; pakai hanya unsur yang membantu aksi terbaca.

## 1. Aksi dan struktur temporal

Sebuah gerak yang jelas biasanya memiliki tiga aspek: kondisi awal yang bisa dibaca, perubahan yang dapat dilihat, dan kondisi akhir yang bermakna. Tambahkan fase sesuai kebutuhan:

- **Establish:** kenalkan subjek, ruang, arah, dan titik perhatian.
- **Anticipation:** siapkan arah/energi sebelum aksi; bisa berupa kompresi, arah pandang, perpindahan berat, jeda, atau gerakan berlawanan kecil.
- **Action:** perubahan utama, dengan jalur dan timing yang jelas.
- **Contact/impact:** momen hubungan sebab-akibat; dapat diberi aksen bentuk, kamera, suara, atau hold.
- **Follow-through:** bagian sekunder meneruskan gerak setelah massa utama berhenti.
- **Settle/recovery:** osilasi, pantulan, atau perpindahan berhenti secara bertahap dan meninggalkan pose akhir yang stabil.

Tidak semua fase perlu muncul eksplisit. Gerakan UI sederhana mungkin hanya membutuhkan masuk dan settle; gag slapstick mungkin perlu anticipation, contact, hold, recoil, dan recovery.

## 2. Timing, spacing, dan easing

**Timing** adalah berapa lama aksi berlangsung. **Spacing** adalah seberapa jauh nilai berubah antar-sampel waktu. Keduanya menentukan rasa gerak.

- Perpindahan dengan spacing merata terasa konstan/mekanis.
- Ease-in membangun laju; ease-out mengurangi laju; ease-in-out memulai dan berhenti dengan lembut.
- Overshoot dan recoil membantu gerak elastis, tetapi terlalu banyak membuat bobot hilang.
- Hold yang singkat di pose penting memberi waktu mata membaca bentuk atau reaksi.
- Aksi cepat yang diikuti settle lebih tegas daripada gerak yang selalu berosilasi.
- Pakai kurva dan durasi yang berbeda untuk massa utama, rambut/kain, prop, partikel, dan kamera.

Jangan memilih easing hanya karena nama preset terdengar menarik. Jelaskan hasil yang dicari—misalnya benda berat berhenti dengan momentum, tombol merespons cepat, atau karakter karet memantul—lalu pilih kurva yang menghasilkan rasa itu. Bila framework memberi custom easing, dokumentasikan parameter yang penting.

## 3. Hierarki gerak multiskala

Pisahkan gerak menjadi skala agar detail tidak saling berebut:

1. **Makro:** blocking, lintasan karakter, komposisi, perubahan kamera, perpindahan antar-area.
2. **Meso:** rotasi anggota tubuh, deformasi benda, teks, partikel kelompok, prop sekunder.
3. **Mikro:** getaran, smear, debu, kilau, gelembung, wobble, atau detail material.

Kunci gerak makro terlebih dahulu. Tambahkan detail mikro hanya pada event yang bermakna dan kurangi saat fokus berpindah. Detail dekoratif tidak boleh menjadi lebih kontras/cepat daripada aksi utama.

## 4. Kamera dan koreografi

Gunakan framing berdasarkan fungsi: wide untuk orientasi, medium untuk aksi tubuh, close-up untuk ekspresi/kontak, insert untuk detail. Pilih gerakan kamera yang jelas motivasinya:

- **Follow/track:** pertahankan aksi yang bergerak di dalam frame.
- **Push/pull:** alihkan perhatian atau ubah hubungan penonton dengan subjek.
- **Pan/tilt:** ungkap area atau ikuti lintasan.
- **Orbit/rotation:** tunjukkan relasi ruang hanya bila kedalaman relevan.
- **Locked camera:** biarkan aksi/staging sendiri yang bekerja; ini pilihan aktif, bukan kegagalan.

Hindari pan/zoom identik berulang. Untuk transisi, pertimbangkan objek yang menutupi frame, perubahan komposisi melalui aksi, match arah/bentuk, atau cut yang sinkron dengan impact. Pertahankan screen direction; bila perlu membalik arah, tunjukkan perpindahan sumbu dengan jelas.

## 5. Teks dan kinetic typography

Teks adalah objek animasi sekaligus informasi. Tentukan dahulu apa yang dibaca dan kapan. Gunakan pembagian baris, jeda, skala, posisi, mask, tracking, atau per-kata/per-huruf hanya jika mendukung aksen.

- Hindari menampilkan semua teks sekaligus jika narasi ingin diungkap bertahap.
- Gunakan panjang teks yang sesuai waktu baca dan ukuran layar.
- Jangan animasikan semua kata dengan efek seragam bila yang penting hanya satu kata.
- Jaga safe area, kontras, dan keterbacaan saat bergerak.
- Gunakan pengulangan motif tipografi sebagai sistem, bukan sebagai template otomatis di tiap shot.

## 6. Transisi

Pilih transisi berdasarkan hubungan beat, bukan demi variasi. Jenis yang dapat digunakan: cut, match cut, object wipe, mask reveal, perubahan fokus, gerak kamera berkesinambungan, transformasi bentuk, atau perpindahan objek. Pastikan state masuk shot berikutnya konsisten dengan akhir shot sebelumnya.

Periksa apakah transisi menambah makna, menjaga orientasi, dan tidak menyembunyikan aksi yang harus dilihat. Bila tidak membantu, cut sederhana dapat menjadi pilihan terbaik.
