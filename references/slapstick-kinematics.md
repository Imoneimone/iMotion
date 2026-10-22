# Slapstick Kinematics: aksi, transformasi, dan recovery

Gunakan untuk karakter 2D, gag fisik, deformasi, dan transformasi material bergaya. Utamakan keterbacaan; ini bukan simulasi fisika ilmiah.

## 1. Bangun gag sebagai rantai sebab-akibat

Tentukan:

1. **Intent:** apa yang diinginkan karakter?
2. **Setup:** benda/ruang apa yang memungkinkan atau mengancam tujuan itu?
3. **Trigger:** kejadian spesifik yang memulai gag.
4. **Escalation:** aksi atau komplikasi yang memperbesar masalah.
5. **Payoff:** transformasi, impact, reveal, atau reaksi yang menyelesaikan gag.
6. **Recovery/button:** pose akhir atau respons yang memberi rasa selesai.

Penonton harus dapat menghubungkan pemicu dengan akibat. Jika aksi terlalu kompleks, sederhanakan rangkaian sebab-akibat sebelum menambah smear, partikel, atau kamera.

## 2. Fase gerak slapstick

Urutan yang sering berguna:

- **Anticipation:** pose mengarah ke aksi atau reaksi; pandangan membantu menunjukkan perhatian.
- **Tension/hold:** tahan tepat sebelum/di kontak untuk memperjelas ekspektasi atau shock. Jangan menahan tanpa alasan.
- **Action:** perpindahan utama, terpeleset, tarikan, benturan, kompresi, pecah, atau transformasi.
- **Reaction/recoil:** tubuh dan bagian sekunder bereaksi sesuai arah energi bergaya.
- **Follow-through:** telinga, ekor, kain, prop, dan partikel menyusul dengan timing berbeda.
- **Settle/recovery:** bagian kembali stabil atau karakter mengambil pose/ekspresi akhir.

Dalam komedi, jeda ekspresi sering lebih penting daripada menambah gerak. Sesuaikan timing dengan intensi dan durasi.

## 3. Pertahankan identitas ketika bentuk berubah

Sebelum mengodekan transformasi, catat fitur identitas yang harus bertahan, misalnya proporsi kepala, warna, pola, aksesori, posisi mata, atau siluet khas. Tentukan:

- Bagian mana yang tetap, bergeser, terkompresi, memanjang, terpisah, atau berubah material.
- Anchor mana yang menjaga hubungan bagian (mata/wajah, anggota tubuh, prop, titik kontak).
- Bagaimana orientasi dan arah pandang tetap terbaca.
- State visual per tahap transformasi dan state akhir yang dapat dipulihkan.
- Apakah volume hanya ilusi artistik, atau benar-benar perlu dipertahankan oleh rig.

Squash-and-stretch adalah gaya visual, bukan hukum konservasi literal. Jaga konsistensi yang dibutuhkan oleh karakter, bukan angka fisika yang tidak terlihat.

## 4. Interaksi dengan benda dan material

Tentukan titik kontak, arah gaya yang tampak, respons benda, dan urutan geraknya. Untuk setiap material, pilih sedikit ciri visual/auditori:

- **Karet/gelatin:** kompresi, stretch, recoil, wobble yang mereda.
- **Logam:** rigid body, rotasi/pantulan tegas, resonansi/settle singkat.
- **Kain:** lag, lipatan, drag, overshoot.
- **Cairan:** slosh/splash dengan arah dan settle; batasi agar bentuk utama tidak hilang.
- **Granular:** cloud/pecahan menyebar dengan arah, lalu partikel kecil berhenti.
- **Kertas/kayu:** lipatan, dent, pecah, atau snap berdasarkan gaya desain.

Jangan mencoba meniru seluruh simulasi bila cue visual sederhana cukup menjelaskan aksi. Buat kontak terasa terjadi: objek tidak boleh saling menembus kecuali itu adalah deformasi yang disengaja.

## 5. Smear, getaran, dan detail mikro

- Smear mengikuti arah dan kecepatan gerak; batasi pada jendela waktu aksi cepat.
- Recoil dimulai setelah impact dan mereda menuju settle; amplitudo/frekuensi adalah parameter artistik.
- Partikel harus punya sumber, arah, jumlah yang wajar, dan akhir hidup. Hindari debris tanpa sebab.
- Getaran lebih efektif sebagai aksen pendek pada kontak/mesin daripada lapisan permanen.
- Detail mikro jangan menutupi wajah, siluet, teks, atau objek payoff.

Gunakan kurva deterministik atau seed tetap untuk procedural detail bila hasil perlu di-seek/render berulang.

## 6. Rig dan state machine

Untuk rig sederhana, beri nama bagian berdasarkan fungsi dan tetapkan pivot sebelum animasi. Untuk aksi dengan tahap eksplisit, pertimbangkan state machine atau keyframe state bernama seperti `anticipate`, `contact`, `compress`, `recoil`, `settle`. Pastikan transisi state memiliki waktu masuk/keluar dan tidak memicu ulang event audio ketika timeline di-seek.

Uji tiap tahap sebagai frame diam: jika pose kunci tidak terbaca sendiri, perbaiki staging sebelum menambah gerakan.
