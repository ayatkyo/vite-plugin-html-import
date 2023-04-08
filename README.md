# HTML Import - Vite plugin

Vite plugin for import .html as string.

[![NPM version](https://img.shields.io/npm/v/@ayatkyo/vite-plugin-html-import.svg)](https://www.npmjs.com/package/@ayatkyo/vite-plugin-html-import)

## 🤔 Why

Actually we can import html file as a string using:

```js
import htmlString from './partial.html?raw'
```

but when running `vite build` the html string is not minified and we need to add `?raw` to the import syntax.

So with this plugin, we just need to import html file as usual without adding `?raw`:

```js
import htmlString from './partial.html'
```

When running `vite build` the html string also minified.

If needed we also can do another thing to the html string buffer.

## ⚙️ Installing

```shell
npm i @ayatkyo/vite-plugin-html-import
```

## 📖 Usage

Make sure the `type` in the project `package.json` is set to `module`.

```json
{
  // ...
  "type": "module",
  // ...
}
```

Add `htmlImport` into plugins in `vite.config.js`:

```js
import htmlImport from '@ayatkyo/vite-plugin-html-import';

export default defineConfig({
  // ...
  plugins: [
    // ...
    htmlImport(),
  ],
});
```

Now we can import html file like this:

```js
import template from './path/to/file.html';

document.body.innerHTML = template;
// or
Vue.component('some-component', {
  template: template,
  // ...
});
```

## 🎯 TODO

- [ ] Add plugin configuration
  - [ ] Allow to disable minify using `minify: false`
  - [ ] Allow to pass configuration into `minify-html` plugin

## ⭐️ Thanks

- [Vite](https://vitejs.dev/)
- [minify-html](https://github.com/wilsonzlin/minify-html)
