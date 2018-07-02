# Leon Paternoster version ?

This is an old website which has largely remained in tact over the years.

It's been built on Jekyll for 5 (five!) years, and I'm starting again using my Jekyll Tachyons framework. It _should_ be a quick process, but let's see. Back to basics.

---

## Jekyll Tachyons docs

Jekyll Tachyons is a base Jekyll theme that:

- imports Tachyons modules as SASS files
- provides an option to inlines styles
- creates basic `default` and `post` layout files
- adds a `c-sans-serif` variable to `_variables.scss`
- adds a `.c-sans-serif` rule to `_c.scss`

### Installation

Clone or fork this repo, or download the files. Then:

1. if you haven't done so already, install [Bundler](http://bundler.io/)
2. navigate to the theme folder
3. run `bundle update`
4. run `bundle install`
5. run `bundle exec jekyll s` to serve and build the site

### Selecting Tachyons modules

Simply comment out any modules you don't want by preceding them with `//`.

The Tachyons modules live in the `_sass` directory, along with 2 additional SASS files:

- `_c.scss`, which includes any additional user styles (I normally precede these with a 'c-' to distinguish them from Tachyons selectors).
- `_variables.scss`, which includes any variables you want to refer to in `_c.scss`

Alternatively, import just the following files. You can comment out or even delete the rest.

1. `_tachyons-4.8.1.scss`
2. `_variables.scss`
3. `_c.scss`

If you haven't created any variables and/or custom rules, you'll only need to import `_tachyons-4.8.1.scss`.

### Inlining styles in the head or linking to a separate CSS file

You can get the theme to include styles within `<style></style>` tags in the document `head`. This saves a call to a separate CSS file, maybe speeding your site up a bit.

To inline your styles make sure you include this line in `_config.yml`:

`css: inline`

If you don't include the line, or change it to something like `css: linked`, the theme will link to a separate CSS file (`/css/style.css`).

Note that the theme is set to inline styles by default.

### Media queries

Tachyons is mobile first, i.e. media query breakpoints are only applied as the screen width increases. Default styles are applied to all screen widths.

It uses three breakpoints, which can be applied to almost all tachyons selectors through the `selector-[breakpoint-shorthand]` syntax. For example, the `db` selector (`display: block`) can be employed in these ways:

- `db` (default, applies to all screen widths)
- `db-ns` (applies to medium and large screen widths)
- `db-m` (applies to medium screen widths only)
- `db-l` (applies to large screen widths and up only)

You can define the ranges of `ns`, `m` and `l` in the `_media-queries.scss` file by overriding the defaults after they've been declared.

### Import Order

Because the SASS files refer to each other and `_c.scss` may refer to `_variables.scss`, the first files you import should be:

1. `_normalize.scss`
2. `_media-queries.scss`
3. `_variables.scss`
4. `_colors.scss`
5. `_spacing.scss`

### Moi

- [leonpaternoster.com](https://www.leonpaternoster.com)
- [Micro.blog](https://micro.blog/leonp)
- [Twitter](https://www.mobile.twitter.com/leonpaternoster)
