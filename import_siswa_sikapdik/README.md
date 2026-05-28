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

## Sumber Data

`daftar_pd-SD NEGERI 4 JATIGUNUNG-2.xlsx` (export Dapodik) — sudah berisi seluruh
kolom yang dibutuhkan (JK, Tempat Lahir, Tanggal Lahir).

## Pemetaan Kolom

| Template (Tujuan) | Sumber Dapodik |
|---|---|
| `No` | nomor urut otomatis (1..N) |
| `NIS *` | `NIPD` |
| `NISN` | `NISN` |
| `NAMA LENGKAP *` | `Nama` (di-Title Case) |
| `JENIS KELAMIN *` | `JK` (L / P) |
| `TEMPAT LAHIR` | `Tempat Lahir` (di-Title Case) |
| `TANGGAL LAHIR` | `Tanggal Lahir` → format `DD/MM/YYYY` |
| `ALAMAT` | gabungan `Dusun, RT/RW, Desa <Kelurahan>, Kec. ..., Kab. Pacitan` |

Pengelompokan kelas memakai kolom `Rombel Saat Ini` dari Dapodik.

## Catatan

- Format header, styling, kolom, dan struktur file mengikuti template asli secara persis.
- Siswa di setiap kelas diurutkan alfabetis berdasarkan nama.
- NIS, NISN, dan Tanggal Lahir disimpan sebagai teks (`@`) untuk menjaga leading zero & konsistensi format.
