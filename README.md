# 11ty-website-example

## Resources

- [How the Heck Do I Use Eleventy: The Intro Guide I Wish I Had](https://medium.com/@tarngerine/how-the-heck-do-i-use-eleventy-the-intro-guide-i-wish-i-had-84d9b2689031)
- [How to Deploy Eleventy to GitHub Pages with GitHub Actions](https://www.rockyourcode.com/how-to-deploy-eleventy-to-github-pages-with-github-actions/)

## Notes

If removing files, delete the `_sites` folder and re-run `npx @11ty/eleventy`.  The tool will not clean out old files.

With the line `"build": "npx @11ty/eleventy"` in the `scripts` section of the `package.json` file, you can call `npm run build` as shorthand for `npx @11ty/eleventy`.

Here are some default scripts:

``` js
    "build": "npx @11ty/eleventy",
    "serve": "npx @11ty/eleventy --serve"
```
