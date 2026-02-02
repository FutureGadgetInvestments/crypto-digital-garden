# Crypto Investment Research Garden

A digital garden for exploring and documenting crypto investment ventures.

## Research Categories

- **Perp DEX Liquidity Pools**: Research on perpetual DEX LP strategies and yield opportunities
- **Stable Coins**: Analysis of stablecoin mechanisms, risks, and yield strategies
- **Zero Coupon Bonds**: Exploration of DeFi fixed income and zero coupon bond protocols

## Features

- **Bidirectional links**: Research automatically shows backlinks from other entries that reference them
- **Growth stages**: Mark research as seedling, budding, or evergreen to indicate maturity
- **Categories**: Organize research by investment category
- **Tags**: Additional organization with tags
- **Clean, minimal design**: Focus on content with a distraction-free layout

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

## Creating Research

Research lives in the `_research/` directory. Create a new Markdown file with front matter:

```markdown
---
title: My Research Title
date: 2026-02-02
status: seedling
category: perp-dex-liquidity-pools
tags: [topic1, topic2]
---

Your research content here...
```

### Front Matter Options

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | The research title |
| `date` | Yes | Creation date (YYYY-MM-DD) |
| `status` | No | Growth stage: `seedling`, `budding`, or `evergreen` |
| `category` | No | One of: `perp-dex-liquidity-pools`, `stable-coins`, `zero-coupon-bonds` |
| `tags` | No | List of tags |
| `last_modified_at` | No | Last update date |

### Linking Research

Link to other research using standard Markdown:

```markdown
Check out my analysis of [stablecoins](/research/stablecoin-overview).
```

Research will automatically display "Linked References" showing all entries that link to them.

## Structure

```
.
├── _config.yml          # Site configuration
├── _includes/           # Reusable components
├── _layouts/            # Page templates
├── _research/           # Your research entries
├── assets/
│   └── css/
│       └── style.css    # Styles
├── about.md             # About page
├── index.md             # Homepage
├── research.md          # Research index page
├── Gemfile              # Ruby dependencies
└── README.md
```

## Deployment

### GitHub Pages

1. Push to a GitHub repository
2. Go to Settings > Pages
3. Select your branch as the source
4. Site will be available at `https://username.github.io/repo-name`

## License

MIT License - see [LICENSE](LICENSE) for details.
