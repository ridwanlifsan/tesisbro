# Akun Login Orang Tua – SD Negeri 04 Jatigunung

File: `Akun_Login_Orang_Tua.xlsx` — daftar 57 akun login untuk orang tua siswa,
dirancang ringkas dan **ramah parser komputer** (1 sheet, 1 baris per record,
header di baris 1, tanpa merged cell, tanpa multi-row header).

## Sumber

`daftar_pd-SD NEGERI 4 JATIGUNUNG-2.xlsx` (export Dapodik).

## Kolom

| # | Kolom | Sumber / Aturan |
|---|---|---|
| 1 | `No` | nomor urut 1..57 |
| 2 | `Nama Siswa` | kolom Dapodik `Nama` |
| 3 | `NIS` | kolom Dapodik `NIPD` (text, leading-zero aman) |
| 4 | `NISN` | kolom Dapodik `NISN` (text) |
| 5 | `Nama Orang Tua` | utamakan `Nama Ayah`, fallback ke `Nama Ibu` jika ayah kosong |
| 6 | `Hubungan` | `Ayah` atau `Ibu` (auto-detect) |
| 7 | `No HP` | kolom Dapodik `HP`, fallback `Telepon` (text) |
| 8 | `Username` | `<nama_awal_ortu_lowercase><NNN>` |
| 9 | `Password` | sama persis dengan Username |

## Aturan Generate Username

1. Ambil **kata pertama** dari Nama Orang Tua, lowercase, hapus tanda baca/angka.
2. Jika kata pertama < 3 huruf (mis. inisial `S.`), gunakan kata berikutnya yang ≥ 3 huruf
   (contoh: `S. RIYONO` → `riyono`).
3. Tambahkan **3 digit angka unik** sekuensial (`001`..`057`) sebagai suffix.

Hasil: setiap username pasti unik meskipun beberapa siswa memiliki orang tua dengan
nama yang sama (misalnya kakak-adik atau nama generik seperti `SISWANTO`, `UNTUNG`, `SLAMET`).

## Format File (ramah komputer)

- 1 sheet (`Akun Login Orang Tua`)
- Header tunggal di baris 1 (tidak ada title/sub-header tambahan)
- Tidak ada merged cells
- `NIS`, `NISN`, `No HP`, `Username`, `Password` di-format sebagai **TEXT** (`@`) →
  leading zero (`0152806553`, `082262189171`, dll.) tidak hilang saat dibaca
  parser/CSV converter.
- Freeze pane di baris 1 untuk keperluan view manusia.
