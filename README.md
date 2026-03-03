# Daysift Landing Page

Marketing website for Daysift - a Chrome extension for instant access to your work history.

## Files

| File | Description |
|------|-------------|
| `index.html` | Main landing page (version A) |
| `index-b.html` | Variant landing page (version B) - bolder typography, marquee, hover effects |
| `privacy.html` | Privacy policy |
| `terms.html` | Terms of service |
| `logo.png` | Current logo asset |
| `DEMO_SPEC.md` | Spec for the interactive demo carousel |
| `blog/` | Blog section |
| `blog/index.html` | Blog listing page |
| `blog/_template.html` | Article template (copy for new posts) |
| `blog/images/` | Article images |

## Brand

**Colors:**
- Background: `#FAFAF9`
- Foreground: `#1C1917`
- Muted: `#78716C`
- Accent (orange): `#F46B45`
- Border: `#E7E5E4`

**Font:** Inter (Google Fonts)

## Demo Carousel

The landing page features an interactive demo showing 5 screens:
1. **Search** - Typing "Q3 budget", showing results with favicons
2. **Filters** - Filter pills narrowing results to Google Docs
3. **AI Search** - Question with AI answer and code blocks
4. **Notes** - `/notes` command with floating notes window
5. **Commands** - Slash commands list (`/doc`, `/sheet`, `/figma`, etc.)

Auto-advances every 5 seconds with progress bar indicator. Manual switching pauses autoplay.

## Current Pricing (Free Tier)

- 30 days of history search
- 5 pinned items
- 5 notes
- 30 AI credits/month

## Deployment

Push to `main` branch auto-deploys to daysift.com:

```bash
git add -A && git commit -m "Update message" && git push
```

## Local Preview

```bash
open index.html
# or
open index-b.html
```

## Blog

### Creating a New Article

1. Copy `blog/_template.html` to `blog/article-slug.html`
2. Update the meta tags (title, description, canonical URL, OG image)
3. Update the structured data (headline, description, datePublished)
4. Write the article content
5. Add article card to `blog/index.html` (remove empty state when first article added)
6. Add article to `sitemap.xml`
7. Deploy: `git add -A && git commit -m "Add: article-slug blog post" && git push`

### Article Tags

Use consistent tags for categorization:
- **Productivity** — General productivity tips
- **Tutorial** — How-to guides for Daysift
- **Comparison** — vs competitor articles
- **ADHD** — Neurodivergent-focused content
