---
marp: true
theme: terminus
paginate: true
---

<!-- _class: cover -->

# Terminus
## A developer-first Marp theme

**enprod.fr** · `v1.0`

---

## What's included

- **5 slide classes** : `cover`, `section`, `terminal`, `light`, `split`
- Syntax highlighting styles optimized for code-heavy decks
- JetBrains Mono + Inter font pairing
- GitHub Dark color palette with light variant
- Custom callouts, tables, image helpers

---

## Code blocks look great

Install the theme in VS Code:

```bash
# 1. Download terminus.css
# 2. Add to your VS Code settings.json
"markdown.marp.themes": ["./presentation/custom-theme/terminus.css"]
```

Then activate it in your front-matter:

```yaml
---
marp: true
theme: terminus
---
```

---

## Tables are readable

| Feature        | Free themes | **Terminus** |
|----------------|:-----------:|:------------:|
| Dark mode      | ✓           | ✓            |
| Light variant  | ✗           | ✓            |
| Dev color palette | ~        | ✓            |
| Monospace UI   | ✗           | ✓            |
| Split layout   | ✗           | ✓            |
| Callout boxes  | ✗           | ✓            |

---

<!-- _class: terminal -->

# deploy --production

## All systems operational

- `build` passed in 42s
- `tests` 148/148 OK
- `lighthouse` score: 98/100
- Deployed to **https://yourapp.io**

---

<!-- _class: section -->

# Chapter 2
## Architecture & Design

---

<!-- _class: split -->

## Two-column layout

Left column content here.
Use it for code snippets,
bullet points, or text.

> Right column content.
> Perfect for diagrams,
> screenshots, or contrasting
> information.

---

<!-- _class: light -->

## Light variant

Same theme, light background.  
Great for slides with screenshots
or when projecting in bright rooms.

```python
def greet(name: str) -> str:
    return f"Hello, {name}!"
```

---

<!-- _class: cover -->

# Thanks
## Get Terminus at enprod.fr

**Questions?** `csurbier@idevotion.fr`
