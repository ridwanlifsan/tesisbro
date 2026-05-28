# Import Siswa SIKAPDIK – SD Negeri 04 Jatigunung

Hasil konversi data dari `NAMA PD V1.1.xlsx` ke format `Template_Import_Siswa_SIKAPDIK.xlsx`,
dipecah per kelas (6 file).

## File

| File | Jumlah Siswa |
|---|---|
| `Template_Import_Siswa_SIKAPDIK_Kelas1.xlsx` | 10 |
| `Template_Import_Siswa_SIKAPDIK_Kelas2.xlsx` | 7 |
| `Template_Import_Siswa_SIKAPDIK_Kelas3.xlsx` | 11 |
| `Template_Import_Siswa_SIKAPDIK_Kelas4.xlsx` | 11 |
| `Template_Import_Siswa_SIKAPDIK_Kelas5.xlsx` | 6 |
| `Template_Import_Siswa_SIKAPDIK_Kelas6.xlsx` | 12 |
| **Total** | **57** |

## Pemetaan Kolom

| Template (Tujuan) | Sumber |
|---|---|
| `No` | nomor urut otomatis (1..N) |
| `NIS *` | kolom `NIS` |
| `NISN` | kolom `NISN` |
| `NAMA LENGKAP *` | kolom `Nama` (di-Title Case) |
| `JENIS KELAMIN *` | **(kosong – tidak tersedia di sumber)** |
| `TEMPAT LAHIR` | **(kosong – tidak tersedia di sumber)** |
| `TANGGAL LAHIR` | **(kosong – tidak tersedia di sumber)** |
| `ALAMAT` | gabungan `Dusun, RT/RW, Kelurahan, Kecamatan, Kabupaten` |

## Catatan

- Format header, styling, kolom, dan struktur file mengikuti template asli secara persis.
- Siswa di setiap kelas diurutkan alfabetis berdasarkan nama.
- Kolom `JENIS KELAMIN`, `TEMPAT LAHIR`, dan `TANGGAL LAHIR` perlu diisi manual karena tidak ada di file sumber.
- NIS & NISN disimpan sebagai teks (`@`) untuk menjaga leading zero.
