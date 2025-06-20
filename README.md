# Hacking Archives - Hugo Theme

This theme is based on [hugo-xmin](https://github.com/yihui/hugo-xmin) as the base template with extensive modifications to create a comprehensive cybersecurity community archive.

[![Screenshot](https://raw.githubusercontent.com/anantshri/hackingarchives-theme/main/images/screenshot.png)](https://github.com/anantshri/hackingarchives-theme)

## Notable Differences from hugo-xmin

This theme is a significant departure from the original hugo-xmin theme, with the following major enhancements:

- **Specialized Content Types**: Added dedicated templates for hackers, conferences, tools, books, and awards
- **Advanced Metadata Support**: Extended front matter with social media links, GitHub/GitLab integration, and rich metadata
- **Dynamic Relationships**: Automatic generation of collaboration networks and activity timelines
- **Visual Enhancements**: Tag clouds, profile photos, conference logos, and FontAwesome icons
- **Performance Optimizations**: Integration with hugo-booster for enhanced loading speeds
- **Responsive Design**: Mobile-first approach with dark mode support
- **Community Features**: Built specifically for documenting cybersecurity communities and their activities

## Features

The theme has been customized to support different content types with specialized templates for:

- **Hacker Profiles** - Individual security researcher pages with activity timelines
- **Conference Pages** - Event-specific pages with presentation listings
- **Tool Pages** - Security tool showcases with GitHub/GitLab integration
- **Book Pages** - Publication listings with purchase links
- **Award Pages** - Recognition and achievement showcases

## Content Organization

### Hacker Profiles
- Individual profile pages with professional information
- Activity timelines showing conference presentations, tools created, and collaborations
- Social media links and contact information
- Automatic generation of collaboration networks

### Conference Pages
- Event information and social media links
- Chronological listing of all presentations and participants
- Categorization by presentation type (talk, workshop, etc.)
- Integration with external media (videos, slides, papers)

### Tool Pages
- Tool descriptions and documentation links
- GitHub/GitLab integration with automatic badges
- Creator attribution and contributor information
- Usage statistics and download links

### Book Pages
- Publication metadata (ISBN, publisher, length, etc.)
- Author attribution and purchase links
- Category classification and release information

## Technical Features

- **Responsive Design** - Works on mobile and desktop devices
- **Dark Mode Support** - Automatic theme switching based on user preference
- **FontAwesome Integration** - Icons for different content types
- **GitHub/GitLab Badges** - Automatic repository statistics
- **Dynamic Video Playlists** - YouTube playlist generation
- **Tag Cloud Visualization** - Visual representation of community activity
- **Performance Optimized** - Built with Hugo Booster for fast loading

## Installation

1. Clone this repository to your Hugo themes directory
2. Copy the `exampleSite` content structure to your Hugo site
3. Update the configuration in `config.toml`
4. Replace sample content with your actual data
5. Run `hugo server` to preview your site

## Content Structure

```
content/
├── book/                    # Book publications
├── conference/              # Security conferences
│   └── conference_name/
│       └── _index.md
├── hacker/                  # Security researchers
│   └── hacker_name/
│       ├── _index.md        # Profile
│       └── event_name.md    # Individual activities
└── tool/                    # Security tools
    └── tool_name/
        └── _index.md
```

## Archetypes

The theme provides archetype templates for easy content creation:

- `archetypes/book.md` - Book entry template
- `archetypes/conference.md` - Conference page template
- `archetypes/hacker.md` - Hacker profile template
- `archetypes/entry.md` - Event entry template
- `archetypes/tool.md` - Tool page template

## Customization

- Modify CSS in `static/css/style.css`
- Update templates in `layouts/` directory
- Add custom FontAwesome icons in `static/fontawesome/`
- Configure social media links and metadata

## License

This theme is licensed under the MIT License. See the LICENSE file for details.

## Credits

- Based on the [hugo-xmin](https://github.com/yihui/hugo-xmin) theme by Yihui Xie
- Enhanced with [hugo-booster](https://github.com/anantshri/hugo_booster) for performance
- FontAwesome icons for enhanced visual presentation

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
