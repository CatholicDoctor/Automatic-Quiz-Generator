# Question Bank PDF Generator

A question bank manager for educators. Organize questions by category, difficulty, and unit. Randomly generate quizzes with custom difficulty mixes, add reference images, and export formatted PDF exams — complete with a styled header, answer spaces, and a figures section. Fully offline, runs in any browser.

**Created and maintained by Dr. Angel Hernandez** · dr.angel.e.hernandez@gmail.com  
Distributed under [Creative Commons BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/) — free to use and share, not for sale.

---

## Getting Started

No installation required. Simply open `question-bank.html` in any modern web browser (Chrome, Firefox, Edge, Safari). The app runs entirely offline — no internet connection is needed after the file is downloaded.

> **Note:** Your question bank is saved automatically in your browser's `localStorage`. This means your data persists between sessions on the same browser and device. If you switch browsers or devices, use the Export/Import backup feature to transfer your data.

---

## Features

- Organize questions into **categories** and group categories into **units**
- Tag each question with a **difficulty level** (Easy, Medium, Hard)
- **Randomly generate** quizzes by selecting how many Easy, Medium, and Hard questions to draw from each category
- Attach **reference images** to questions, shown as a numbered Figures section at the end of the PDF
- Export a fully formatted **PDF** in US Letter size with a two-column institutional header, student name/ID fields, instructions, and answer spaces
- **Backup and restore** your question bank as a JSON file

---

## The Three Tabs

### Add Questions

Use this tab to add questions to your bank one at a time or in bulk.

- **Single question:** Select a category (or create a new one), choose a difficulty, optionally add an image URL, and type your question.
- **Bulk import:** Select a category and difficulty, then paste a list of questions — one per line. All imported questions will receive the selected difficulty.

> To create a new category while adding a question, select **"＋ New category…"** from the dropdown. A text field will appear for the category name.

### Question Bank

Browse and manage everything in your bank.

- **Units** are shown at the top. A unit is a group of categories (e.g. a course module or exam block). You can add, rename, and delete units, and assign categories to them.
- **Categories** are listed below. Click a category to expand it and see its questions. While expanded, you can rename the category, change its ID number (used for ordering), reassign its unit, and delete individual questions.
- The **ID number** on each category and unit controls the sort order — lower IDs appear first.
- Use **Export backup** and **Import backup** to save and restore your full question bank as a `.json` file.

### Select & Export

Use this tab to configure and generate a quiz PDF.

**Quiz information** (always visible):
- **Quiz Name** — e.g. *Primer*, *Segundo*
- **Quiz ID / Model** — e.g. *A*, *B* (for parallel exam versions)

Click **Show more options** to reveal:
- University ID, Department ID, Teacher — appear in the PDF header
- Subject, Subject ID — appear in the PDF header
- Trimester and Year — auto-detected from the current date (GMT-4)

**Questions per category:** For each category, set how many Easy (E), Medium (M), and Hard (H) questions to include. A per-category counter and a grand total badge update live as you type.

Click **Generate selection** to randomly draw the specified questions. The preview updates below. Click **Download PDF** to export.

---

## Adding Images to Questions

Questions can have an optional reference image attached. Images are displayed in a **Figures section** at the end of the PDF (up to 3 per row), and the question text automatically includes a note: *"Referirse a la Figura X para responder."*

### Option 1 — Online image URL

Paste any publicly accessible image URL directly into the **Image URL** field when adding a question. Example:

```
https://i.imgur.com/example.jpeg
```

> Images hosted online require an internet connection at the time of PDF generation.

### Option 2 — Base64 (fully offline, recommended)

To embed an image that works completely offline and from a local file, convert it to a Base64 data URL first.

**Recommended tool:** [https://www.base64-image.de/](https://www.base64-image.de/)

Steps:
1. Go to [https://www.base64-image.de/](https://www.base64-image.de/)
2. Upload your image (PNG, JPEG, GIF, WEBP, or SVG)
3. Click **"copy image"** to copy the full Base64 data URL to your clipboard
4. Paste it into the **Image URL** field in the app

The data URL will look something like this:

```
data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA...
```

Base64 images are stored directly inside your question bank and work offline with no external dependencies. SVG images are automatically converted to PNG when generating the PDF.

> **Tip:** Base64 strings can be very long. This is normal — the full image data is embedded in the text.

---

## PDF Format

The exported PDF follows this structure:

| Section | Details |
|---|---|
| **Header** | Two-column: University/Subject/Trimester on the left; Department/Teacher/Quiz name on the right |
| **Student fields** | Nombre (name) and ID lines with proportional underlines (3:1 ratio) |
| **Instructions** | *¡Salve! Lee cuidadosamente el examen...* |
| **Questions** | Numbered, 1.25-spaced, with 2 blank lines per answer |
| **Figures** | At the end, up to 3 per row, max 200px height each |

- **Page size:** US Letter
- **Margins:** 0.5 inch on all sides
- **Font:** Times New Roman (closest standard PDF equivalent to Century Schoolbook)
- **File name format:** `YEAR-TRIMESTER#-QuizName pruebín-ModelID.pdf`  
  *(e.g. `2026-1-Primer pruebín-A.pdf`)*

---

## Backup & Data Portability

Your question bank is stored in `localStorage` in your browser. To back it up or move it to another device:

1. Go to the **Question bank** tab
2. Click **Export backup** — this downloads a `.json` file with all your categories and questions
3. On the target browser/device, click **Import backup** and select the file

> Backups include all question text, difficulty tags, image URLs, category IDs, unit assignments, and unit definitions.

---

## License

This software is distributed under [Creative Commons BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/).  
You are free to share and use this tool for educational purposes.  
You may **not** claim ownership of the idea or charge for its use.
