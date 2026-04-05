# lottecss

![Homepage](https://img.shields.io/badge/website-lottecss.com-blue)

- out of the box design and styling for your app
- no need to apply classes
- use with your semantic HTML/JSX markup
- consistent styling for your elements
- minimal (familiar) utility classes so you don't need Tailwind

**Live demo & docs:** [https://lottecss.com](https://lottecss.com)

---

## Installation

```bash
yarn add lottecss
# or
npm install lottecss
```

## Development & Publishing

### Dependencies

**Dev Dependencies:**

- `autoprefixer` - Adds vendor prefixes for browser compatibility
- `cssnano` - Minifies CSS for production
- `postcss` - CSS processor
- `postcss-cli` - Command line interface for PostCSS

### Update and Publish Workflow

1. **Make your changes** to the CSS files in `src/css/`

2. **Build the distribution file:**

   ```bash
   yarn build
   # or
   npm run build
   ```

   This concatenates all CSS modules in the correct order and processes them through PostCSS (autoprefixer + cssnano).

3. **Update the version** in package.json:

   ```bash
   npm version patch  # for bug fixes (1.0.13 → 1.0.14)
   npm version minor  # for new features (1.0.13 → 1.1.0)
   npm version major  # for breaking changes (1.0.13 → 2.0.0)
   ```

4. **Commit and push changes:**

   ```bash
   git add .
   git commit -m "1.0.14"  # use the new version number
   git push origin main
   ```

5. **Publish to npm:**
   ```bash
   npm publish
   # or if using yarn
   yarn npm publish
   ```
