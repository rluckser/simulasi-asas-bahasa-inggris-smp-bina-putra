# Simulasi ASAS Bahasa Inggris SMP Bina Putra

Website tes soal prediksi ASAS — Bahasa Inggris Kelas VIII dan IX, ASAS Ganjil 2026/2027,
berdasarkan kisi-kisi MGMP Bahasa Inggris SMP Kabupaten Lampung Tengah.

**Dibuat oleh Jelly Dharmawan S.Pd.**

Pilih kelas di awal (Kelas 8 atau Kelas 9); tiap kelas punya bank soalnya sendiri.
Kelas 8 tetap berperilaku seperti sebelumnya.

- **45 soal per sesi**, waktu **120 menit** (timer hitung mundur, otomatis mengumpulkan saat habis)
- **Bank soal 90 soal per kelas**: 2 varian (A/B) untuk tiap indikator 1–45. Tiap sesi diambil 1 varian acak per indikator, lalu urutan soal diacak di dalam tiap jenis soal dan pilihan jawaban PG diacak.
- Urutan soal mengikuti kisi-kisi. Kelas 8: Pilihan Jamak (1–25), Benar-Salah (26–30), Menjodohkan (31–35), Isian Singkat (36–40), Uraian (41–45). Kelas 9: Pilihan Jamak (1–25), Benar-Salah (26–30), Menjodohkan (31–35), Uraian Singkat (36–40), Essay (41–45).
- **Skor otomatis** dari 35 soal: Pilihan Jamak (25), Benar-Salah (5), Menjodohkan (5). Nilai 0–100.
- **Cek mandiri** untuk 10 soal: Kelas 8 — Isian Singkat (5) dan Uraian (5); Kelas 9 — Uraian Singkat (5) dan Essay (5). Tampil kunci jawaban dan pembahasan, tidak masuk skor otomatis. Isian Singkat dijawab dengan satu kata atau frasa pendek.
- Menjodohkan: tiap soal menampilkan 5 pilihan, yaitu jawaban dari kelima soal Menjodohkan pada sesi itu.
- Soal bergambar: Kelas 8 — 10 soal (indikator 13, 15, 16, 19, 20 × 2 varian); Kelas 9 — 8 soal (indikator 1, 3, 33, 44 × 2 varian), dengan ilustrasi SVG di `assets/img/`.
- Riwayat skor tersimpan di `localStorage` perangkat siswa, dengan label kelas (VIII/IX).

## Distribusi materi

### Kelas 8

| Materi | Soal |
|---|---|
| Inviting Someone to Do Something | 5 |
| Asking and Giving Permission | 6 |
| Asking and Giving Opinion | 4 |
| Prohibition | 3 |
| Obligation | 2 |
| Instruction | 2 |
| Suggestion | 2 |
| Announcement | 4 |
| Descriptive Text | 7 |
| Menjodohkan: Inviting, Permission, Opinion, etc. | 5 |
| Isian Singkat: Invitation, Obligation, Suggestion | 5 |

### Kelas 9

| Materi | Soal |
|---|---|
| Congratulating | 3 |
| Complimenting | 3 |
| Hope and Wish | 4 |
| Agreement and Disagreement | 5 |
| Procedure Text | 10 |
| Report Text | 13 |
| Label | 7 |

## Struktur file

```
index.html                  Halaman utama (beranda, tes, hasil) + pemilih kelas
assets/css/style.css        Gaya tampilan (tema teal-biru)
assets/js/main.js           Logika: pemilih kelas, pengacakan, timer, penilaian, riwayat
assets/data/questions.json  Bank soal gabungan Kelas 8 (90 soal)
assets/data/questions-9.json Bank soal gabungan Kelas 9 (90 soal)
assets/img/eng-*.svg        Ilustrasi soal Kelas 8 (10 file)
assets/img/eng9-*.svg       Ilustrasi soal Kelas 9 (8 file)
bank/                       Bank soal Kelas 8 per bentuk soal (sumber, sebelum digabung)
bank-9/                     Bank soal Kelas 9 per bentuk soal (sumber, sebelum digabung)
```

## Menjalankan lokal

Dari folder ini, jalankan server statis (jangan buka `index.html` langsung dari file,
karena bank soal dimuat lewat `fetch`):

```bash
python3 -m http.server 8000
```

Lalu buka http://localhost:8000 di browser.

## Publish ke GitHub Pages

1. Buat repository baru bernama `simulasi-asas-bahasa-inggris-smp-bina-putra`.
2. Unggah semua file di folder ini ke branch `main`, di root repository.
3. Di repository, buka **Settings → Pages**, pilih **Deploy from a branch**,
   branch `main`, folder `/ (root)`, lalu simpan.
4. Situs akan live di `https://<username>.github.io/simulasi-asas-bahasa-inggris-smp-bina-putra/`.
