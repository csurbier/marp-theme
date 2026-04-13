# Terminus — Marp Theme

A developer-first dark theme for [Marp](https://marp.app/), inspired by GitHub Dark and VS Code.

---

## Requirements

- [VS Code](https://code.visualstudio.com/) with the [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension, **or**
- [Marp CLI](https://github.com/marp-team/marp-cli) installed globally

---

## Installation

### Option A — VS Code (recommended)

1. Download `terminus.css` and place it in your project folder, e.g. `./themes/terminus.css`

2. Open VS Code **Settings** (`Ctrl+,` / `Cmd+,`) and search for **Marp: Themes**

3. Click **Add Item** and enter the path to the file:
   ```
   ./themes/terminus.css
   ```

4. Add the following front-matter at the very top of your `.md` file:
   ```yaml
   ---
   marp: true
   theme: terminus
   paginate: true
   ---
   ```

5. Open the Marp preview with `Ctrl+Shift+P` → **Marp: Open Preview**

---

### Option B — Marp CLI

1. Place `terminus.css` next to your Markdown file (or in a subfolder)

2. Export to PDF:
   ```bash
   marp --theme ./terminus.css deck.md -o deck.pdf
   ```

3. Export to HTML:
   ```bash
   marp --theme ./terminus.css deck.md -o deck.html
   ```

4. Export to PowerPoint:
   ```bash
   marp --theme ./terminus.css deck.md -o deck.pptx
   ```

> **Note:** The theme loads fonts from Google Fonts (Inter + JetBrains Mono). An internet connection is required the first time. For offline use, you can self-host the fonts and update the `@import` line at the top of the CSS.

---

## Slide classes

Apply a class to a single slide using the `_class` directive:

```markdown
<!-- _class: cover -->
```

Or apply it globally in the front-matter:

```yaml
---
marp: true
theme: terminus
class: terminal
---
```

### `cover` — Title / Hero slide

```markdown
<!-- _class: cover -->

# Your Presentation Title
## A subtitle or tagline

**Author** · `v1.0` · April 2025
```

### `section` — Chapter divider

```markdown
<!-- _class: section -->

# Part 2
## What we'll cover next
```

### `terminal` — Full terminal look

Titles are automatically prefixed with a `$` prompt. Lists use `>` markers.

```markdown
<!-- _class: terminal -->

# deploy --production

- build passed in 42s
- tests 148/148 OK
- deployed to https://yourapp.io
```

### `light` — Light variant

Same design, white background. Useful for screenshots or bright rooms.

```markdown
<!-- _class: light -->

## This slide uses the light variant
```

### `split` — Two-column layout

Write your left column content normally. Use a `>` blockquote for the right column.

```markdown
<!-- _class: split -->

## Slide title

Left column content here.
Can contain text or bullet points.

> Right column content here.
> Use it for code, images,
> or contrasting information.
```

### `center` — Vertically centered content

```markdown
<!-- _class: center -->

## Centered slide

Content is vertically centered on the slide.
```

### `tinytext` — Fit more content

Reduces the font size of paragraphs, lists, and blockquotes. Useful for reference slides.

```markdown
<!-- _class: tinytext -->

## References

- Long list of items that would not otherwise fit on a single slide...
```

---

## Image helpers

Add keywords to the image alt text to control positioning:

```markdown
![center](image.png)   <!-- Centered horizontally -->
![right](image.png)    <!-- Floated to the right (45% width) -->
![badge](logo.png)     <!-- Inline, icon-sized -->
![rounded](photo.png)  <!-- Rounded corners + border -->
```

---

## Header, footer, and pagination

Configure these in the front-matter:

```yaml
---
marp: true
theme: terminus
paginate: true
header: "My Company · Confidential"
footer: "April 2025"
---
```

Disable pagination on a single slide:

```markdown
<!-- _paginate: false -->
```

---

## Callout boxes

Use blockquotes with a bold label to create callout-style boxes:

```markdown
> **NOTE** This is an informational note.

> **WARN** This is a warning.

> **TIP** This is a helpful tip.
```

---

## Highlighted text

Wrap text in `==double equals==` to highlight it (requires Marp's `markdown.marp.enableHtml: false` — this is standard Marp syntax):

```markdown
This is ==highlighted== text.
```

---

## Quick reference

| Class       | Use case                        |
|-------------|----------------------------------|
| `cover`     | Title / hero slide               |
| `section`   | Chapter divider                  |
| `terminal`  | CLI / deployment / ops slides    |
| `light`     | Light background variant         |
| `split`     | Two-column layout                |
| `center`    | Vertically centered content      |
| `tinytext`  | Dense reference slides           |

| Image keyword | Effect                          |
|---------------|---------------------------------|
| `center`      | Center horizontally             |
| `right`       | Float right (45% width)         |
| `badge`       | Inline icon size                |
| `rounded`     | Rounded corners + border        |

---

## Support

Questions or issues? Contact **csurbier@idevotion.fr**

---
 