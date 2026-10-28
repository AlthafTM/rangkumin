# Rangkumin

**Catatan belajar dari sumber yang jelas, pengerjaan yang bisa diikuti, dan rumus yang enak dibaca.**

[Bahasa Indonesia](#bahasa-indonesia) · [English](#english) · [Skill](SKILL.md)

## Bahasa Indonesia

Rangkumin adalah skill untuk merangkum slide, modul, PDF, dan soal menjadi catatan belajar, pembahasan lengkap, atau cheatsheet. Skill ini mengarahkan asisten untuk membaca sumber terlebih dahulu, memeriksa jawaban, lalu mengecek keterbacaan hasilnya.

Instruksi utama ditulis dalam bahasa Inggris agar mudah dibagikan lintas alat. **Bahasa hasil mengikuti permintaan pengguna:** Indonesia, Inggris, atau bahasa lain. Tidak ada kewajiban menerjemahkan kode, simbol, maupun kutipan asli.

### Yang diatur

- Struktur per minggu, bab, topik, atau task; materi landasan dibuat secukupnya.
- Rumus beserta simbol, kondisi pemakaian, dan contoh. Pengerjaan memakai urutan rumus → substitusi → langkah hitung → hasil.
- Pilihan ganda dengan seluruh opsi dan jawaban; isian singkat secara langsung; blok isian dengan posisi dan pengisiannya.
- Pengecekan soal duplikat, transkripsi foto, kutipan, versi sumber, serta kesalahan pada slide atau opsi jawaban.
- Analisis algoritma: operasi yang dihitung, batas perulangan, sigma, best/worst/average, dan notasi asimtotik.
- Pseudocode, C++, tabel, dan diagram yang konsisten dengan sumber.
- Pemisahan rangkuman lengkap dan cheatsheet ringkas, serta pemeriksaan tampilan PDF/Word/slides.

### Pemasangan

Salin **`SKILL.md` dan seluruh folder `references/`** ke folder skill bernama `rangkumin`. Jangan hanya menyalin berkas utama karena panduan rinci ditautkan secara relatif. `agents/openai.yaml` adalah metadata tambahan untuk Codex dan tidak wajib untuk penggunaan manual.

| Lingkungan | Lokasi / cara pakai |
|---|---|
| Codex, satu proyek | `<proyek>/.agents/skills/rangkumin/` |
| Codex, pribadi | `~/.agents/skills/rangkumin/` |
| Claude Code, satu proyek | `<proyek>/.claude/skills/rangkumin/` |
| Claude Code, pribadi | `~/.claude/skills/rangkumin/` |
| ChatGPT atau Claude chat | Gunakan fitur skill yang tersedia pada akun/lingkungan tersebut. Alternatif manual: lampirkan `SKILL.md`, referensi yang relevan, dan materi, lalu minta asisten mengikuti panduannya. |

`~` berarti folder pengguna; pada Windows umumnya `%USERPROFILE%`. Mulai sesi baru atau muat ulang daftar skill bila skill belum muncul. Untuk proyek, salin isi paket ke direktori di atas, bukan menaruh `SKILL.md` langsung di `.agents/skills/` atau `.claude/skills/`.

Codex dapat dipanggil dengan `$rangkumin`; Claude Code dengan `/rangkumin`. Menempelkan berkas ke chat adalah penggunaan instruksi secara manual, bukan jaminan pemasangan skill otomatis. Ketersediaan OCR, pembacaan berkas, eksekusi kode, dan ekspor PDF bergantung pada alat serta izin lingkungan.

### Contoh permintaan

```text
Gunakan $rangkumin untuk merangkum modul ini per minggu dalam bahasa Indonesia.
Pertahankan semua rumus penting, sertakan contoh dari slide, lalu 2 soal baru
beserta pengerjaan lengkap. Buat PDF rangkuman dan PDF cheatsheet terpisah.
```

```text
/rangkumin Kerjakan soal pada foto ini. Gabungkan duplikat yang benar-benar sama.
Untuk pilgan, tulis semua opsi dan jawabannya. Untuk blok isian, gambarkan
posisinya dan isi setiap blok. Jika ada kesalahan pada soal, jelaskan singkat.
```

Untuk chat biasa, ganti `$rangkumin` atau `/rangkumin` dengan “Ikuti SKILL.md Rangkumin yang saya lampirkan.” Jika referensi pendukung belum bisa dibaca, lampirkan berkas yang disebut oleh skill; tautan relatif tidak otomatis memberikan akses ke GitHub.

### Isi paket

| Berkas | Kegunaan |
|---|---|
| [SKILL.md](SKILL.md) | Alur utama dan syarat hasil selesai |
| [sources.md](references/sources.md) | Membaca sumber, kutipan, versi, dan duplikat |
| [structure.md](references/structure.md) | Susunan rangkuman, contoh, hafalan, dan cheatsheet |
| [questions.md](references/questions.md) | Opsi jawaban, blok isian, matematika, kode, dan diagram |
| [algorithm-analysis.md](references/algorithm-analysis.md) | Aturan khusus analisis kompleksitas algoritma |
| [artifacts.md](references/artifacts.md) | Format keluaran dan pemeriksaan visual |
| [acceptance-cases.md](checks/acceptance-cases.md) | Kasus evaluasi perilaku untuk pengembangan skill |

Skill ini tidak menyertakan materi kuliah pribadi, jawaban pengguna, atau layanan ekspor. Jangan menganggap hasil otomatis benar: periksa sumber dan proses verifikasinya. Instruksi pengguna dan batas izin tetap berlaku.

## English

Rangkumin turns supplied learning materials and exercises into source-grounded study notes, worked solutions, and compact cheatsheets. Its workflow is: establish scope, inspect sources, organize content, solve step by step, verify independently, render and inspect, then deliver.

The canonical instructions are in English, but **output follows the user's requested language**, including Indonesian and languages beyond English. Original quotations must not be silently translated and presented as verbatim text.

### Install and use

Copy `SKILL.md` together with `references/` into a folder named `rangkumin`:

- Codex: `.agents/skills/rangkumin/` in a project, or `~/.agents/skills/rangkumin/` for personal use.
- Claude Code: `.claude/skills/rangkumin/` in a project, or `~/.claude/skills/rangkumin/` for personal use.
- ChatGPT / Claude chat: use supported skill features in your environment, or attach the instructions, relevant reference files, and source material and explicitly ask the assistant to follow them.

Invoke with `$rangkumin` in Codex or `/rangkumin` in Claude Code. For manual chat use, say “Follow the attached Rangkumin SKILL.md.” A relative reference link does not itself grant access to the repository: attach the referenced files when the assistant cannot read them. Native skill support, file access, OCR, code execution, and export capabilities depend on the host.

```text
Use $rangkumin to summarize these slides by chapter in English. Show formulas
before substitution and preserve the important assumptions. Include the original
worked examples, then two new exercises with complete solutions. Produce a study
guide PDF and a separate concise formula sheet.
```

The skill preserves original option letters, identifies genuine duplicates, maps fill-in boxes to values, checks source errors, and distinguishes exact operation counts from asymptotic bounds. It favors examples and short explanations while retaining all necessary solution steps. No personal course files or proprietary templates are bundled.

### Compatibility references

Installation guidance was checked on 28 October 2026 against [OpenAI's Build skills documentation](https://learn.chatgpt.com/docs/build-skills) and [Claude Code's skills documentation](https://code.claude.com/docs/en/skills). These document the respective skill directories and invocation mechanisms. Product interfaces and availability can change; manual instruction use is the fallback, not a claim of automatic native installation in every chat product.

### License

See the repository's existing [LICENSE](LICENSE).
