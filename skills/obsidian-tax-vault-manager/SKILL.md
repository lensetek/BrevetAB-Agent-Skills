---
name: obsidian-tax-vault-manager
description: Memanajemeni basis pengetahuan perpajakan, profil Wajib Pajak (YAML schema), kertas kerja fiskal, dan sitasi hukum bi-directional linking di dalam Obsidian Vault lokal.
---

# Obsidian Tax Vault Manager Skill

Skill ini bertindak sebagai pengelola basis pengetahuan perpajakan (*Tax Personal Knowledge Management / PKM*) di dalam **Obsidian Vault** lokal pengguna. Mengatur struktur berkas Markdown, skema YAML frontmatter untuk Wajib Pajak, sitasi hukum perpajakan, dan *query* dashboard berformat Dataview.

---

## 🗂️ 1. Struktur Folder Standar Vault

Saat diinisialisasi, skill ini memastikan struktur folder dalam Vault tertata rapi sebagai berikut:

```text
Tax-Vault/
├── 01-Klien/              # Catatan profil Wajib Pajak (Orang Pribadi & Badan)
├── 02-Peraturan/          # Basis pengetahuan UU, PMK, PER DJP dengan bi-directional links
├── 03-Kertas-Kerja/       # Laporan rekonsiliasi fiskal & ekualisasi PPN
├── 04-SP2DK-Dispute/      # Tanggapan surat imbauan & berkas keberatan KPP
└── 05-Dashboards/         # Catatan pemantauan berbasis Obsidian Dataview
```

---

## 📝 2. Skema Templat Catatan Klien (YAML Frontmatter)

Setiap catatan Wajib Pajak di bawah folder `01-Klien/` (contoh: `01-Klien/PT_Sinar_Jaya.md`) harus memiliki struktur frontmatter terstandardisasi:

```markdown
---
nama_wp: "PT Sinar Jaya"
npwp: "01.234.567.8-012.000"
nik_nitku: "0123456789012345"
klu: "46591 - Perdagangan Besar Mesin"
status_pkp: true
tanggal_pkp: "2021-04-15"
metode_pembukuan: "Stelsel Akrual"
toleransi_risiko_pajak: "Konservatif"
terakhir_diperbarui: 2026-07-15
tags:
  - klien/badan
  - pkp
---

# PT Sinar Jaya - Profil Wajib Pajak

## 📌 Ringkasan Eksekutif
- **AR Penanggung Jawab**: KPP Pratama Semarang Selatan
- **Email Kontak**: finance@sinarjaya.co.id

## 📑 Riwayat Pelaporan SPT
- [[Kertas-Kerja/2025/Rekonsiliasi_Fiskal_2025_PT_Sinar_Jaya|SPT Tahunan PPh Badan 2025]] - *Status: NIHIL / Sudah Lapor*

## 🏛️ Riwayat SP2DK & Pengawasan DJP
- [[SP2DK-Dispute/2026/SP2DK_Ekualisasi_Omset_2024|Tanggapan SP2DK Ekualisasi Omset 2024]] - *Selesai*
```

---

## 🔗 3. Sintaks Bi-Directional Linking Peraturan Pajak

Skill ini memastikan seluruh dokumen hukum perpajakan terhubung menggunakan sintaks wikilink Obsidian `[[Nama_Dokumen]]` agar dapat divisualisasikan dalam *Graph View*:

* **Format Link Regulasi**: `[[Peraturan/PMK-66-2023|PMK 66/2023 (Natura)]]`
* **Format Link Undang-Undang**: `[[Peraturan/UU-7-2021-HPP|UU HPP Cluster PPh]]`
* **Contoh Sitasi dalam Catatan Disput/Kertas Kerja**:
  > *"Sesuai dengan ketentuan pasal 4 ayat (3) [[Peraturan/UU-7-2021-HPP|UU HPP]], kenikmatan fasilitas komputer kerja dikategorikan sebagai bukan objek PPh berdasarkan [[Peraturan/PMK-66-2023|PMK 66/2023]] pasal 3."*

---

## 📊 4. Halaman Dashboard Berbasis Obsidian Dataview

Menyediakan templat catatan di `05-Dashboards/Kepatuhan_Klien.md` yang memanfaatkan plugin **Obsidian Dataview** untuk agregasi otomatis:

```dataview
TABLE 
  npwp AS "NPWP / NITKU", 
  klu AS "KLU Usaha", 
  status_pkp AS "Status PKP", 
  toleransi_risiko_pajak AS "Profil Risiko"
FROM "01-Klien"
SORT nama_wp ASC
```

---

## 🔒 5. Keamanan Data & Kebocoran Credential

* **Strictly Local-First**: Seluruh catatan hanya ditulis dan disimpan dalam Obsidian Vault di komputer lokal.
* **Pembersihan Data Sensitif**: Kata sandi portal CoreTax, sertifikat elektronik passphrase, atau token API tidak boleh ditulis dalam catatan plain-text. Selalu gunakan penanda referensi env lokal.
