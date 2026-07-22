---
name: ru-academic-writer
description: Polish and structure-check academic writing for Russian universities — курсовая (coursework), диплом/ВКР (thesis), диссертация, статья, аннотация/abstract, and отзыв на диссертацию responses. Use this skill whenever the user mentions ГОСТ, курсовая, диплом, ВКР, диссертация, аспирантура, a Russian university/institute by name, or asks to check/polish/format an academic paper written for a Russian institution — even if they don't explicitly say "ГОСТ" or "Russia". Covers ГОСТ 7.32-2017 formatting and structure requirements and ГОСТ Р 7.0.5-2008 citation/reference rules. Does NOT rewrite the author's arguments, data, or conclusions — only formatting, structural order, and language fluency (Russian or English).
---

# Ru Academic Writer

A skill for checking and polishing academic papers written for Russian universities against real ГОСТ (Russian state standard) requirements — not generic Western/Chinese academic conventions, which differ from Russian ones in structure, citation, and formatting.

**Core principle: this skill NEVER changes the author's arguments, data, numbers, or conclusions.** It only fixes formatting, structural ordering, citation mechanics, and language fluency. If asked to add new claims, strengthen conclusions, or "make it sound more impressive," politely decline that part and explain the skill's scope.

## When to use this skill

Trigger on any of:
- Mentions of курсовая, диплом, ВКР (выпускная квалификационная работа), диссертация, аспирантура, автореферат
- Mentions of ГОСТ, ГОСТ 7.32, ГОСТ Р 7.0.5
- A named Russian university/institute, or "for my Russian advisor / научный руководитель"
- A request to check/format/polish a paper "for a Russian university" even without the Russian terms above
- Requests to write/polish введение (introduction), заключение (conclusion), аннотация (abstract), or список литературы (reference list) in a Russian academic context

