# Output Profiles: kebutuhan deliverable

Tentukan output sejak awal. Checklist ini membantu memilih perilaku dan verifikasi; bukan keharusan memakai stack tertentu.

## Browser motion

Pastikan cara membuka proyek dan dependensi. Tentukan autoplay, play/pause, restart, scrub, serta perilaku saat tab tidak aktif. Perhatikan reduced motion dan aksesibilitas bila ini UI. Kebijakan autoplay audio browser dapat mewajibkan interaksi pengguna. Uji viewport, resize, font loading, dan performa.

## Motion pendek dan loop

Rancang pose awal/akhir yang kompatibel. Periksa transisi pada batas loop dan jangan biarkan audio reset kasar kecuali disengaja. Tentukan durasi, safe area, hierarki fokus, dan perilaku restart.

## Frame-accurate rendering

Tetapkan FPS, dimensi, total frame, timebase, dan asumsi warna. Semua animasi harus bisa di-seek ke frame arbitrer dengan state yang konsisten. Render frame awal, puncak, transisi, akhir, dan frame sekitar cut/impact. Sinkronkan audio memakai marker/timecode sama. Playback real-time tidak menjamin ekspor frame-perfect.

## Video export

Gunakan pipeline yang sesuai proyek. Pastikan font, media, dan aset tersedia saat render. Periksa dimensi/aspect ratio, FPS, durasi, codec/container, audio, dan frame akhir dari file aktual; tonton hasil penuh. Jelaskan bila yang tersedia hanya rekam layar karena frame dapat terlewat. Jangan menjanjikan format atau resolusi yang tidak didukung tool.

## Explainer/narasi

Biarkan visual membawa informasi; satu kalimat narasi tidak selalu perlu satu scene baru. Beri waktu membaca data, peta, label, dan bukti. Jangan mengarang fakta/angka. Susun perhatian: aksi/claim, bukti, lalu detail.

## Motion UI

Prioritaskan feedback, status, dan affordance. Durasi mendukung usability, tidak menunda tindakan. Uji state hover/focus/pressed/loading/success/error, keyboard/touch, dan reduced motion sesuai konteks.
