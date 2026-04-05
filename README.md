# lottecss

![Homepage](https://img.shields.io/badge/website-lottecss.com-blue)

A CSS framework that styles semantic HTML automatically. No classes, no inline styles — just write proper markup and lottecss handles the design.

**Live demo & docs:** [https://lottecss.com](https://lottecss.com)

---

## Installation

Add the lottecode registry to your project's `.yarnrc.yml`:

```yaml
npmScopes:
  lottecode:
    npmRegistryServer: "https://npm.pkg.github.com"
```

Then install:

```bash
yarn add @lottecode/lottecss
```

## Usage

```css
@import "@lottecode/lottecss/styles.css";
```

## How It Works

lottecss targets semantic HTML elements directly. You do not add classes or inline styles to control appearance. The framework styles elements based on what they are and where they sit in the document structure.

### Rules

- **Use semantic HTML elements**: `<header>`, `<nav>`, `<main>`, `<footer>`, `<article>`, `<section>`, `<aside>`, `<h1>`–`<h6>`, `<p>`, `<ul>`, `<ol>`, `<blockquote>`, `<table>`, `<form>`, `<button>`, `<details>`, `<figure>`
- **Never add inline styles** (`style=""`) to semantic elements
- **Never add styling classes** (no `className="text-xl text-blue-500"` on headings, paragraphs, etc.)
- **No custom class names** like `"site-header"`, `"nav-list"`, `"card-title"` — use the semantic element itself
- **Layout utilities only**: basic Tailwind utility classes (`flex`, `grid`, `gap-*`, `p-*`, `m-*`) are acceptable for layout purposes only, not for visual styling

### Examples

```html
<!-- CORRECT: pure semantic markup, lottecss handles all styling -->
<header>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <h1>Article Title</h1>
    <p>Paragraph text styled automatically.</p>
    <blockquote>A styled blockquote.</blockquote>
    <ul>
      <li>Styled list item</li>
    </ul>
  </article>
  <aside>
    <h2>Sidebar</h2>
    <p>Sidebar content.</p>
  </aside>
</main>

<footer>
  <p>Footer content.</p>
</footer>
```

```html
<!-- WRONG: do not do this -->
<h1 style="font-size: 2rem; color: navy;">Title</h1>
<p class="text-gray-600 text-lg">Text</p>
<div class="card-header">Not a real element</div>
```

### What lottecss Styles

| Module | What it covers |
|---|---|
| `typography.css` | Headings, paragraphs, inline text (`<strong>`, `<em>`, `<code>`, `<mark>`) |
| `navigation.css` | `<nav>`, nav lists, links within nav |
| `header.css` | `<header>` element and its children |
| `button.css` | `<button>` and button-like elements |
| `forms.css` | `<form>`, `<input>`, `<select>`, `<textarea>`, `<label>` |
| `tables.css` | `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>` |
| `lists.css` | `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>` |
| `card.css` | `<article>` and `<section>` as card-like containers |
| `accordion.css` | `<details>` and `<summary>` |
| `tabs.css` | Tab patterns using semantic markup |
| `media.css` | `<img>`, `<video>`, `<figure>`, `<figcaption>` |
| `links.css` | `<a>` elements |
| `editorial.css` | `<blockquote>`, `<hr>`, long-form content |
| `layout.css` | Page-level layout (`<main>`, `<aside>`) |
| `column.css` | Column-based layouts |
| `colors.css` | Color palette and CSS custom properties |
| `fonts.css` | Font face definitions (Berkeley Mono) |
| `globals.css` | Base resets and defaults |
| `utility.css` | Minimal utility classes for layout only |

## Fonts

lottecss uses [Berkeley Mono](https://berkeleygraphics.com/typefaces/berkeley-mono) by default, loaded from `assets.lottecode.com`. The system falls back to `monospace` if the font is unavailable.

To use your own font, override the CSS custom properties:

```css
:root {
  --font-family-sans: "Your Font", sans-serif;
  --font-family-mono: "Your Mono Font", monospace;
}
```

### Key Principle

If you're reaching for a class name or inline style to make something look right, you're probably using the wrong HTML element. Choose the element that semantically represents your content and lottecss will style it correctly.