Do not trigger for general English academic writing polish (that's a different task) unless the destination is explicitly a Russian institution.

## Workflow

When the user provides a draft (in Russian, English, or mixed), do the following in order:

### Step 1 — Identify the document type and ask if unclear
Курсовая, диплом/ВКР, диссертация, статья (journal article), and аннотация each have different length/structure expectations (see reference table below). If the user hasn't said which, ask once, briefly — don't assume a диссертация-level structure for a short курсовая.

### Step 2 — Check structural completeness
Compare the draft against the required structure for that document type (below). Flag missing required elements explicitly, in order. Do not silently add sections yourself — tell the user what's missing and ask before inserting placeholder text.

### Step 3 — Check formatting against ГОСТ 7.32-2017
Apply the formatting checklist below. Since most users submit plain text (not a formatted Word doc), the formatting check usually means:
- Confirming they know the numeric requirements before they format in Word (font, spacing, margins)
- If given a .docx, actually checking/fixing these via the docx skill

### Step 4 — Fix citation and reference formatting per ГОСТ Р 7.0.5-2008
Convert whatever citation style the draft currently uses (APA, MLA, numbered brackets, etc.) into ГОСТ Р 7.0.5 style. See citation section below.

### Step 5 — Polish language and logical flow only
- Improve sentence clarity, remove awkward literal translation (very common in drafts translated from Chinese or English into Russian, or vice versa)
- Improve transitions between paragraphs and sections
- Do NOT add new claims, do NOT strengthen hedged statements into strong ones, do NOT remove data or citations the author included
- Preserve the author's own academic voice — don't make it sound like marketing copy or an AI-generated essay (avoid phrases like "in today's rapidly evolving world," "it is important to note that," "paves the way for")

### Step 6 — Summarize what changed
Give the user a short list of what you changed and why, organized under: (1) structure fixes, (2) formatting fixes, (3) citation fixes, (4) language fixes. This lets them sanity-check that their argument wasn't altered.

---

## Reference: ГОСТ 7.32-2017 formatting checklist

| Element | Requirement |
|---|---|
| Font | Times New Roman, size 14pt for main text (12pt is the technical minimum per ГОСТ 7.32, but 14pt is standard practice at most universities) |
| Line spacing | 1.5 (полуторный интервал) |
| Alignment | Justified (по ширине) |
| Paragraph indent | 1.25 cm (красная строка) |
| Margins | Left ≥3 cm, right ≥1–1.5 cm, top ≥2 cm, bottom ≥2 cm |
| Page numbering | Starts from page 2 (title page counts but isn't numbered), centered or right, bottom of page |
| Chapter headings | New page, uppercase, centered, no period at the end |
| Page count | No fixed rule in ГОСТ itself, but курсовая is conventionally 25–35 pages; check the university's own методичка (guidance handbook), which takes precedence over ГОСТ if they conflict |

**Important caveat to tell the user:** many universities layer their own методичка (department style guide) on top of ГОСТ 7.32, and where the two conflict, the методичка wins. Always ask if the user has one and defer to it for anything it specifies.

## Reference: required structure by document type

**Курсовая / Диплом — Введение (Introduction) must contain, in this order:**
1. Актуальность (why the topic matters now)
2. Объект исследования (research object — the broader field/system studied)
3. Предмet исследования (research subject — the specific aspect within the object)
4. Цель (goal) и задачи (tasks/objectives, usually 3–5 numbered items)
5. (Often also expected): методы исследования (methods), структура работы (a one-paragraph roadmap of chapters)

Missing any of items 1–4, or having them out of order, is a common reason работы get sent back before content is even reviewed. Check this first.

**Full paper structure (курсовая/диплом):**
Титульный лист (title page, unnumbered) → Содержание (table of contents) → Введение → Основная часть (2–3 chapters, theoretical + practical/analytical) → Заключение (conclusion — must answer each задача from the introduction) → Список литературы → Приложения (appendices, if any)

**Диссертация/автореферат** follows a similar but more extensive structure with additional required sections (научная новизна — scientific novelty, положения, выносимые на защиту — statements for defense, апробация результатов — how results were presented/published). Ask the user if they need this level of detail before assuming it.

## Reference: ГОСТ Р 7.0.5-2008 citation rules

Russian academic citation is NOT APA/MLA/Chicago. Key differences to apply:

- **In-text citation**: numbered bracket referring to position in the reference list, optionally with page: `[5]` or `[5, с. 81]` (с. = страница/page). This is a затекстовая ссылка (reference placed after the text, i.e., in a numbered bibliography) — the most common format for курсовая/диплом.
- **Reference list ordering**: typically alphabetical by author surname (Cyrillic sources first, then Latin-alphabet sources, each block alphabetized separately) — unless the department requires order of first appearance in text instead. Ask if unsure.
- **Monograph format**: `Фамилия И.О. Название: тип издания. Город: Издательство, Год. Количество страниц.`
  Example: `Пакшина С.М. Передвижение солей в почве: монография. М.: Наука, 1980. 120 с.`
- **Multi-author format**: `Фамилия1 И.О., Фамилия2 И.О. Название...`
- **Journal article format**: includes journal name, year, volume/issue, and page range, using abbreviations like `Т.` (том/volume), `Вып.` (выпуск/issue), `С.` (страницы/pages).
- **DOI**: written without a trailing period after it.
- **City abbreviations**: only Moscow (М.), St. Petersburg (СПб.), and a few others are conventionally abbreviated; other cities are spelled out.
- Don't mix dash-separated (older ГОСТ 2003 style) and period-only (2008 style) punctuation within one list — pick one and apply consistently, matching whatever the university's методичка specifies if given.

When converting a user's existing APA/MLA list, ask whether their department wants Cyrillic and Latin-script sources in one alphabetized list or two separate blocks — this varies by faculty.

## What this skill will NOT do

- Will not translate a paper wholesale from Chinese/English into Russian (that's a translation task — flag it as out of scope and suggest doing it as a separate explicit request)
- Will not fabricate citations, page numbers, or sources
- Will not strengthen or invent conclusions/results beyond what the data supports
- Will not guess a specific university's методичка requirements — always ask if the user has one, since it overrides ГОСТ defaults
