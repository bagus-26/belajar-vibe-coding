# Project API Setup (ElysiaJS + Drizzle + MySQL)

Dokumen ini berisi panduan tingkat tinggi (high-level) untuk melakukan setup project aplikasi backend menggunakan Bun.

## 1. Persiapan Project
- Lakukan inisialisasi project menggunakan Bun di direktori ini (`bun init -y` atau serupa).
- Install package utama yang dibutuhkan:
  - `elysia` (Framework)
  - `drizzle-orm` (ORM)
  - `mysql2` (MySQL Driver)
- Install package development (dev-dependencies):
  - `drizzle-kit` (Migration Tool)
  - Ekstensi tipe (jika diperlukan)

## 2. Pengaturan Database
- Buat file `.env` dan tambahkan koneksi ke database MySQL lokal atau remote (misalnya `DATABASE_URL`).
- Buat file konfigurasi koneksi database menggunakan Drizzle (misalnya `src/db/index.ts`).

## 3. Pembuatan Skema Database (Schema)
- Tentukan tabel utama yang akan digunakan (misalnya tabel `users` atau `items`).
- Tulis definisi skema di file terpisah (misalnya `src/db/schema.ts`).
- Gunakan `drizzle-kit` untuk melakukan generate dan push struktur tabel ke database MySQL.

## 4. Pembuatan Endpoint / Routing
- Buat file utama aplikasi (misalnya `src/index.ts`).
- Inisialisasi `Elysia` app.
- Buat endpoint dasar (misalnya GET `/` dan beberapa contoh endpoint API CRUD).
- Sambungkan endpoint tersebut ke database lewat Drizzle (misalnya mengambil data dari tabel yang baru saja dibuat).

## 5. Menjalankan Aplikasi
- Tambahkan script di `package.json` untuk menjalankan server mode development (`bun --watch run src/index.ts`).
- Pastikan tidak ada error saat server dijalankan dan endpoint bisa diakses dengan baik.
