# DESIGN SYSTEM — WEBMAIL PEMKAB LAMPUNG BARAT

> **Single Source of Truth** untuk UI/UX Webmail Resmi Pemerintah Kabupaten Lampung Barat.
> Berpedoman pada standar *High-End Agency Design System*, *Stitch Design Taste*, dan *Accessible Government Identity*.

---

## 1. Visual Atmosphere & Filosofi Desain

| Dimensi | Nilai (1–10) | Karakter Visual |
| :--- | :---: | :--- |
| **Density** | **5** (Balanced Civic) | Kerapatan profesional aplikasi kerja ASN; lega untuk keterbacaan, padat untuk produktivitas email harian. |
| **Variance** | **4** (Clean Structural) | Tata letak simetris-terkalibrasi, memancarkan wibawa, stabilitas birokrasi, dan rasa aman bagi pengguna. |
| **Motion** | **3** (Subtle Precision) | Animasi minimalis berbasis pegas fisik (`cubic-bezier(0.32, 0.72, 0, 1)`); tanpa efek heboh yang memperlambat alur kerja. |

* **Prinsip Utama:** *Authoritative, Sovereign, and Frictionless*. Webmail instansi tidak boleh terlihat seperti template murahan ataupun SaaS komersial generik. Identitas daerah Lampung Barat terpancar kuat dari sentuhan warna merah khas lambang daerah yang dikombinasikan dengan neutral tones (Slate/Zinc) berstandar WCAG AAA.

---

## 2. Palet Warna (Color Calibration)

Logo Lampung Barat didominasi oleh warna **Merah Kebanggaan (Crimson Red)**, hitam, dan putih. Sistem warna ini mengadopsi dominasi merah tersebut ke dalam seluruh status interaktif dan identitas visual aplikasi.

### A. Brand & Accent Colors (Dominan Merah)
* **Brand Crimson Primary:** `#C8102E` / `#DC2626` *(Tombol utama, tab aktif, unread indicator, cursor accent)*
* **Brand Crimson Hover/Active:** `#991B1B` / `#B91C1C` *(State hover & pressed tombol utama)*
* **Brand Crimson Muted/Subtle:** `rgba(220, 38, 38, 0.08)` *(Highlight baris email, badge status, selection background)*
* **Brand Crimson Glow / Focus Ring:** `rgba(220, 38, 38, 0.25)` *(Focus outline input keyboard navigation)*

### B. Neutral Palette (Light Mode)
* **Background:** `#F8FAFC` *(Slate-50 — bersih, tidak silau, elegan)*
* **Surface / Card:** `#FFFFFF` *(Pure White dengan hairline border)*
* **Surface Secondary / Sidebar:** `#F1F5F9` *(Slate-100)*
* **Borders & Dividers:** `#E2E8F0` *(Slate-200)*
* **Text High-Contrast:** `#0F172A` *(Slate-900 — keterbacaan optimal)*
* **Text Muted:** `#64748B` *(Slate-500)*

### C. Neutral Palette (Dark Mode)
* **Background:** `#090A0F` *(OLED Deep Charcoal — kontras tinggi dan hemat daya)*
* **Surface / Card:** `#12141A` *(Zinc-900 dengan inset border)*
* **Surface Secondary / Sidebar:** `#0E1015`
* **Borders & Dividers:** `rgba(255, 255, 255, 0.08)`
* **Text High-Contrast:** `#F8FAFC` *(Slate-50)*
* **Text Muted:** `#94A3B8` *(Slate-400)*

### D. Anti-Patterns Warna (STRICTLY BANNED)
- ❌ DILARANG menggunakan gradasi neon ungu/pink ala template AI.
- ❌ DILARANG menggunakan dominasi hijau/emas yang tidak mencerminkan logo Lampung Barat.
- ❌ DILARANG menggunakan hitam pekat `#000000` flat tanpa tekstur/depth.

---

## 3. Typographic Architecture

Menggunakan tipografi modern sans-serif yang tajam, presisi, dan sangat terbaca di berbagai layar HP maupun monitor kerja:

* **Primary Font Stack:** `-apple-system, BlinkMacSystemFont, "Geist", "Plus Jakarta Sans", "Segoe UI", Roboto, sans-serif`
* **Monospace Stack:** `"Geist Mono", "JetBrains Mono", Menlo, monospace` *(Untuk waktu, tanggal, kuota storage, dan security tokens)*
* **Scale & Rhythm:**
  * **H1 / Portal Title:** `text-2xl font-bold tracking-tight text-slate-900 dark:text-white`
  * **H2 / Form Labels:** `text-xs font-semibold uppercase tracking-wider text-slate-500`
  * **Body Text:** `text-sm leading-relaxed text-slate-700 dark:text-slate-300`
  * **Caption / Meta:** `text-xs text-slate-400`

---

## 4. Haptic Component Architecture

### A. Double-Bezel Login Enclosure (Doppelrand)
Kartu login dirancang menyerupai pelat instrumen fisik yang terpasang di atas dashboard:
1. **Outer Shell:** Kotak pembungkus dengan padding halus, batas rambut `ring-1 ring-slate-200/80 dark:ring-white/10`, radius `rounded-2xl`, serta bayangan lembut `shadow-2xl shadow-black/5 dark:shadow-red-950/10`.
2. **Inner Core:** Kontainer isi dengan latar `bg-white dark:bg-[#12141A]`, highlight atas `shadow-[inset_0_1px_1px_rgba(255,255,255,0.8)] dark:shadow-[inset_0_1px_1px_rgba(255,255,255,0.06)]`.

### B. Logo Identity Presentation
* Menggunakan aset resmi: `/branding/lambar.png`
* Dimensi presisi: Rasio aspek terjaga, tinggi ideal `h-20 w-auto`, dengan filter drop-shadow halus (`drop-shadow-sm`).
* Header login memuat nama resmi: **Pemerintah Kabupaten Lampung Barat** dan sub-judul **Layanan Email Kedinasan Terintegrasi**.

### C. Buttons (Primary Action)
* **Warna:** Solid Lampung Barat Crimson (`bg-[#C8102E] text-white hover:bg-[#991B1B]`).
* **Interaksi:** `active:scale-[0.98]` untuk memberikan respon haptik taktil saat diklik.
* **Transisi:** `transition-all duration-200 ease-[cubic-bezier(0.32,0.72,0,1)]`.

### D. Form Inputs
* Border default `#E2E8F0` (light) / `rgba(255,255,255,0.12)` (dark).
* Saat fokus: `focus:border-[#DC2626] focus:ring-4 focus:ring-[#DC2626]/15 outline-none`.

---

## 5. Layout & Aksesibilitas (WCAG AAA)

* **Touch Targets:** Minimal `44px` untuk semua tombol dan input agar mudah ditekan ASN saat membuka email di smartphone.
* **Keyboard Navigation:** Setiap tombol dan tautan memiliki indikator fokus yang jelas dan kontras tinggi.
* **Footer Identitas Daerah:**
  ```text
  © 2026 Dinas Komunikasi dan Informatika Kabupaten Lampung Barat
  Pemerintah Kabupaten Lampung Barat
  ```
