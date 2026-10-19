# Monitoring Dapur MBG 🍽️

Platform web untuk sistem pemantauan (monitoring) operasional dapur program **Makan Bergizi Gratis (MBG)**, dibangun menggunakan **SvelteKit 5**, **Tailwind CSS v4**, dan **Bun**.

---

## 🚀 Tech Stack

- **Framework**: [SvelteKit](https://kit.svelte.dev/) (Svelte 5 dengan mode Runes)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/)
- **Bahasa**: [TypeScript](https://www.typescriptlang.org/)
- **Bundler & Build Tool**: [Vite](https://vite.dev/)
- **Package Manager & Runtime**: [Bun](https://bun.sh/)
- **Linter & Formatter**: ESLint, Prettier, `svelte-check`
- **CI/CD & Deployment**: Docker & Jenkins Pipeline

---

## 📋 Prasyarat

Pastikan Anda telah menginstal:

- [Bun](https://bun.sh/) (disarankan v1.2+ / v1.4) atau [Node.js](https://nodejs.org/) (v20+)
- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/) _(opsional, untuk deployment kontainer)_

---

## 🛠️ Panduan Memulai

### 1. Clone Repositori

```bash
git clone git@github.com:ahlaiptek/monitoring-dapur-mbg.git
cd monitoring-dapur-mbg
```

### 2. Instal Dependensi

Menggunakan Bun:

```bash
bun install
```

_(Atau menggunakan npm/pnpm/yarn jika diperlukan)_:

```bash
npm install
```

### 3. Menjalankan Server Pengembangan (Dev)

```bash
bun run dev
```

Buka peramban di [http://localhost:5173](http://localhost:5173). Untuk membuka langsung di browser secara otomatis:

```bash
bun run dev -- --open
```

---

## 📜 Perintah yang Tersedia (NPM/Bun Scripts)

| Perintah              | Deskripsi                                                             |
| :-------------------- | :-------------------------------------------------------------------- |
| `bun run dev`         | Menjalankan server pengembangan lokal (Vite Dev Server)               |
| `bun run build`       | Melakukan build aplikasi untuk lingkungan produksi                    |
| `bun run preview`     | Menjalankan preview lokal dari hasil build produksi                   |
| `bun run check`       | Memeriksa tipe data TypeScript dan diagnostik Svelte (`svelte-check`) |
| `bun run check:watch` | Menjalankan pemeriksaan tipe data secara live/watch mode              |
| `bun run lint`        | Menjalankan pengecekan format kode (Prettier) dan linting (ESLint)    |
| `bun run format`      | Memperbaiki dan memformat kode secara otomatis dengan Prettier        |

---

## 📁 Struktur Direktori

```text
monitoring-dapur-mbg/
├── .docker/             # Konfigurasi Docker (CI/CD)
│   └── ci/
│       └── Dockerfile
├── src/                 # Kode sumber aplikasi
│   ├── lib/             # Komponen bersama, utility, dan aset
│   ├── routes/          # Rute dan halaman SvelteKit
│   ├── app.d.ts         # Deklarasi tipe TypeScript global SvelteKit
│   └── app.html         # Template HTML utama
├── static/              # Aset statis yang disajikan langsung
├── Jenkinsfile          # Pipeline otomatisasi CI/CD Jenkins
├── vite.config.ts       # Konfigurasi Vite & Tailwind CSS
├── tsconfig.json        # Konfigurasi TypeScript
├── eslint.config.js     # Konfigurasi ESLint
├── prettier.config.js   # Konfigurasi Prettier
└── package.json         # Dependensi dan skrip proyek
```

---

## 🐳 Docker & Deployment

### Build & Jalankan secara Lokal dengan Docker

```bash
# Build Docker Image
docker build -f .docker/ci/Dockerfile -t monitoring-dapur-mbg:latest .

# Jalankan Kontainer (Port 8001 -> Port 80)
docker run -d -p 8001:80 --name monitoring-dapur-mbg monitoring-dapur-mbg:latest
```

### CI/CD Pipeline (Jenkins)

Proyek ini telah dikonfigurasi dengan `Jenkinsfile` yang menggunakan pipeline shared library `svelteVPSDeploy`:

- **Nama Aplikasi**: `monitoring-dapur-mbg`
- **Target Port**: `8001`

---

## 🤝 Kontribusi

1. Fork repositori ini
2. Buat branch fitur baru (`git checkout -b feature/FiturKeren`)
3. Commit perubahan Anda (`git commit -m 'feat: tambah fitur keren'`)
4. Pastikan lolos linting dan type check (`bun run check && bun run lint`)
5. Push ke branch Anda (`git push origin feature/FiturKeren`)
6. Buat Pull Request

---

## 📄 Lisensi

Hak Cipta © Ahlaiptek. Seluruh hak cipta dilindungi undang-undang.
