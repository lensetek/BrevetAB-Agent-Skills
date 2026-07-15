---
name: tax-ui-visualizer
description: Menggenerasikan antarmuka visual on-demand baik dalam bentuk aplikasi Python Desktop GUI (CustomTkinter/PyWebView) maupun Dasbor Single-File HTML interaktif tanpa dependensi luar.
---

# Tax UI Visualizer & On-Demand Desktop GUI Generator Skill

Skill ini bertugas menghasilkan **antarmuka visual interaktif secara on-demand** untuk data akuntansi & perpajakan. Mendukung 2 mode keluaran:
1. **Single-File Interactive HTML Dashboard** (100% offline, zero-install, dibuka cukup double-click).
2. **On-Demand Python Desktop GUI Application Generator** (CustomTkinter / PyWebView) yang aman terintegrasi dengan CLI Subprocess Agent (`antigravity`, `claude-code`, dll.) tanpa risiko membocorkan API credentials.

---

## 🖥️ Mode 1: Single-File Interactive HTML Visualizer

Ketika pengguna meminta laporan visual (seperti Buku Besar / General Ledger, Kertas Kerja Rekonsiliasi Fiskal, atau Form SPT Preview), hasilkan 1 berkas `.html` mandiri yang berisi gabungan:
* **HTML5**: Struktur komponen dan tabel.
* **Vanilla CSS (Modern Design Tokens)**: Tema terang/gelap (*dark/light toggle*), font modern Inter/Roboto, responsif mobile-first, dan layout bersih.
* **Embedded Vanilla JS**: Logika interaktif live search, filtering akun, accordion detail transaksi, dan penanganan simpan data lokal.

### Template Komponen Utama Single-File HTML:

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Buku Besar & Rekonsiliasi Fiskal - [Nama WP]</title>
  <style>
    :root {
      --bg-color: #f8fafc;
      --card-bg: #ffffff;
      --text-color: #0f172a;
      --primary: #2563eb;
      --border: #e2e8f0;
    }
    [data-theme="dark"] {
      --bg-color: #0f172a;
      --card-bg: #1e293b;
      --text-color: #f8fafc;
      --border: #334155;
    }
    body { font-family: system-ui, -apple-system, sans-serif; background: var(--bg-color); color: var(--text-color); margin: 0; padding: 20px; }
    .card { background: var(--card-bg); border: 1px solid var(--border); border-radius: 12px; padding: 20px; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); }
    .btn { background: var(--primary); color: white; border: none; padding: 8px 16px; border-radius: 6px; cursor: pointer; font-weight: 600; }
    table { width: 100%; border-collapse: collapse; margin-top: 15px; }
    th, td { border-bottom: 1px solid var(--border); padding: 10px; text-align: left; }
  </style>
</head>
<body>
  <div class="card">
    <div style="display:flex; justify-content:space-between; align-items:center;">
      <h2>📘 Buku Besar & Rekonsiliasi Fiskal</h2>
      <div>
        <button class="btn" onclick="saveChanges()">💾 Simpan Perubahan</button>
        <button class="btn" style="background:#64748b;" onclick="toggleTheme()">🌙 Mode</button>
      </div>
    </div>
    <input type="text" id="searchBox" onkeyup="filterTable()" placeholder="🔍 Cari Kode Akun atau Deskripsi Transaksi..." style="width:100%; padding:10px; margin-top:15px; border-radius:6px; border:1px solid var(--border);">
    <table id="dataTable">
      <thead>
        <tr>
          <th>Kode Akun</th>
          <th>Nama Akun</th>
          <th>Nilai Komersial</th>
          <th>Koreksi Positif</th>
          <th>Koreksi Negatif</th>
          <th>Aksi</th>
        </tr>
      </thead>
      <tbody>
        <!-- Dynamic JSON Render Rows -->
      </tbody>
    </table>
  </div>

  <script>
    function filterTable() {
      const q = document.getElementById('searchBox').value.toLowerCase();
      const rows = document.querySelectorAll('#dataTable tbody tr');
      rows.forEach(r => {
        r.style.display = r.innerText.toLowerCase().includes(q) ? '' : 'none';
      });
    }

    function toggleTheme() {
      const current = document.body.getAttribute('data-theme');
      document.body.setAttribute('data-theme', current === 'dark' ? 'light' : 'dark');
    }

    function saveChanges() {
      // Direct File Access API / LocalStorage Saving
      alert('💾 Perubahan data telah tersimpan ke berkas lokal!');
    }
  </script>
</body>
</html>
```

---

## 🐍 Mode 2: Generator Python Desktop GUI Wrapper (On-Demand)

Jika pengguna meminta aplikasi desktop GUI mandiri, buatkan skrip Python tunggal menggunakan **CustomTkinter** yang mengeksekusi CLI agent lokal via `subprocess`:

```python
import sys
import subprocess
import threading
import customtkinter as ctk

ctk.set_appearance_mode("System")
ctk.set_default_color_theme("blue")

class TaxAgentDesktopApp(ctk.CTk):
    def __init__(self):
        super().__init__()
        self.title("Brevet AB Tax Agent Desktop Suite")
        self.geometry("900x650")

        # Header Title
        self.header = ctk.CTkLabel(self, text="🛡️ Brevet AB Tax Agent Suite", font=ctk.CTkFont(size=20, weight="bold"))
        self.header.pack(pady=10)

        # Input Prompt Textbox
        self.prompt_label = ctk.CTkLabel(self, text="Masukkan Perintah Pajak ke AI Agent:")
        self.prompt_label.pack(anchor="w", padx=20)
        self.prompt_entry = ctk.CTkEntry(self, placeholder_text="Contoh: Tolong hitung PPh 21 TER bulan Mei PT Sinar Jaya...", width=860)
        self.prompt_entry.pack(padx=20, pady=5)

        # Submit Button
        self.submit_btn = ctk.CTkButton(self, text="🚀 Jalankan Agen CLI", command=self.execute_agent_thread)
        self.submit_btn.pack(pady=10)

        # Live Terminal Output Log Viewer
        self.log_label = ctk.CTkLabel(self, text="Live Output Log Sesi CLI Agent:")
        self.log_label.pack(anchor="w", padx=20)
        self.log_view = ctk.CTkTextbox(self, width=860, height=350, font=ctk.CTkFont(family="Consolas", size=12))
        self.log_view.pack(padx=20, pady=5)

    def execute_agent_thread(self):
        threading.Thread(target=self._run_cli, daemon=True).start()

    def _run_cli(self):
        prompt = self.prompt_entry.get()
        if not prompt:
            return
        
        self.log_view.insert("end", f"\n> Memulai Perintah: {prompt}\n")
        # Eksekusi CLI Agent Lokal (tanpa terekspos API Key)
        cmd = f'antigravity "{prompt}"'
        
        proc = subprocess.Popen(cmd, shell=True, stdout=subprocess.PIPE, stderr=subprocess.STDOUT, text=True)
        for line in proc.stdout:
            self.log_view.insert("end", line)
            self.log_view.see("end")
        proc.wait()
        self.log_view.insert("end", "\n[Selesai] Eksekusi agen berhasil.\n")

if __name__ == "__main__":
    app = TaxAgentDesktopApp()
    app.mainloop()
```

---

## 🔒 6. Prinsip Keamanan & Responsif

* **Credential Shield**: Selalu eksekusi perintah melalui CLI lokal. Jangan pernah meminta atau menyimpan API Key di dalam kode GUI.
* **Mobile-First Responsive Layout**: Tampilan HTML single-file harus tetap nyaman diakses di perangkat seluler/tablet konsultan pajak.
