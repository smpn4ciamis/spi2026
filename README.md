# Monitoring Pengisian Google Form Siswa

Halaman web sederhana untuk membantu operator sekolah dan wali kelas mengecek siswa yang **sudah** dan **belum** mengisi Google Form untuk kelas:

- 7A s.d. 7G
- 8A s.d. 8G

## Cara pakai inti

1. Buka `index.html` di browser.
2. Isi daftar siswa per kelas pada bagian **Data Master Siswa** (satu nama per baris), lalu simpan.
3. Unduh respons Google Form sebagai **CSV** (boleh beberapa file sekaligus, misalnya per-hari/per-form).
4. Unggah satu atau beberapa file CSV pada bagian **Import Jawaban Google Form**.
5. Pilih kolom **nama siswa** dan **kelas** (otomatis dicoba dideteksi jika ada kata "nama" dan "kelas").
6. Klik **Proses pengecekan**.
7. Lihat hasil per kelas: jumlah persen, daftar sudah isi, dan belum isi.

## Cara akses web bagi wali kelas

### Opsi A (paling cepat di jaringan sekolah/LAN)

1. Operator simpan folder ini di komputer operator.
2. Jalankan server sederhana dari folder project:

   ```bash
   python3 -m http.server 4173 --bind 0.0.0.0
   ```

3. Cek IP komputer operator (contoh `192.168.1.10`).
4. Wali kelas yang satu jaringan buka:

   `http://192.168.1.10:4173`

> Catatan: pastikan firewall mengizinkan port `4173`.

### Opsi B (dibuka langsung tanpa server)

- Kirim file `index.html` ke wali kelas.
- Wali kelas cukup klik dua kali file tersebut di browser.

### Berbagi data roster dari operator ke wali kelas

Karena data roster disimpan lokal di browser, lakukan alur berikut agar data sama:

1. Operator klik **Export roster (.json)**.
2. Kirim file `roster-siswa.json` ke wali kelas (WA/Drive/email).
3. Wali kelas buka web, lalu **Import roster dari operator (.json)**.
4. Wali kelas tinggal unggah satu/lebih file CSV terbaru untuk melihat siapa yang belum/sudah mengisi.

## Catatan

- Data daftar siswa disimpan di **localStorage browser** (lokal perangkat yang dipakai).
- Jika berpindah komputer/browser, data roster perlu diisi lagi atau import dari file JSON export.
