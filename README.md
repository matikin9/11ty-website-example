# 11ty-website-example

## Resources

- [How the Heck Do I Use Eleventy: The Intro Guide I Wish I Had](https://medium.com/@tarngerine/how-the-heck-do-i-use-eleventy-the-intro-guide-i-wish-i-had-84d9b2689031)
- [How to Deploy Eleventy to GitHub Pages with GitHub Actions](https://www.rockyourcode.com/how-to-deploy-eleventy-to-github-pages-with-github-actions/)
- [Liquid Template Defaults/Options](https://www.11ty.dev/docs/languages/liquid/)

## Notes

### Package.json

If removing files, delete the `_sites` folder and re-run `npx @11ty/eleventy`.  The tool will not clean out old files.  This can be automated by using the `scripts` section of `package.json`: `rm -rf folder_name`.

With the line `"build": "npx @11ty/eleventy"` in the `scripts` section of the `package.json` file, you can call `npm run build` as shorthand for `npx @11ty/eleventy`.

Here are some default scripts:

``` js
"build": "npx @11ty/eleventy",
"serve": "npx @11ty/eleventy --serve"
```

They can be chained like this:

``` js
"clean": "rm -rf docs",
"build": "npx @11ty/eleventy",
"clean:build": "npm run clean && npm run build"
```

### GitHub Pages Publishing

Switch the output folder from the default `_site` to `docs` in the `.eleventy.js` config file.

Add a path prefix for the repository name because eleventy assumes root by default.

``` js
module.exports = function(eleventyConfig) {
    return {
        pathPrefix: "/11ty-website-example/",
        dir: {
            output: "docs"
        }
    }
}
```

### Liquid Templates

To use includes without quotes, they need to be enabled via `dynamicPartials: false` in the Liquid options. Front matter in the include fill will not be evaluated. By default, includes must be formatted this way: `{% include 'user' %}`, which looks for `_includes/user.liquid`.
