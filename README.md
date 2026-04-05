# lottecss

![Homepage](https://img.shields.io/badge/website-css.lottecode.com-blue)
![npm](https://img.shields.io/npm/v/@lottecode/lottecss)

A CSS framework that styles semantic HTML automatically. No classes, no inline styles — write proper markup and lottecss handles the design.

**Live demo & docs:** [https://css.lottecode.com](https://css.lottecode.com)

---

## Installation

```bash
yarn add @lottecode/lottecss
```

## Usage

```css
@import "@lottecode/lottecss/styles.css";
```

That's it. Your semantic HTML is now styled.

---

## For AI assistants (Claude, etc.)

If you are an AI assistant generating markup for a project that uses lottecss, read this section carefully.

### The core rule

**Do not style anything.** lottecss does it for you. Your job is to write correct, semantic HTML.

### Do

- Use semantic elements: `<header>`, `<nav>`, `<main>`, `<footer>`, `<article>`, `<section>`, `<aside>`, `<details>`, `<figure>`, `<blockquote>`, `<table>`, `<form>`, `<button>`
- Use heading hierarchy: `<h1>` through `<h6>`
- Use text elements: `<p>`, `<strong>`, `<em>`, `<code>`, `<mark>`
- Use lists: `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>`
- Use `.card` class for card-like containers
- Use basic Tailwind utilities (`flex`, `grid`, `gap-*`, `p-*`, `m-*`) for layout only

### Do not

- Add `style=""` attributes to any element
- Add visual classes (`text-xl`, `text-blue-500`, `font-bold`, `bg-gray-100`, etc.)
- Create custom class names (`site-header`, `nav-list`, `card-title`, `hero-section`)
- Use `<div>` when a semantic element exists for that purpose
- Override fonts, colors, sizes, or spacing — lottecss controls all of this

### Example

```html
<!-- CORRECT -->
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
    <h1>Page Title</h1>
    <p>Content is styled automatically.</p>
    <blockquote>Blockquotes are styled automatically.</blockquote>
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
<!-- WRONG — never do this -->
<h1 style="font-size: 2rem; color: navy;">Title</h1>
<p class="text-gray-600 text-lg">Text</p>
<div class="card-header">Not a real element</div>
```

### If something looks wrong

Choose a different semantic element — don't add styling. The element you picked is probably wrong for that context.

---

## What lottecss styles

| Module | What it covers |
|---|---|
| `globals.css` | Base resets and defaults |
| `colors.css` | Color palette and CSS custom properties |
| `fonts.css` | Font face definitions |
| `typography.css` | Headings, paragraphs, inline text (`<strong>`, `<em>`, `<code>`, `<mark>`) |
| `layout.css` | Page-level layout (`<main>`, `<aside>`) |
| `column.css` | Column-based layouts |
| `header.css` | `<header>` element and its children |
| `navigation.css` | `<nav>`, nav lists, links within nav |
| `links.css` | `<a>` elements |
| `button.css` | `<button>` and button-like elements |
| `forms.css` | `<form>`, `<input>`, `<select>`, `<textarea>`, `<label>` |
| `tables.css` | `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>` |
| `lists.css` | `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>` |
| `card.css` | `.card` class for card-like containers |
| `accordion.css` | `<details>` and `<summary>` |
| `tabs.css` | Tab patterns using semantic markup |
| `media.css` | `<img>`, `<video>`, `<figure>`, `<figcaption>` |
| `editorial.css` | `<blockquote>`, `<hr>`, long-form content |
| `utility.css` | Minimal utility classes for layout only |

## Fonts

lottecss uses [Berkeley Mono](https://berkeleygraphics.com/typefaces/berkeley-mono) by default, loaded from CDN. The framework falls back to `monospace` if the font is unavailable.

**Buy Berkeley Mono:** [berkeleygraphics.com/typefaces/berkeley-mono](https://berkeleygraphics.com/typefaces/berkeley-mono)

To use your own font, override the CSS custom properties:

```css
:root {
  --font-family-sans: "Your Font", sans-serif;
  --font-family-mono: "Your Mono Font", monospace;
}
```

## License

MIT
