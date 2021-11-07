# Eleventy from Scratch

I took the eleventy from scratch .zip code and attempted to run it as is.
It fails the `npm i` install.
It seems to be trying to build `sass` with `Makefile`!

So I removed all the dependancies, bringing them in one by one.

I got this far, and I was able to at least build the main app code.

```json
    "@11ty/eleventy": "^0.12.1",
    "@11ty/eleventy-cache-assets": "^2.3.0",
    "@11ty/eleventy-plugin-rss": "^1.1.2",
    "html-minifier": "^4.0.0",
    "moment": "^2.29.1"
```

but then, the `css` files are not built.

The original lessons used `gulp`
to build three sections of the assets.

- font
- image
- sass

But `sass` can be built directly by it's built-in cli.

## Sass

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

## Image

Not doing image, as the imagemin seems to be boken again.

## Contact

Andy never built out the contact form, but it is traivial to do so with `netlify forms`

## Netlify CLI

`netlify init`
No git remote was found, would you like to set one up?

Then it gives the steps to follow

```bash
# 1. Initialize a new repo:
   git init
# 2. Commit your files
   git add .
# 3. Commit your files
   git commit -m 'initial commit'
# 4. Create a new repo in GitHub https://github.com/new

# 5. Link the remote repo with this local directory
   git remote add origin git@github.com:YourGithubName/your-repo-slug.git

# 6. Push up your files
   git push -u origin main

# 7. Initialize your Netlify Site
   netlify init
```
