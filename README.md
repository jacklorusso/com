# eleventy-base-blog v9 -- with Deno 🦕

A starter repository showing how to build a blog with Deno and the [Eleventy](https://www.11ty.dev/) site generator (using the [v3.0 release](https://github.com/11ty/eleventy/releases/tag/v3.0.0)).

## Main changes from default [11ty blog starter](https://github.com/11ty/eleventy-base-blog)

### `package.json` is now `deno.json` (and `package-lock.json` is `deno.lock`)

- Scripts → tasks
- Dependencies → imports (via npm specifiers - now there is no more dependencies/devDependencies split)
- npx → direct deno run or deno task
- cross-env → not needed (Deno handles env vars cross-platform)

### Imports in JS files now use `npm:` specifiers

For example:

```diff
- import { feedPlugin } from "@11ty/eleventy-plugin-rss@^2.0.4";
+ import { feedPlugin } from "npm:@11ty/eleventy-plugin-rss@^2.0.4";

```

### No more including CSS or JS from node_modules

- Prism CSS now lives directly in `/css` (the `prism-diff.css` file already lived here)
- [@zachleat/heading-anchors](https://github.com/zachleat/heading-anchors) has been vendored (now lives in `_vendor` directory)

### Miscellanous

- nvmrc deleted
- node_modules removed from gitignore
- well-meaning but unwanted (by me) config files deleted: netlify, vercel, jekyll, editorconfig, gh-pages workflow


