# Brevet AB Tax Agent Skills

🌐 [English](#english) | [Bahasa Indonesia](#bahasa-indonesia)

---

<a name="english"></a>
## English Version

### About the Project
This repository contains a comprehensive suite of 10 **Professional Tax Agent Skills (Brevet A & B)** designed for advanced AI Coding and Consulting Agents. It automates financial reconciliation, tax calculation, compliance checking, dispute drafting, tax planning, browser-based CoreTax filing, and secure system maintenance.

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

### 🆕 What's New (v1.1.0)
- **CoreTax RPA Integration**: Introduced a new agent skill (`coretax-automation-specialist`) that integrates with `chrome-devtools-mcp` for secure browser-based direct data entry into CoreTax (SIAP).
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
Repositori ini berisi rangkaian lengkap dari 10 **Agent Skills Asisten Pajak Profesional (Brevet A & B)** yang dirancang untuk AI Coding & Consulting Agent. Sistem ini mengotomatiskan rekonsiliasi fiskal akuntansi, perhitungan pajak, pemeriksaan regulasi baru, penyusunan draf sengketa, perencanaan pajak, pengisian formulir CoreTax via browser, dan pemeliharaan sistem yang aman.

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

### 🆕 Yang Baru (v1.1.0)
- **Integrasi RPA CoreTax**: Menambahkan agent skill baru (`coretax-automation-specialist`) yang terintegrasi dengan `chrome-devtools-mcp` untuk pengisian data langsung secara aman ke web CoreTax (SIAP).
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
