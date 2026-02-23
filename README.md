# 📋 Apprenticeship Report Generator (Berichtsheft Generator)

A free, offline-first web app for managing **Ausbildungsnachweise** (training reports) required during vocational training (*Ausbildung*) in Germany. Built as a single HTML file — no installation, no server, no account needed.

---

## What is an Ausbildung?

In Germany, vocational training (*Berufsausbildung*) is a dual system where apprentices (*Auszubildende*) split their time between a company and a vocational school (*Berufsschule*). The training typically lasts 2–3.5 years and leads to a nationally recognized qualification.

As part of the training, every apprentice is **legally required** to keep a training journal called a **Berichtsheft** (also known as *Ausbildungsnachweis*). This is mandated by **§ 43 of the Berufsbildungsgesetz (BBiG)** — the German Vocational Training Act. Without a completed Berichtsheft, apprentices are generally **not admitted to the final exam** (*Abschlussprüfung*).

Each weekly report must document:
- What the apprentice worked on that week
- How many hours were worked
- How many days were spent at the company, in home office, at school, or were missed due to illness or vacation

The completed reports must be **signed by both the apprentice and the trainer (Ausbilder)** and submitted to the examining board (*Prüfungsausschuss*).

---

## Features

- **Master data** — store your name, date of birth, trainer's name, company, training occupation, start/end dates, and weekly target hours
- **Weekly reports** — create one entry per calendar week with description, hours, and daily breakdown (office / home office / school / sick / vacation)
- **Smart date sync** — enter a calendar week and the date range fills in automatically (Monday–Friday), or pick a date and the week number is calculated for you
- **Offline storage** — all data is saved locally in your browser using **IndexedDB** — nothing leaves your device, works without internet
- **PDF export** — generates a properly formatted A4 PDF with signature fields and the official § 43 BBiG confirmation text, ready to print and sign
- **JSON export / import** — back up all your data as a JSON file and restore it later; import prompts for confirmation before overwriting existing data
- **Search** — quickly find reports by keyword, calendar week, or year
- **Dashboard** — overview of your reports with key stats (total reports, days at company, home office, school)

---

## How to Use

### Option 1 — Open directly in the browser

Download `index.html` and open it in any modern browser (Chrome, Firefox, Edge, Safari). Everything runs locally.

### Option 2 — Host on GitHub Pages

1. Fork or create a repository
2. Rename the file to `index.html` and push it to the `main` branch
3. Go to **Settings → Pages** and enable GitHub Pages from the `main` branch
4. Your app is now accessible at `https://yourusername.github.io/your-repo/`

> Data is stored in the browser's IndexedDB on the device you use — it does not sync across devices. Use the export/import feature to transfer data between devices.

---

## Workflow

```
1. Go to "Stammdaten" → fill in your personal and training details → Save
2. Go to "Berichte" → click "Neuer Bericht" → fill in the weekly report → Save
3. Repeat every week throughout your Ausbildung
4. Before your exam → go to "Drucken" → download PDF → print → sign with your Ausbilder
```

---

## PDF Output

Each report is exported as a separate A4 page containing:

| Field | Content |
|---|---|
| Apprentice name | From master data |
| Date of birth | From master data |
| Company | From master data |
| Trainer (Ausbilder) | From master data |
| Occupation | From master data |
| Training period | From master data |
| Calendar week | From weekly report |
| Report date range | From weekly report |
| Activity description | From weekly report |
| Attendance table | Office / Home office / School / Sick / Vacation days + total hours |
| § 43 BBiG confirmation | Fixed legal text |
| Signature fields | Apprentice + Ausbilder |

---

## Data & Privacy

- **No data leaves your device.** Everything is stored locally in your browser's IndexedDB.
- **No cookies, no tracking, no analytics.**
- Clearing your browser data will erase the stored reports — use the **Export** function regularly as a backup.

---

## Tech Stack

| | |
|---|---|
| Storage | Browser IndexedDB (offline) |
| PDF generation | [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) (loaded from CDN on demand) |
| Fonts | Google Fonts — Inter |
| Framework | Vanilla HTML / CSS / JavaScript — zero dependencies |
| Hosting | Any static file host (GitHub Pages, Netlify, local file system) |

---

## Legal Note

The § 43 BBiG confirmation text included in the PDF is a standard declaration used across many training companies in Germany. Always verify the exact wording required by your **Prüfungsausschuss** (examining board) or **IHK/HWK** before submission, as requirements may vary by chamber and profession.

---

## License

MIT — free to use, modify, and distribute.
