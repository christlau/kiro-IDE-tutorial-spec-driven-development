# 🎸 Kiro IDE — Spec-Driven Development Tutorial
### Panduan Lengkap Membangun Website Produk dengan AWS Kiro + Agentic AI

> 📺 **Tonton tutorial lengkapnya di YouTube:**  

***

## 📖 Tentang Repository Ini

Repository ini adalah **companion resource** untuk tutorial YouTube tentang cara membangun website e-commerce produk gitar menggunakan **Kiro IDE** dari AWS — sebuah agentic IDE yang menerapkan pendekatan *Spec-Driven Development*.

Di sini kamu akan menemukan dua prompt siap pakai yang digunakan dalam video:

| File | Kegunaan |
|------|----------|
| [`prompt steering file kiro.md`](./prompt%20steering%20file%20kiro.md) | Instruksi permanen best-practice software engineering untuk Kiro |
| [`prompt spec driven development.md`](./prompt%20spec%20driven%20development.md) | Spesifikasi lengkap untuk membangun website MBG (Mari Beli Gitar) |

Kamu **tidak perlu menulis ulang prompt dari nol** — cukup ikuti langkah-langkah di bawah ini, copy-paste ke Kiro, dan sesuaikan dengan proyek kamu sendiri.

***

## 🧠 Apa itu Kiro?

**Kiro** adalah agentic IDE buatan AWS yang dirancang untuk *Spec-Driven Development* — pendekatan di mana AI tidak langsung menulis kode, melainkan **merencanakan dulu** sebelum mengeksekusi.

Kiro bekerja dalam tiga tahap:

```
Prompt kamu  →  📋 Spec (requirements + design + tasks)  →  💻 Code
```

Ini berbeda dari vibe coding biasa di mana AI langsung generate kode tanpa struktur. Dengan Kiro, setiap baris kode yang ditulis memiliki dasar dari dokumen spesifikasi yang terstruktur.

