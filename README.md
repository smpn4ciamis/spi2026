# Monitoring Pengisian Google Form Siswa

Halaman web sederhana untuk membantu operator sekolah dan wali kelas mengecek siswa yang **sudah** dan **belum** mengisi Google Form untuk kelas:

- 7A s.d. 7G
- 8A s.d. 8G

## Cara pakai

1. Buka `index.html` di browser.
2. Isi daftar siswa per kelas pada bagian **Data Master Siswa** (satu nama per baris), lalu simpan.
3. Unduh respons Google Form sebagai **CSV**.
4. Unggah file CSV pada bagian **Import Jawaban Google Form**.
5. Pilih kolom **nama siswa** dan **kelas** (otomatis dicoba dideteksi jika ada kata "nama" dan "kelas").
6. Klik **Proses pengecekan**.
7. Lihat hasil per kelas: jumlah persen, daftar sudah isi, dan belum isi.

## Catatan

- Data daftar siswa disimpan di **localStorage browser** (lokal perangkat yang dipakai).
- Jika berpindah komputer/browser, data roster perlu diisi lagi.
