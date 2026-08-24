# Changelog — RK-Lab Mass Calc (mass-calc_v5.html)

## [Released] — Perubahan basis satuan (meter & kg)

### Diubah
- **Basis dimensi internal**: dari **cm** → **meter**. Semua input dimensi (mm/cm/m/ft) tetap bisa dipilih bebas per kolom seperti biasa, tapi sekarang dikonversi ke meter dulu sebelum dihitung volumenya (sebelumnya dikonversi ke cm).
- **Basis massa jenis**: dari **g/cm³** → **kg/m³** langsung. Karena volume sekarang dalam m³, densitas material (disimpan di data dalam g/cm³) dikonversi otomatis ×1000 ke kg/m³ saat perhitungan. Densitas custom yang diinput user juga langsung dipakai sebagai kg/m³ tanpa konversi tambahan.
- **Hasil massa**: `volume (m³) × densitas (kg/m³) = massa (kg)` langsung — tidak ada lagi tahap konversi gram → kg seperti sebelumnya.
- **Preferensi tampilan satuan massa**: kg sekarang jadi satuan utama (bukan gram). Kalau hasilnya besar (≥1.000 kg / 1 ton), otomatis ditambahkan info `(≈ X ton)` di sebelah nilai kg — nilai kg tetap dicantumkan, tidak diganti.
- **Presisi angka**: nilai di bawah 1 kg ditampilkan dengan 5 desimal (biar objek ringan tetap kebaca, ga jadi `0,000 kg`); nilai ≥1 kg pakai 3 desimal.
- **Tampilan Volume (1 pcs)**: satuan diganti dari `cm³` → `m³`, dengan desimal adaptif (8 digit kalau volumenya <1 m³, 4 digit kalau ≥1 m³).
- **Label toggle satuan hasil**: "GRAM / KG" → **"KG / TON"** (menyesuaikan preferensi baru, gram sudah tidak dipakai di jalur metrik).
- **Langkah "Rumus & Penyelesaian"**: seluruh langkah konversi satuan dan substitusi rumus disesuaikan ke basis meter. Langkah konversi densitas g/cm³↔kg/m³ dihapus karena sudah tidak diperlukan (densitas langsung dalam kg/m³).

### Tidak berubah
- Pilihan satuan input per kolom (mm/cm/m/ft) di form tetap ada, default tetap cm.
- Semua 8 bentuk (kubus, balok, tabung, pipa, bola, kerucut, IWF/WF, hollow), daftar material, fitur berat wadah, dan toleransi beban tidak berubah logikanya.
- Mode satuan Imperial (oz/lbs) tidak berubah, tetap dihitung dari hasil kg yang dikonversi ke gram internal untuk keperluan oz/lbs.