**Download Kiro:** [kiro.dev](https://kiro.dev)

***

## ✅ Prasyarat Sebelum Mulai

Pastikan kamu sudah menyiapkan hal berikut sebelum menggunakan prompt di repo ini:

- [ ] **Kiro IDE** sudah terinstall di Windows 11
- [ ] Login dengan akun **Kiro Pro**
- [ ] **Node.js 18+** sudah terinstall → cek dengan `node -v`
- [ ] **Git** sudah terinstall → cek dengan `git --version`
- [ ] **Chrome browser** sudah terbuka (untuk Chrome DevTools MCP)
- [ ] MCP berikut sudah dikonfigurasi di Kiro:
  - `fetch`
  - `modelcontextprotocol/server-memory`
  - `chrome-devtools`
  - `aws-knowledge`
  - `memory`
  - `sequential-thinking`
  - `git`

> 💡 **Belum tahu cara setup MCP?** Tonton bagian "Tour MCP Setup" di video tutorial untuk panduan visual lengkapnya.

***

## 🚀 Cara Menggunakan Prompt di Repo Ini

### Langkah 1 — Setup Steering File (Lakukan PERTAMA)

Steering file adalah instruksi permanen yang selalu dibaca Kiro setiap kali dia menulis kode. Anggap ini sebagai "aturan kerja" untuk Kiro di project kamu.

1. Buka **Kiro IDE** dan buka folder project baru yang kosong
2. Buka file [`prompt steering file kiro.md`](./prompt%20steering%20file%20kiro.md)
3. **Copy seluruh isinya**
4. Paste ke **Kiro Chat** dan tekan Enter
5. Kiro akan generate file `.kiro/steering/engineering-best-practices.md` secara otomatis

✅ Setelah ini, Kiro akan selalu:
- Commit ke Git setiap selesai satu task
- Menulis test case yang lean dan efisien
- Melakukan security review di akhir sesi
- Menjaga README tetap up-to-date

***

### Langkah 2 — Buat Spec untuk Project Kamu

Spec adalah inti dari Kiro. Di sinilah kamu mendeskripsikan **apa yang ingin dibangun**, lalu Kiro akan generate tiga dokumen: `requirements.md`, `design.md`, dan `tasks.md`.

**Untuk project MBG (dari tutorial video):**

1. Buka file [`prompt spec driven development.md`](./prompt%20spec%20driven%20development.md)
2. **Copy seluruh isinya**
3. Di Kiro, buka panel **Spec** (dari sidebar atau Command Palette)
4. Paste prompt dan Submit
5. Tunggu Kiro generate tiga dokumen spesifikasi

**Untuk project kamu sendiri:**

Kamu bisa memodifikasi prompt spec dengan mengganti bagian-bagian berikut:

```
- Nama aplikasi  →  Ganti "MBG (Mari Beli Gitar)" dengan nama project kamu
- Fitur produk   →  Sesuaikan dengan kebutuhan bisnis kamu
- Tech stack     →  Bisa diganti sesuai preferensi (tapi Next.js + Prisma direkomendasikan)
- Nomor WhatsApp →  Ganti "6281234567890" dengan nomor CS kamu
- Link toko      →  Ganti URL Tokopedia dan Shopee dengan link toko kamu
```

***

### Langkah 3 — Review Dokumen Spec

Sebelum mengeksekusi tasks, luangkan waktu untuk review dokumen yang di-generate Kiro:

```
.kiro/
├── steering/
│   └── engineering-best-practices.md   ← Aturan coding permanen
└── specs/
    └── [nama-project]/
        ├── requirements.md              ← User stories (format EARS notation)
        ├── design.md                    ← Arsitektur teknis & API routes
        └── tasks.md                     ← Task list yang siap dieksekusi
```

> 💡 **Tips:** Kalau ada requirement yang kurang tepat atau perlu ditambah, edit langsung di `requirements.md` sebelum melanjutkan ke step berikutnya.

***

### Langkah 4 — Eksekusi Tasks

1. Buka `tasks.md`
2. Klik **Execute** di task pertama untuk lihat prosesnya
3. Setelah yakin semuanya berjalan dengan benar, klik **Execute All** untuk tasks sisanya
4. Kiro akan menulis kode, menjalankan terminal commands, dan melakukan git commit secara otomatis

***

### Langkah 5 — Screenshot dengan Chrome DevTools MCP

Setelah website berjalan di `localhost:3000`, kamu bisa meminta Kiro untuk **melihat tampilan visual website kamu** menggunakan Chrome DevTools MCP:

```
Using the Chrome DevTools MCP, take a screenshot of the currently running 
website at localhost:3000 and review the visual result. Check if:
1. The product cards look good and consistent
2. The WhatsApp floating widget is visible at bottom right
3. The overall layout feels professional for an Indonesian online store
Then suggest 2-3 specific UI improvements based on what you see.
```

> 🔥 **Fitur ini powerful banget** — Kiro tidak hanya membaca kode CSS kamu, tapi benar-benar "melihat" tampilan website dan memberikan feedback berdasarkan visual yang nyata.

***

### Langkah 6 — Security Review di Akhir Sesi

Sesuai steering file, jalankan security review sebelum selesai:

```
Perform a security review of the entire codebase. Check for:
1. Any hardcoded secrets or credentials
2. Unprotected API routes that should require authentication
3. Missing input validation or sanitization
4. SQL injection vulnerabilities in Prisma queries
5. Missing .env in .gitignore

List all findings with severity level, then fix the critical ones immediately.
```

***

## 📁 Struktur File di Repo Ini

```
kiro-IDE-tutorial-spec-driven-development/
│
├── README.md                              ← Kamu sedang membaca ini
├── prompt steering file kiro.md           ← Prompt untuk setup steering rules
└── prompt spec driven development.md      ← Prompt spec untuk MBG Guitar Store
```

***

## 🛠️ Tentang MCP yang Digunakan di Tutorial

MCP (Model Context Protocol) adalah cara Kiro "tersambung" ke tools eksternal. Berikut ringkasan MCP yang dipakai di tutorial ini:

| MCP | Fungsi |
|-----|--------|
| `fetch` | Browsing URL langsung — Kiro bisa lihat halaman Tokopedia/Shopee sebagai referensi UI |
| `server-memory` | Menyimpan ingatan antar sesi — Kiro ingat keputusan teknis dari sesi sebelumnya |
| `chrome-devtools` | Koneksi ke Chrome — Kiro bisa screenshot website, baca console error, dan inspect elemen |
| `aws-knowledge` | Akses knowledge base AWS — berguna saat deploy ke AWS Amplify atau App Runner |
| `memory` | Context recall dalam satu sesi berjalan |
| `sequential-thinking` | Reasoning step-by-step sebelum menulis solusi kompleks |
| `git` | Baca git history, lihat diff, dan buat commit langsung dari chat |

***

## 💡 Tips & Catatan Tambahan

### ⚠️ Soal Kiro Plans & Token Limit
- Prompt spec yang panjang dan eksekusi semua tasks sekaligus mengonsumsi token yang signifikan
- **Disarankan:** Rekam vibe coding session dalam **satu take** untuk menghemat usage limit
- Steering file hanya perlu dibuat **sekali per project** — tidak mengonsumsi token berulang

### 🔧 Kalau Kiro Salah Interpretasi
Jika Kiro menghasilkan sesuatu yang tidak sesuai ekspektasi:
1. Jangan langsung re-run — tambahkan klarifikasi di chat
2. Edit `requirements.md` secara manual untuk memperjelas requirement
3. Minta Kiro regenerate hanya task yang bermasalah

### 📝 Customizing untuk Project Lain
Steering prompt di repo ini bersifat **general** dan bisa dipakai untuk project Next.js apapun, tidak hanya MBG. Kamu hanya perlu mengganti prompt spec-nya sesuai kebutuhan project kamu.

### 🔐 Credentials Default Admin
Prompt spec tidak menentukan username/password admin secara spesifik — Kiro biasanya akan set default credentials dan mendokumentasikannya di README project. Cek file `.env` atau `README.md` yang di-generate Kiro setelah eksekusi selesai.

### 🌐 Deploy ke Production
Di tutorial lanjutan, kita akan deploy website ini menggunakan:
- **AWS Amplify** (recommended untuk Next.js)
- **`aws-knowledge` MCP** yang sudah dikonfigurasi akan sangat membantu di tahap ini

***

## 🎬 Tutorial Video Lengkap

Semua langkah di atas didemonstrasikan secara visual di channel YouTube:

**👉 [Central Data Technology](https://www.youtube.com/@centraldatatechnology155/videos)**

Subscribe untuk update tutorial berikutnya tentang:
- Deploy MBG ke AWS menggunakan Amplify
- Advanced Kiro features (Agent Hooks)
- Optimasi performa website Next.js

***

## 📬 Pertanyaan & Feedback

Kalau ada pertanyaan tentang prompt atau tutorial, silakan buka **Issue** di repository ini. Pull Request untuk perbaikan juga sangat disambut! 🙌

***

*Dibuat dengan ❤️ sebagai companion resource untuk tutorial Kiro IDE di Central Data Technology*
