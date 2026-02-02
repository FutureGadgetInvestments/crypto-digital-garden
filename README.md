# Digital Garden

A Jekyll template for creating a digital garden - a personal wiki of interconnected notes and ideas.

## Features

- **Bidirectional links**: Notes automatically show backlinks from other notes that reference them
- **Growth stages**: Mark notes as seedling, budding, or evergreen to indicate maturity
- **Tags**: Organize notes with tags
- **Clean, minimal design**: Focus on content with a distraction-free layout
- **Responsive**: Works on desktop and mobile
- **SEO-friendly**: Includes jekyll-seo-tag and sitemap generation

## Quick Start

### Prerequisites

- Ruby 2.7+
- Bundler (`gem install bundler`)

### Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Start the development server:
   ```bash
   bundle exec jekyll serve
   ```
4. Open http://localhost:4000 in your browser

## Creating Notes

Notes live in the `_notes/` directory. Create a new Markdown file with front matter:

```markdown
---
title: My Note Title
date: 2024-01-15
status: seedling
tags: [topic1, topic2]
---

Your note content here...
```

### Front Matter Options

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | The note title |
| `date` | Yes | Creation date (YYYY-MM-DD) |
| `status` | No | Growth stage: `seedling`, `budding`, or `evergreen` |
| `tags` | No | List of tags |
| `last_modified_at` | No | Last update date |

### Linking Notes

Link to other notes using standard Markdown:

```markdown
Check out my thoughts on [digital gardening](/notes/digital-gardening).
```

Notes will automatically display "Linked References" showing all notes that link to them.

## Customization

### Site Configuration

Edit `_config.yml` to set:
- Site title and description
- Author information
- Base URL (if not hosting at root)

### Styling

Modify `assets/css/style.css` to customize:
- Colors (via CSS variables)
- Typography
- Layout

### Layouts

Customize layouts in `_layouts/`:
- `default.html` - Base layout with header/footer
- `note.html` - Individual note pages
- `page.html` - Static pages
- `home.html` - Homepage

## Deployment

### GitHub Pages

1. Push to a GitHub repository
2. Go to Settings > Pages
3. Select your branch as the source
4. Site will be available at `https://username.github.io/repo-name`

Note: Update `baseurl` in `_config.yml` if deploying to a subdirectory.

### Other Platforms

The site can be deployed to any static hosting:
- Netlify
- Vercel
- Cloudflare Pages

Build command: `bundle exec jekyll build`
Output directory: `_site`

## Structure

```
.
├── _config.yml          # Site configuration
├── _includes/           # Reusable components
├── _layouts/            # Page templates
├── _notes/              # Your garden notes
├── assets/
│   └── css/
│       └── style.css    # Styles
├── about.md             # About page
├── index.md             # Homepage
├── notes.md             # Notes index page
├── Gemfile              # Ruby dependencies
└── README.md
```

## License

MIT License - see [LICENSE](LICENSE) for details.
