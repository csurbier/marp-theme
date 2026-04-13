# Pitch — Marp Theme

A marketing-first theme for [Marp](https://marp.app/). Clean, bold, and conversion-oriented — built for decks that need to convince, present, and impress.

---

## Requirements

- [VS Code](https://code.visualstudio.com/) with the [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension, **or**
- [Marp CLI](https://github.com/marp-team/marp-cli) installed globally

---

## Installation

### Option A — VS Code (recommended)

1. Download `pitch.css` and place it in your project folder, e.g. `./themes/pitch.css`

2. Open VS Code **Settings** (`Ctrl+,` / `Cmd+,`) and search for **Marp: Themes**

3. Click **Add Item** and enter the path to the file:
   ```
   ./themes/pitch.css
   ```

4. Add the following front-matter at the very top of your `.md` file:
   ```yaml
   ---
   marp: true
   theme: pitch
   paginate: true
   ---
   ```

5. Open the Marp preview with `Ctrl+Shift+P` → **Marp: Open Preview**

---

### Option B — Marp CLI

1. Place `pitch.css` next to your Markdown file (or in a subfolder)

2. Export to PDF:
   ```bash
   marp --theme ./pitch.css deck.md -o deck.pdf
   ```

3. Export to HTML (shareable link):
   ```bash
   marp --theme ./pitch.css deck.md -o deck.html
   ```

4. Export to PowerPoint:
   ```bash
   marp --theme ./pitch.css deck.md -o deck.pptx
   ```

> **Note:** The theme loads fonts from Google Fonts (Poppins + Inter). An internet connection is required on the first export. For offline use, download the fonts locally and update the `@import` line at the top of the CSS.

---

## Slide classes

Apply a class to a single slide using the `_class` directive (two underscores, no space after `<!--`):

```markdown
<!-- _class: cover -->
```

Or apply a class to all slides in the front-matter:

```yaml
---
marp: true
theme: pitch
class: dark
---
```

---

### `cover` — Hero / Title slide

Use `h3` for a label above the title, `h1` for the main title, `h2` for the subtitle.

```markdown
<!-- _class: cover -->

### Campaign name or date
# Your Presentation Title
## A subtitle or tagline

**Company name** · Month Year
```

**Result:** Deep navy gradient background, large white title, orange-accented strong text.

---

### `section` — Chapter divider

Use `h1` for the chapter title and `h2` for the optional subtitle.

```markdown
<!-- _class: section -->

# Part 2
## What we'll cover next
```

**Result:** Light grey background, centered bold title with a gradient underline.

---

### `stats` — Big numbers / KPIs

There are two ways to use this slide:

**Single number** — use `h1` for the metric, `p` for the label:

```markdown
<!-- _class: stats -->

## Revenue this quarter

# $2.4M

Compared to $1.1M last year
```

**Multiple KPIs** — use a list where each item has a `**bold**` number followed by a label:

```markdown
<!-- _class: stats -->

## Results after 6 months

- **+127%** Monthly Active Users
- **4.8 ★** App Store Rating
- **92%** Customer Retention
- **$2.4M** Annual Recurring Revenue
```

**Result:** Large gradient numbers, clean grid layout, strong visual impact.

---

### `quote` — Testimonial or pull quote

Write the quote as a `> blockquote` and the attribution as a paragraph below.

```markdown
<!-- _class: quote -->

> The team went from spending 2 days on a deck to shipping one in 2 hours.

**Sarah K.** — Head of Marketing, TechCorp
```

**Result:** Large oversized quotation mark, bold serif-style text, clean attribution.

---

### `dark` — Inverted dark slide

Identical layout to the default slide but with a deep navy background and orange accents. Good for key messages you want to stand out.

```markdown
<!-- _class: dark -->

## What we're building next

- **Distribute** — native LinkedIn and Notion exports
- **Collaborate** — real-time co-editing
- **Measure** — slide-level engagement analytics
```

---

### `tinytext` — Dense reference slide

Reduces font size on paragraphs, lists, and tables. Useful for appendix or methodology slides.

```markdown
<!-- _class: tinytext -->

## Methodology & sources

- Data from Nielsen Q4 2024 report...
```

---

## Formatting shortcuts

The theme makes certain Markdown elements look different to suit marketing contexts.

### `**bold**` → accent color

In most slides, bold text renders in **indigo** — use it to highlight key terms, metrics, or names:

```markdown
We grew **127%** last quarter thanks to our **new onboarding flow**.
```

In `dark` slides, bold renders in **orange** for contrast.

---

### `` `backtick` `` → pill badge

Backtick-wrapped text renders as a rounded badge — great for statuses, tags, or labels:

```markdown
| Feature | Status     |
|---------|------------|
| Export  | `Live`     |
| API     | `Beta`     |
| Mobile  | `Planned`  |
```

---

### `> blockquote` → callout box

On regular slides, blockquotes render as a highlighted indigo callout box:

```markdown
> **Key insight:** 78% of lost deals cite poor presentation quality as a factor.
```

On `quote` slides, the blockquote is treated as the main pull quote (see above).

---

## Image helpers

Add keywords to the image alt text to control positioning:

```markdown
![center](image.png)    <!-- Centered horizontally -->
![right](image.png)     <!-- Floated to the right (~42% width) -->
![rounded](image.png)   <!-- Rounded corners with subtle shadow -->
![logo](image.png)      <!-- Small inline logo / icon -->
```

---

## Header, footer, and pagination

```yaml
---
marp: true
theme: pitch
paginate: true
header: "Acme Corp · Confidential"
footer: "April 2025"
---
```

Disable the page number on a single slide:

```markdown
<!-- _paginate: false -->
```

Disable on the cover only (common pattern):

```markdown
---
marp: true
theme: pitch
paginate: true
---

<!-- _class: cover _paginate: false -->

# Your Title
```

---

## Typical deck structure

Here is a recommended slide order for a marketing or sales deck:

```
1. cover        → Title, company, date
2. (default)    → Problem / context
3. (default)    → Your solution
4. stats        → Key metrics or proof points
5. section      → Part 2 — Product / Roadmap
6. (default)    → Detail slides
7. quote        → Customer testimonial
8. dark         → Key message / bold claim
9. (default)    → Pricing or next steps
10. cover       → Thank you / contact
```

---

## Quick reference

| Class      | Use case                            |
|------------|--------------------------------------|
| `cover`    | Title / hero slide (dark gradient)   |
| `section`  | Chapter divider (light, centered)    |
| `stats`    | Big numbers and KPIs                 |
| `quote`    | Testimonial or pull quote            |
| `dark`     | Inverted dark slide, bold statements |
| `tinytext` | Dense reference / appendix slides    |

| Markdown       | Renders as                          |
|----------------|--------------------------------------|
| `**bold**`     | Indigo accent text (orange on dark)  |
| `` `backtick` ``| Rounded pill badge                  |
| `> blockquote` | Indigo callout box (or pull quote)   |
| `==highlight==`| Orange highlight                     |

| Image keyword | Effect                              |
|---------------|--------------------------------------|
| `center`      | Center horizontally                  |
| `right`       | Float right (~42% width)             |
| `rounded`     | Rounded corners + shadow             |
| `logo`        | Small inline icon size               |

---

## Support

Questions or issues? Contact **csurbier@idevotion.fr**

---
 