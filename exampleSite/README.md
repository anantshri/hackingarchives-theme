# Example Site Structure

This example site demonstrates how to use the Hacking Archives Hugo theme. It includes sample content for all the main content types supported by the theme.

## Content Structure

### Books (`content/book/`)
- One markdown file per book
- Contains metadata like ISBN, publisher, authors, purchase links
- Example: `sample-security-book.md`

### Conferences (`content/conference/<conference_name>/`)
- Each conference has its own directory with an `_index.md` file
- Contains conference information, social links, and description
- Example: `conference_name/_index.md`

### Hackers (`content/hacker/<hacker_name>/`)
- Each hacker has their own directory with an `_index.md` file for their profile
- Individual event entries are stored as separate markdown files
- Example: `hacker_name/_index.md` and `hacker_name/sample-security-talk.md`

### Tools (`content/tool/<tool_name>/`)
- Each tool has its own directory with an `_index.md` file
- Contains tool information, GitHub/GitLab links, and description
- Example: `tool_name/_index.md`

## Archetypes

The theme provides several archetype templates for creating new content:

- `archetypes/book.md` - Template for new book entries
- `archetypes/conference.md` - Template for new conference pages
- `archetypes/hacker.md` - Template for new hacker profiles
- `archetypes/entry.md` - Template for new event entries
- `archetypes/tool.md` - Template for new tool pages

## Usage

1. Copy this example site structure to your Hugo site
2. Replace the sample content with your actual data
3. Customize the configuration in `config.toml`
4. Add your own images to the appropriate directories
5. Run `hugo server` to preview your site

## Metadata Fields

### Book Entries
- `title`, `type`, `date`, `publisher`, `hacker`, `print_isbn13`, `published_on`, `category`, `length`, `released`, `imageUrl`, `book_link`, `amazon`

### Conference Pages
- `title`, `youtube`, `home`, `twitter`, `linkedin`, `mastodon`

### Hacker Profiles
- `title`, `date`, `draft`, `linkedin`, `twitter`, `home`, `github`

### Event Entries
- `title`, `date`, `conference`, `draft`, `type`, `hacker`, `year`, `conf_link`, `presentation`, `whitepaper`, `video`, `source`, `tag`

### Tool Pages
- `title`, `youtube`, `home`, `twitter`, `github`, `producthunt`, `download`, `linkedin`, `documents`, `mastodon`, `facebook` 