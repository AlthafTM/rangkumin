# Rangkumin

**Catatan belajar dari sumber yang jelas, pengerjaan yang bisa diikuti, dan keluaran rapi dalam format PDF, PPT, Word, maupun Gambar.**

[Bahasa Indonesia](#bahasa-indonesia) · [English](#english) · [Skill](SKILL.md)

## Bahasa Indonesia

Rangkumin adalah skill AI untuk merangkum slide kuliah, modul, PDF, buku teks, dan soal latihan menjadi catatan belajar, pembahasan lengkap, slide presentasi ringkas, cheatsheet, atau gambar ringkasan visual. Skill ini mengarahkan asisten untuk membaca sumber terlebih dahulu, menjaga kelengkapan materi, memverifikasi jawaban secara mandiri, lalu mengecek tampilan visual hasil akhirnya.

Instruksi utama ditulis dalam bahasa Inggris agar konsisten dan mudah dipakai lintas alat AI. **Bahasa hasil selalu mengikuti permintaan pengguna:** Indonesia, Inggris, atau bahasa lainnya. Kode, simbol, dan kutipan asli tetap dijaga keasliannya.

### Format keluaran yang didukung

- **PDF (Rangkuman / Cheatsheet):** Ringkas, jelas, mudah dibaca, dan mencakup **seluruh materi modul secara lengkap** kecuali pengguna meminta pemfilteran topik. Rumus terformat rapi (bukan teks LaTeX mentah).
- **PPT / PPTX (Presentasi):** Berbasis **poin-poin singkat** (bukan paragraf panjang), variasi layout, dilengkapi visual cues, tabel perbandingan, diagram, atau grafik bila relevan, dengan palet warna bersih dan **tanpa gradien warna aneh**.
- **Word / DOCX:** Dokumen yang benar-benar bisa diedit (heading asli, tabel editable, daftar rapi, mengikuti template bila diberikan).
- **Gambar (PNG / JPG):** Kartu ringkasan visual, diagram konsep, tabel perbandingan, atau lembar rumus beresolusi tinggi, bersih, kontras tinggi, dan bebas tumpukan teks.
- **Teks Chat / Markdown:** Langsung di chat tanpa membuat berkas bila pengguna meminta teks saja.

### Yang diatur

- Alur kerja terstruktur: identifikasi tugas → inventaris & verifikasi sumber → susun struktur belajar → pengerjaan langkah demi langkah → pengecekan fakta mandiri → render & inspeksi visual.
- Struktur per minggu, bab, modul, atau soal dengan urutan ketergantungan konsep serta tabel perbandingan istilah yang mudah tertukar.
- Rumus beserta simbol, kondisi pemakaian, dan contoh dari sumber. Urutan pengerjaan: rumus → substitusi → langkah hitung → hasil dan syarat.
- Pilihan ganda dengan seluruh opsi dan huruf aslinya; isian singkat langsung; blok isian dengan posisi dan pemetaan nilainya.
- Pengecekan soal duplikat, transkripsi foto/OCR, kutipan, versi sumber, serta kesalahan pada slide atau kunci jawaban.
- Analisis algoritma: operasi yang dihitung, batas perulangan, sigma, best/worst/average, dan notasi asimtotik.
- Pemrograman & Struktur Data: **Notasi Algoritmik / pseudocode (Rinaldi Munir ITB & Telkom University)**, **Go (Golang)**, dan **C++** — mengikuti contoh referensi dosen/modul bila diberikan.
- Standar desain visual bersih: palet solid/flat berkontras tinggi, whitespace cukup, tanpa gradien warna aneh atau dekorasi mengganggu.

### Pemasangan

Salin **`SKILL.md` dan seluruh folder `references/`** ke folder skill bernama `rangkumin`. Jangan hanya menyalin berkas utama karena panduan rinci ditautkan secara relatif. `agents/openai.yaml` adalah metadata tambahan untuk Codex dan tidak wajib untuk penggunaan manual.

| Lingkungan | Lokasi / cara pakai |
|---|---|
| Antigravity / Codex, satu proyek | `<proyek>/.agents/skills/rangkumin/` |
| Codex, pribadi | `~/.agents/skills/rangkumin/` |
| Claude Code, satu proyek | `<proyek>/.claude/skills/rangkumin/` |
| Claude Code, pribadi | `~/.claude/skills/rangkumin/` |
| ChatGPT atau Claude chat | Gunakan fitur skill yang tersedia pada akun/lingkungan tersebut. Alternatif manual: lampirkan `SKILL.md`, referensi yang relevan, dan materi, lalu minta asisten mengikuti panduannya. |

`~` berarti folder pengguna; pada Windows umumnya `%USERPROFILE%`. Mulai sesi baru atau muat ulang daftar skill bila skill belum muncul. Untuk proyek, salin isi paket ke direktori di atas, bukan menaruh `SKILL.md` langsung di `.agents/skills/` atau `.claude/skills/`.

Codex dapat dipanggil dengan `$rangkumin`; Claude Code dengan `/rangkumin`. Menempelkan berkas ke chat adalah penggunaan instruksi secara manual, bukan jaminan pemasangan skill otomatis. Ketersediaan OCR, pembacaan berkas, eksekusi kode, dan ekspor PDF/PPTX/DOCX/Gambar bergantung pada alat serta izin lingkungan.

### Contoh permintaan

```text
Gunakan $rangkumin untuk merangkum modul ini per minggu dalam bahasa Indonesia.
Pastikan seluruh materi modul masuk secara ringkas dan jelas, pertahankan semua
rumus penting dan contoh dari slide, lalu buat PDF rangkuman dan PDF cheatsheet terpisah.
```

```text
/rangkumin Buat PPT ringkasan dari modul ini dalam bahasa Indonesia. Buat poin-poin
singkat saja (jangan penuh teks), tambahkan diagram alur dan grafik perbandingan
dengan desain yang bersih tanpa gradien aneh.
```

```text
/rangkumin Kerjakan soal pada foto ini. Gabungkan duplikat yang benar-benar sama.
Untuk pilgan, tulis semua opsi dan jawabannya. Untuk blok isian, gambarkan
posisinya dan isi setiap blok. Jika ada kesalahan pada soal, jelaskan singkat.
```

### Isi paket

| Berkas | Kegunaan |
|---|---|
| [SKILL.md](SKILL.md) | Alur utama, routing format (PDF/PPT/Word/Gambar), dan syarat hasil selesai |
| [sources.md](references/sources.md) | Membaca sumber, kutipan, versi, dan duplikat |
| [structure.md](references/structure.md) | Susunan rangkuman, kelengkapan modul, tabel perbandingan, dan cheatsheet |
| [questions.md](references/questions.md) | Opsi jawaban, blok isian, matematika, kode, dan diagram |
| [programming.md](references/programming.md) | Konvensi Notasi Algoritmik (Rinaldi Munir ITB / Telkom University), Go (Golang), dan C++ |
| [algorithm-analysis.md](references/algorithm-analysis.md) | Aturan khusus analisis kompleksitas algoritma |
| [artifacts.md](references/artifacts.md) | Standar desain visual & kualitas PDF, PPT/PPTX, Word, dan Gambar |
| [acceptance-cases.md](checks/acceptance-cases.md) | Kasus evaluasi perilaku untuk pengembangan skill |

Skill ini tidak menyertakan materi kuliah pribadi, jawaban pengguna, atau layanan ekspor. Jangan menganggap hasil otomatis benar: periksa sumber dan proses verifikasinya. Instruksi pengguna dan batas izin tetap berlaku.

---

## English

Rangkumin turns school and university learning materials, slides, modules, and exercises into source-grounded study summaries, worked solutions, presentation decks, visual study cards, and compact cheatsheets—across **PDF, PowerPoint (PPT/PPTX), Word (DOCX), Images (PNG/JPG), and chat Markdown**.

Its workflow is: establish scope, inspect and map sources, structure for learning, solve step by step, fact-check independently, build and visually inspect, then deliver.

### Supported Output Formats

- **PDF (Study Guide / Cheatsheet):** Concise, clear, and covers **all module material by default** unless the user narrows scope. Properly typeset math, clean tables, and readable page flow.
- **PPT / PPTX (Slide Decks):** **Point-by-point takeaways** instead of full-text paragraphs, varied layouts, clean diagrams and graphs where helpful, and restrained flat high-contrast palettes (**no weird color gradients**).
- **Word / DOCX:** Truly editable documents using native headings, lists, tables, and template fidelity.
- **Images (PNG / JPG):** Crisp, high-resolution visual summaries, comparison tables, concept diagrams, and formula cards with clean flat styling.
- **Coding & Programming:** Supports **Notasi Algoritmik pseudocode (Rinaldi Munir ITB & Telkom University)**, **Go (Golang)**, and **C++**, adopting any supplied course/lecturer reference example automatically.

The canonical instructions are in English, while **output follows the user's requested language** (including Indonesian and other languages). Original quotations are never silently translated and presented as verbatim text.

### Install and Use

Copy `SKILL.md` together with `references/` into a folder named `rangkumin`:

- Antigravity / Codex: `.agents/skills/rangkumin/` in a project, or `~/.agents/skills/rangkumin/` for personal use.
- Claude Code: `.claude/skills/rangkumin/` in a project, or `~/.claude/skills/rangkumin/` for personal use.
- ChatGPT / Claude chat: use supported skill features in your environment, or attach `SKILL.md`, relevant reference files, and source material and explicitly ask the assistant to follow them.

Invoke with `$rangkumin` in Codex or `/rangkumin` in Claude Code. For manual chat use, say “Follow the attached Rangkumin SKILL.md.” Native skill support, file access, OCR, code execution, and export capabilities depend on the host.

```text
Use $rangkumin to summarize this university module into a concise, complete PDF
study guide and a point-by-point PPTX review deck with clean diagrams (no weird
color gradients). Include all module formulas and worked examples.
```

### Compatibility References

Installation guidance was checked against OpenAI's Build skills documentation, Claude Code's skills documentation, and the Agent Skills (`SKILL.md`) specification. Product interfaces and availability can change; manual instruction attachment remains the fallback.

### License

See the repository's existing [LICENSE](LICENSE).
