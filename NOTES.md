# Eleventy from Scratch

It fails the `npm i` install.
It tries to build `sass` in `c`!

So I removed all the dependancies, bringing them in one by one.

I got this far,

```json
    "@11ty/eleventy": "^0.12.1",
    "@11ty/eleventy-cache-assets": "^2.3.0",
    "@11ty/eleventy-plugin-rss": "^1.1.2",
    "html-minifier": "^4.0.0",
    "moment": "^2.29.1"
```

but then, the `css` files are not built.

Install `sass`, locally via `npm`, so that it runs with `npx sass`
We need to compile from `./src/scss/*.scss`, and output to `./src/_includes/css`.
The strategy is to build into the `src/css` folder as the first step,
and then include the `css` into inline tags in the `html`

So it seems the app does not have to link in a separate `.css` file.

That is working, but I needed to restore the `gorko` install.

That was great, now I get the `gorko` deprication warning, as the version has bumpped up.

`npm run clean, sass, dev`

So I trashed the entire `gulp` section, but I forgot to load the `google-fonts` thing.

Somehow, `addPassthroughCopy` got deleted from the `.eleventy` config, so I just restored it.

## Fonts

[Further Font Info](https://developers.google.com/fonts/docs/css2)

Since I deleted the `gulp` section, I have 3 supporting tasks to re-impliment.

- font
- image
- sass

Not doing image, as the imagemin seems to be boken again.
