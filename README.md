# Automated Email Extraction Tool 🕷️

A web crawler that automatically extracts all email addresses from a website and saves them to a CSV file. Just provide a **sitemap URL** — the tool handles the rest.

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![MIT License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## 📌 What is this?

This mini-project is a **web crawler (email scraper)** that:
1. Takes a **sitemap URL** as input
2. Crawls all page URLs listed in the sitemap
3. Extracts **every email address** found on each page using regex
4. Saves all discovered emails to a **CSV file**

Useful for research, data collection tasks, and learning how web scraping pipelines work.

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `requests` | Fetch HTML content from web pages |
| `BeautifulSoup4` | Parse HTML and extract text |
| `re` | Regex pattern matching for email addresses |
| `csv` | Write extracted emails to CSV output |

---

## 🗂️ Project Structure

```
Automated-Email-Extraction-Tool/
├── Web_Crawling(Email_Scraper).ipynb   ← Main crawler notebook
└── README.md
```

---

## ⚙️ How it Works

```
Input: Sitemap URL
      │
      ▼
requests.get(sitemap_url)
      │
      ▼
BeautifulSoup → Extract all <loc> URLs from sitemap XML
      │
      ▼
For each URL:
  → requests.get(url) → fetch page HTML
  → BeautifulSoup → extract visible text
  → re.findall(email_pattern) → extract emails
      │
      ▼
Deduplicate + Write to emails.csv
```

---

## 🚀 Setup & Running

### Option A — Google Colab *(zero setup)*
1. Upload `Web_Crawling(Email_Scraper).ipynb` to [Google Colab](https://colab.research.google.com/)
2. Run all cells (`Runtime → Run all`)

### Option B — Local Jupyter

**Step 1 — Clone the repo**
```bash
git clone https://github.com/SnehaTanwar006/Automated-Email-Extraction-Tool.git
cd Automated-Email-Extraction-Tool
```

**Step 2 — Install dependencies**
```bash
pip install requests beautifulsoup4
```

**Step 3 — Launch Jupyter**
```bash
jupyter notebook "Web_Crawling(Email_Scraper).ipynb"
```

**Step 4 — Set your target URL**
In the notebook, replace the `sitemap_url` variable:
```python
sitemap_url = "https://example.com/sitemap.xml"
```

**Step 5 — Run all cells**
`Kernel → Restart & Run All` — your output will be saved to `emails.csv`.

---

## 📤 Sample Output (`emails.csv`)

```csv
Email
contact@example.com
info@example.com
support@company.org
press@startup.io
```

---

## ⚠️ Ethical Use Disclaimer

This tool is intended for **legitimate and lawful use only**, including:
- Academic research and learning about web scraping
- Scraping your **own website** for auditing purposes
- Understanding crawler architecture

**Do NOT use this tool to:**
- Send unsolicited emails or spam
- Violate any website’s Terms of Service
- Harvest emails for malicious or commercial purposes without consent

Always respect `robots.txt` and applicable laws (GDPR, CAN-SPAM, etc.).

---

## 📦 Dependencies

```
requests
beautifulsoup4
```

---

## 📄 License
MIT — see [LICENSE](LICENSE) if present.

---

<p align="center">Made with ❤️ by <a href="https://github.com/SnehaTanwar006">Sneha Tanwar</a></p>
