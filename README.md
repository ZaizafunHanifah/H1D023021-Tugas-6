# H1D023021-Tugas-6

## Penjelasan Proses Passing Data

Aplikasi ini memiliki dua halaman utama:
1. Halaman Input Data (form_data.dart)
2. Halaman Perkenalan (tampil_data.dart)

### Proses Pengiriman Data

1. **Pengisian Form**
   - User mengisi form yang berisi:
     - Nama Lengkap
     - Nomor Induk Mahasiswa (NIM)
     - Tahun Lahir
   - Setiap field memiliki validasi untuk memastikan data terisi dengan benar
   - Data diisi menggunakan TextEditingController untuk mengelola input

2. **Proses Pengiriman**
   - Saat user menekan tombol "Simpan", aplikasi akan:
     - Memeriksa apakah semua data valid
     - Mengambil nilai dari setiap controller menggunakan .text.trim()
     - Menyiapkan data untuk dikirim ke halaman berikutnya

3. **Perpindahan Halaman**
   - Menggunakan Navigator.push untuk berpindah ke halaman Perkenalan
   - Data dikirim melalui constructor TampilData
   - Contoh kode: 
     ```dart
     Navigator.of(context).push(
       MaterialPageRoute(
         builder: (_) => TampilData(
           name: _nameController.text.trim(),
           nim: _nimController.text.trim(),
           tahun: _tahunController.text.trim(),
         ),
       ),
     );
     ```

4. **Penerimaan Data**
   - Halaman Perkenalan menerima data melalui parameter constructor
   - Data yang diterima disimpan dalam variable final
   - Data ditampilkan dalam format yang rapi menggunakan Card dan Container

### Hasil Aplikasi

![Halaman Input Data](input_data.jpg)
![Halaman Perkenalan](perkenalan.jpg)

Demikian penjelasan tentang proses pengiriman (passing) data dari halaman form menuju halaman tampilan pada aplikasi ini.
