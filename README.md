# Brevet AB Tax Agent Skills

🌐 [English](#english) | [Bahasa Indonesia](#bahasa-indonesia)

---

<a name="english"></a>
## English Version

### About the Project
This repository contains a comprehensive suite of 12 **Professional Tax Agent Skills (Brevet A & B)** designed for advanced AI Coding and Consulting Agents. It automates financial reconciliation, tax calculation, compliance checking, dispute drafting, tax planning, browser-based CoreTax filing, local Obsidian PKM knowledge management, and on-demand interactive UI/Desktop GUI generation.

### 📋 Agent Explanations

1. **[Tax Orchestrator](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-orchestrator/SKILL.md)**: The central manager. Receives user requests, coordinates with specialists, and aggregates the final output.
2. **[Tax Regulation Monitor](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-regulation-monitor/SKILL.md)**: Runs daily checks to scan for new Indonesian tax regulations (DJP/Kemenkeu) to prevent compliance risks.
3. **[Accounting Data Processor](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/accounting-data-processor/SKILL.md)**: Processes ledger files or receipt photos (multimodal OCR) and performs fiscal reconciliation (positive/negative corrections).
4. **[Tax Report Generator](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-report-generator/SKILL.md)**: Computes tax liabilities (Corporate & Individual Income Tax, VAT) and drafts official tax return forms (SPT).
5. **[Agent Update Manager](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/agent-update-manager/SKILL.md)**: Checks for Git repository updates with built-in credential leak checkers and requests user confirmation before pulling updates.
6. **[User Personalization Learner](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/user-personalization-learner/SKILL.md)**: Memorizes client profiles (KLU, PKP status), preferred reporting formats, and tax risk tolerance using active learning (`/learn`).
7. **[Withholding Tax & VAT Analyst](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/withholding-vat-analyst/SKILL.md)**: Identifies tax articles for transactions (PPh 21/22/23/26/4(2)) and performs VAT invoice equalization.
8. **[Tax Dispute & Audit Defender](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-dispute-defender/SKILL.md)**: Drafts formal legal responses to tax office inquiries (SP2DK) and official dispute notifications.
9. **[Tax Planner & Strategist](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-planner-strategist/SKILL.md)**: Models legal tax planning strategies, such as natura benefits vs cash allowances optimization.
10. **[CoreTax Automation Specialist](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/coretax-automation-specialist/SKILL.md)**: Automates SPT form filing and data entry directly onto the DJP CoreTax portal (SIAP) using `chrome-devtools-mcp` via secure hybrid execution.
11. **[Obsidian Tax Vault Manager](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/obsidian-tax-vault-manager/SKILL.md)**: Manages taxpayer client profiles, audit working papers, regulation bi-directional wikilinks (`[[PMK-66-2023]]`), and Dataview dashboards inside a local Obsidian Vault.
12. **[Tax UI Visualizer & GUI Generator](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-ui-visualizer/SKILL.md)**: Generates on-demand interactive Single-File HTML visualizers (General Ledger Explorer, SPT Preview) and compiles customizable Python Desktop GUI wrapper applications connected safely via CLI subprocess.

### 🆕 What's New (v1.2.0)
- **Obsidian Vault & On-Demand Desktop GUI**: Added `obsidian-tax-vault-manager` for local PKM integration and `tax-ui-visualizer` for generating custom desktop GUI wrappers or offline interactive HTML dashboards.
- **CoreTax RPA Integration (v1.1.0)**: Introduced `coretax-automation-specialist` with `chrome-devtools-mcp` for secure browser data entry into CoreTax (SIAP).
- **Initial Release (v1.0.0)**: Launched 9 core agent skills with Multimodal OCR, Safety Gates, and Bilingual docs.

### 🚀 How to Install (Prompt-Based Installation)
You can install these skills onto any capable AI coding assistant (like Antigravity, Claude, or other developer agents) by simply issuing a natural language prompt. 

Copy and paste the prompt below to your AI assistant:
> *"Please download and install the Brevet AB tax agent skills from https://github.com/lensetek/BrevetAB-Agent-Skills by cloning the repository, extracting the skills from the `skills/` folder, and registering the path in my agent config's `skills.json` file."*

#### 🔌 Activating CoreTax Browser Automation
To use the CoreTax direct-filling features, configure the Chrome DevTools MCP server in your agent's MCP configurations. Add the following config to connect to your active Chrome browser (make sure to start Chrome with remote debugging on port `9222`):
```json
{
  "mcpServers": {
    "chrome-devtools": {
      "command": "npx",
      "args": ["-y", "chrome-devtools-mcp@latest", "--browser-url=http://127.0.0.1:9222"]
    }
  }
}
```

---

<a name="bahasa-indonesia"></a>
## Versi Bahasa Indonesia

### Tentang Proyek
Repositori ini berisi rangkaian lengkap dari 12 **Agent Skills Asisten Pajak Profesional (Brevet A & B)** yang dirancang untuk AI Coding & Consulting Agent. Sistem ini mengotomatiskan rekonsiliasi fiskal akuntansi, perhitungan pajak, pemeriksaan regulasi baru, penyusunan draf sengketa, perencanaan pajak, pengisian formulir CoreTax via browser, manajemen pengetahuan di Obsidian Vault, hingga pembentukan Dasbor UI & Aplikasi Desktop GUI secara *on-demand*.

### 📋 Penjelasan Agent

1. **[Tax Orchestrator](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-orchestrator/SKILL.md)**: Manajer pusat. Menerima instruksi pengguna, mengoordinasikan agen spesialis, dan merangkum laporan akhir.
2. **[Tax Regulation Monitor](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-regulation-monitor/SKILL.md)**: Memantau aturan baru dari DJP/Kemenkeu secara harian untuk meminimalkan risiko kepatuhan.
3. **[Accounting Data Processor](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/accounting-data-processor/SKILL.md)**: Memproses data Excel/CSV atau foto kuitansi (multimodal OCR) untuk melakukan rekonsiliasi fiskal (koreksi positif/negatif).
4. **[Tax Report Generator](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-report-generator/SKILL.md)**: Menghitung pajak terutang (PPh & PPN) dan menyusun draf formulir lampiran SPT siap lapor.
5. **[Agent Update Manager](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/agent-update-manager/SKILL.md)**: Memantau pembaruan repositori Git, melakukan sensor kebocoran kredensial, dan meminta izin Anda sebelum memperbarui.
6. **[User Personalization Learner](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/user-personalization-learner/SKILL.md)**: Menghafal profil Wajib Pajak klien (KLU, status PKP), format favorit, toleransi risiko pajak, dan memproses perintah `/learn`.
7. **[Withholding Tax & VAT Analyst](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/withholding-vat-analyst/SKILL.md)**: Menganalisis objek pemotongan/pemungutan PPh (21/22/23/26/4(2)) dan ekualisasi e-Faktur PPN.
8. **[Tax Dispute & Audit Defender](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-dispute-defender/SKILL.md)**: Menyusun tanggapan formal berlandaskan hukum atas surat imbauan SP2DK atau teguran KPP.
9. **[Tax Planner & Strategist](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-planner-strategist/SKILL.md)**: Memberikan simulasi perencanaan pajak legal (seperti skema natura vs tunjangan tunai).
10. **[CoreTax Automation Specialist](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/coretax-automation-specialist/SKILL.md)**: Mengotomatiskan pengisian formulir SPT dan pengiriman data langsung ke portal web CoreTax DJP (SIAP) secara aman menggunakan `chrome-devtools-mcp` (eksekusi hybrid).
11. **[Obsidian Tax Vault Manager](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/obsidian-tax-vault-manager/SKILL.md)**: Mengelola profil klien, kertas kerja, tautan peraturan `[[PMK-66-2023]]`, dan dasbor Dataview di Obsidian Vault lokal.
12. **[Tax UI Visualizer & GUI Generator](file:///c:/Users/ACER/Documents/GitHub/BrevetAB-Agent-Skills/skills/tax-ui-visualizer/SKILL.md)**: Menggenerasikan dasbor HTML interaktif mandiri (Buku Besar, Form SPT) dan aplikasi Python Desktop GUI *on-demand* yang aman terintegrasi via CLI Subprocess.

### 🆕 Yang Baru (v1.2.0)
- **Integrasi Vault Obsidian & Generator Desktop GUI**: Menambahkan `obsidian-tax-vault-manager` untuk manajemen pengetahuan PKM lokal dan `tax-ui-visualizer` untuk membuat dasbor HTML interaktif offline atau aplikasi Desktop GUI secara *on-demand*.
- **Integrasi RPA CoreTax (v1.1.0)**: Menambahkan `coretax-automation-specialist` yang terintegrasi dengan `chrome-devtools-mcp` untuk pengisian data langsung secara aman ke web CoreTax (SIAP).
- **Rilis Pertama (v1.0.0)**: Peluncuran 9 agent skills perpajakan utama dengan OCR Multimoda dan gerbang keamanan kredensial.

### 🚀 Cara Instalasi (Berbasis Prompt)
Anda dapat memasang *skills* ini ke AI coding assistant mana pun (seperti Antigravity, Claude, atau agent developer lainnya) cukup dengan memberikan perintah bahasa sehari-hari.

Salin dan tempel perintah berikut ke obrolan agent Anda:
> *"Tolong unduh dan instal agent skills Brevet AB dari https://github.com/lensetek/BrevetAB-Agent-Skills dengan cara melakukan clone repositori tersebut, mengekstrak data skill dari folder `skills/`, lalu mendaftarkan path-nya ke dalam berkas `skills.json` di konfigurasi agent saya."*

#### 🔌 Mengaktifkan Otomatisasi Browser CoreTax
Untuk menggunakan fitur pengisian langsung ke CoreTax, konfigurasikan server Chrome DevTools MCP di pengaturan MCP agen Anda. Tambahkan baris konfigurasi berikut untuk terhubung ke browser Chrome Anda yang aktif (pastikan Chrome dijalankan dengan *remote debugging* aktif pada port `9222`):
```json
{
  "mcpServers": {
    "chrome-devtools": {
      "command": "npx",
      "args": ["-y", "chrome-devtools-mcp@latest", "--browser-url=http://127.0.0.1:9222"]
    }
  }
}
```
