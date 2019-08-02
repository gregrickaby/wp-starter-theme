WordPress Starter Theme
===

A fork of Automattic's _s, with modern CLI tooling based on [NPM scripts](https://github.com/gregrickaby/npm-scripts-boilerplate). No Gulp, Grunt, or Webpack required.

## Features

### HMR
- When you change a `.php`, `.scss`, `.svg`, or `.js` file, BrowserSync will make changes via hot module reloding.

### Enforcement of [WordPress Coding Standards](https://codex.wordpress.org/WordPress_Coding_Standards) via:

- PHPCS
- ESLint
- StyleLint

With each file change during `npm run watch`, you'll be notified in the command line of code warnings and errors.

### Asset minification

Sass and other assets are compiled, optimized, and minified to a `/dist` directory.

- SCSS
- JavaScript
- Images
- SVG icons

### Localization

- `.pot` file automatically generated on each build.

## Prerequisites

1. [Node/NPM](https://nodejs.org)
2. [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer)
3. [WordPress Coding Standards](https://github.com/WordPress/WordPress-Coding-Standards)

## Getting Started

If you want to set things up manually, download this repo from GitHub.

The first thing you want to do is copy the `_s` directory and change the name to something else (like, say, `my-theme`), and then you'll need to do a five-step find and replace on the name in all the templates.

1. Search for `'_s'` (inside single quotations) to capture the text domain.
2. Search for `_s_` to capture all the function names.
3. Search for `Text Domain: _s` in `style.css`.
4. Search for <code>&nbsp;_s</code> (with a space before it) to capture DocBlocks.
5. Search for `_s-` to capture prefixed handles.

OR

1. Search for: `'_s'` and replace with: `'my-theme'`.
2. Search for: `_s_` and replace with: `my_theme_`.
3. Search for: `Text Domain: _s` and replace with: `Text Domain: my-theme` in `style.css`.
4. Search for: <code>&nbsp;_s</code> and replace with: <code>&nbsp;My_Theme</code>.
5. Search for: `_s-` and replace with: `my-theme-`.

Then, update the stylesheet header in `style.css`, the links in `footer.php` with your own information and rename `_s.pot` from `languages` folder to use the theme's slug. Next, update or delete this readme.

## Setup

**Install**
```bash
npm i
```

**Set your proxy URL in `package.json` under the `serve` task.**
```bash
browser-sync start --https --proxy 'https://my-theme.test' --files \'dist/css/*.css, dist/js/*.js, **/*.html, !node_modules/**/*.html\'
```
(or you could remove the proxy... your choice!)

**Watch**
```bash
npm run watch
```
Now you're ready to go! The next step is easy to say, but harder to do: make an awesome WordPress theme. :)

Contributions are welcome, and good luck!
