---
title: Home
---

# Hacking Archives

## _Documenting the Cybersecurity Community_

**Hacking Archives** is a comprehensive Hugo theme designed to create living archives of cybersecurity communities. It provides specialized templates and features for documenting security researchers, conferences, tools, and publications.

## What This Theme Does

This theme creates a connected network of cybersecurity activities, showing:

- **Individual Researchers**: Their profiles, activities, and collaborations
- **Security Conferences**: Events, presentations, and participants
- **Security Tools**: Software projects with GitHub/GitLab integration
- **Publications**: Books and papers with metadata and purchase links
- **Awards**: Recognition and achievements

## Key Features

- **Rich Metadata Support**: Social links, GitHub/GitLab integration, media links
- **Dynamic Relationships**: Shows collaborations between researchers, tools they've created, conferences they've presented at
- **Visual Elements**: Tag clouds, timeline views, profile photos, conference logos
- **Responsive Design**: Works on mobile and desktop with dark mode support
- **Performance Optimized**: Uses hugo-booster for enhanced performance

## Sample Content

This example site includes sample content for all content types:

- **Books**: Sample book entry with metadata and purchase links
- **Conferences**: Sample conference page with social media links
- **Hackers**: Sample researcher profile with activity timeline
- **Tools**: Sample tool page with GitHub integration

## Getting Started

1. Copy the `exampleSite` content structure to your Hugo site
2. Replace sample content with your actual data
3. Customize the configuration in `config.toml`
4. Add your own images to the appropriate directories
5. Run `hugo server` to preview your site

See the [About](/about/) page for detailed information about this theme and its features.

[<img src="https://simpleicons.org/icons/github.svg" style="max-width:15%;min-width:40px;float:right;" alt="Github repo" />](https://github.com/yihui/hugo-xmin)

# HUGO XMIN

## _Keep it simple, but not simpler_

**XMin** is a Hugo theme written by [Yihui Xie](https://yihui.name) in about four hours: half an hour was spent on the Hugo templates, and 3.5 hours were spent on styling. The main motivation for writing this theme was to provide a really minimal example to beginners of Hugo templates. This XMin theme contains about 130 lines of code in total, including the code in HTML templates and CSS (also counting empty lines).


```bash
find . -not -path '*/exampleSite/*' \( -name '*.html' -o -name '*.css' \) | xargs wc -l
```

```
       5 ./layouts/404.html
      12 ./layouts/_default/single.html
      20 ./layouts/_default/list.html
      13 ./layouts/_default/terms.html
       0 ./layouts/partials/foot_custom.html
       0 ./layouts/partials/head_custom.html
       9 ./layouts/partials/footer.html
      20 ./layouts/partials/header.html
      51 ./static/css/style.css
       7 ./static/css/fonts.css
     137 total
```

I can certainly further reduce the code, for example, by eliminating the CSS, but I believe a tiny bit of CSS can greatly improve readability. You cannot really find many CSS frameworks that only contain 50 lines of code.

Although it is a minimal theme, it is actually fully functional. It supports pages (including the home page), blog posts, a navigation menu, categories, tags, and RSS. With [a little bit customization](https://github.com/yihui/hugo-xmin/blob/master/exampleSite/layouts/partials/foot_custom.html), it can easily support LaTeX math expressions, e.g.,

`$${\sqrt {n}}\left(\left({\frac {1}{n}}\sum _{i=1}^{n}X_{i}\right)-\mu \right)\ {\xrightarrow {d}}\ N\left(0,\sigma ^{2}\right)$$`

All pages not under the root directory of the website are listed below. You can also visit the list page of a single section, e.g., [posts](/post/), or [notes](/note/). See the [About](/about/) page for the usage of this theme.
